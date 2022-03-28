# KIP-18: Power Gamma Hypervisors with KeeperDAO Coordination protocol

```
kip: 18
title: Power Gamma Hypervisors with KeeperDAO Coordination Protocol
author: hazard <hazard@keeperdao.com>, exeggcute <exeggcute@keeperdao.com>
status: last-call
tags: none
created: 2022-02-02
replaced-by: none
replaces: none
```

## Proposal

Collaborate with Gamma Strategies to build advanced Hypervisor contracts powered by the KeeperDAO Coordination protocol.

## Summary

Gamma Strategies (https://www.gammastrategies.org) is the leading provider of active liquidity management and discretionary liquidity strategies. Gamma’s products allow depositors to stabilize or enhance returns on concentrated liquidity AMMs like Uniswap v3 and the upcoming Sushi Trident and CrocSwap, without the need to manage the position themselves.

A perpetual concern for such products is the potential for MEV when a position is being updated, as well as the negative impact of just-in-time (JIT) liquidity operations from sophisticated participants which can alter market structure to the detriment of the automated strategy.

To tackle these challenges, Gamma is partnering with KeeperDAO to integrate with the KeeperDAO Coordination protocol, which will offer LPs unprecedented access to our world-class execution network.

By coordinating position updates with our network of keepers, Gamma’s products will not just mitigate MEV, but capture it and use it to drive enhanced returns. Moreover, LPs will gain exposure to the most advanced JIT liquidity strategies, powered by the very keepers who had been competing against them in the liquidity pool! 

## Background

### Concentrated liquidity and active position management

Automated market makers (AMMs) with support for concentrated liquidity allow liquidity providers (LPs) to specify a price range in which their liquidity becomes available to traders, rather than allowing it to be available across the entire pricing curve.

A sophisticated LP will seek to increase returns by actively managing their position, i.e. dynamically altering the ranges where their liquidity is provided, in order to minimize adverse selection and maximize fees accrued.

### Hypervisors

Gamma Strategies provides a smart contract called a “Hypervisor” that makes active position management strategies more accessible to regular LPs. Rather than provide liquidity to the AMM directly, depositors provide it to a Hypervisor contract, which then creates and manages a position on the target AMM using the deposited funds.

- Hypervisor smart contract source code: [https://github.com/GammaStrategies/hypervisor/blob/519117704a67659273b78658ad43bcad8a8073ce/contracts/Hypervisor.sol](https://github.com/GammaStrategies/hypervisor/blob/519117704a67659273b78658ad43bcad8a8073ce/contracts/Hypervisor.sol)
- More information about Hypervisors: [https://docs.gammastrategies.org/gamma/features/hypervisor](https://docs.gammastrategies.org/gamma/features/hypervisor)

### How the Hypervisor works

A Hypervisor maintains a position consisting of two UniswapV3Pool positions:

1. A base position*,* which must match the pool's current ratio of token0 and token1 in composition.
2. A limit position, which contains a single asset (often what cannot be deposited in the base position due to the mechanics of concentrated liquidity).

An advisor is an account designated by the deployer of the Hypervisor contract. The advisor alone has the right to call functions that modify the Hypervisor’s position. These functions are:

- `rebalance` rebalance the position
- `addBaseLiquidity` deploy assets to the base position without rebalancing
- `addLimitLiquidity` deploy assets to the limit position without rebalancing
- `pullLiquidity` remove liquidity from the Uniswap v3 pool

The most important and frequently-called of all the position update functions is `rebalance`. During a `rebalance` call:

1. Liquidity is removed from the base position & limit position.
2. Accrued fees are collected.
3. 10% of the assets are transferred to the Gamma *Swap* contract.
4. The removed liquidity, 90% of the fees, and assets in the Hypervisor, are then placed in a new base position and limit position.
5. (Optionally) perform a swap of assets, by using the `swapQuantity` parameter of the `rebalance` function.

### The impact of MEV on LP returns

Depending on the liquidity of the pool, the size of the position, and the balance of the assets in the Hypervisor, rebalancing can create a meaningful amount of MEV. 

It is important for the Hypervisor to mitigate front-running or sandwiching of rebalance transactions due to the negative impact on LP returns and the risk to LP capital that they pose. To accomplish mitigation Hypervisors today broadcast rebalance transactions via Flashbots RPC, and this has been effective at preventing this MEV leakage. 

Backrunning remains a possibility. It is not uncommon for a backrunning transaction to appear at the top of the block following the Flashbots block in which a rebalance occurs. 

Example: 

- Rebalance transaction [https://etherscan.io/tx/0xe64caff620f1aeb818743a63c5fcd787dd6612c3b31fdf314ce0d9523bc0ffb5](https://etherscan.io/tx/0xe64caff620f1aeb818743a63c5fcd787dd6612c3b31fdf314ce0d9523bc0ffb5)
- Rebalance backrun [https://etherscan.io/tx/0xa5b02ec1e1810e00f514dec7a58c15f36d446ebae7b6dd4b04aa44fe9712fef6](https://etherscan.io/tx/0xa5b02ec1e1810e00f514dec7a58c15f36d446ebae7b6dd4b04aa44fe9712fef6)

While this backrunning does not negatively impact LP returns, it does represent value that is directly attributable to the rebalance, which could be internalized to increase those returns.

## Specification

### A Coordination Facility for Hypervisors

Gamma Strategies and KeeperDAO will work together to create an advanced Hypervisor for which all position management transactions, including rebalances, are routed through the KeeperDAO Coordination Game and executed by Keepers acting through the Coordination protocol.

We expect that the addition of Coordination will allow LP returns to be enhanced through a combination of new efficiencies and strategies, including:

- **Internalized backrun arbitrage**: Hypervisor LPs can now receive approximately 80% of the value of any backrun arbitrage executed as the result of a rebalance.
- **New pool arbitrage**: Hypervisor LPs can now receive 80% of the value of any pool initialization arbitrage that becomes available when the Hypervisor is the initial deployment of liquidity to a Uniswap v3 pool.
- **Just-in-time (”JIT”) liquidity**: Hypervisor LPs can now be included in just-in-time (JIT) liquidity strategies by specialized Keepers acting through the Coordination protocol. LPs can expect greater returns from a combination of fee concentration and reduced IL. Such JIT liquidity would be available for both Hiding Book orders and Uniswap v3 simultaneously.

### Service requirements

Gamma Strategies has a number of requirements that must be met as service conditions for the arrangement.

All will be accomplished through the use of policies governing the behavior of Keepers. Additional backstop mechanisms will be discussed as the technical collaboration advances.

1. Avoidance of any situation which results in loss to TVL of our Hypervisor positions as defined by value of underlying assets in position.
2. All arbitrage opportunities would occur after a `rebalance` transaction.
3. Directed manipulation of the Uniswap v3 price oracle must be avoided.
    1. Example: Price manipulation that leads to liquidity being all in one asset, which can lead to a user depositing into our Hypervisor with a single asset and then withdrawing a disproportionate amount.
    2. Example: Manipulating the Uniswap v3 price oracle to inflate the value of one’s collateral to drain a lending pool.
