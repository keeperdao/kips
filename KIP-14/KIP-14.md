# KIP-14: Allocate $5,000,000 in stablecoins to act as a traveling liquidation backstop for B.Protocol B.AMMs
```
kip: 14
title: Allocate $5,000,000 in stablecoins to act as a traveling liquidation backstop for B.Protocol B.AMMs
author: hazard <hazard@keeperdao.com>, exeggcute <exeggcute@keeperdao.com>
status: last-call
tags: none
created: 2022-01-14
replaced-by: none
replaces: none
```
## Proposal

Commit $5,000,000 in stablecoins from the KeeperDAO Treasury [1] to act as seed liquidity for B.Protocol backstop AMMs (”B.AMMs”) that support the Hiding Game.

## References

1. [0x9a67F1940164d0318612b497E8e6038f902a00a4](https://app.zerion.io/0x9a67F1940164d0318612b497E8e6038f902a00a4)
2. [B.AMM: Efficient Automated Market Maker for DeFi Liquidations (B.Protocol Blog)](https://medium.com/b-protocol/b-amm-efficient-automated-market-maker-for-defi-liquidations-fea7b0fdc0c5)
3. [B.AMM whitepaper](https://cloudflare-ipfs.com/ipfs/Qmb2ZMk7F48jYSwJczdJeqXJz7CZVh8H4KnfyNdHZSMRG5)
4. [KeeperDAO Coordination Game Economics](https://docs.keeperdao.com/reference/developers/coordination-game/economics)
5. [https://dune.xyz/dani/Liquity](https://dune.xyz/dani/Liquity)

## Background

The B.Protocol B.AMM [2,3] is a novel automated market maker smart contract which allows backstop liquidity providers (”Backstoppers”) to earn fees during liquidations. Backstoppers provide liquidity (e.g. DAI), which normally sits idle and farms yield. When a loan becomes liquidatable, the protocol removes some idle funds (e.g. DAI) in order to purchase the distressed collateral (e.g. ETH), removing the risk from the lending protocol and restoring the health of the loan. 

The system, which was balanced before, is now long ETH and short DAI, and needs to rebalance. The B.AMM facilitates rebalancing with a pricing curve derived from the Curve CFMM formula, which will offer traders on the B.AMM a discount that incentivizes them to arbitrage away the imbalance. Fees collected from swaps on the B.AMM go to the Backstoppers.

For a full report, see the B.Protocol B.AMM blog post [2] or B.AMM whitepaper [3].

### KeeperDAO Coordination facility

KeeperDAO and B.Protocol have worked together to research an improvement to the B.AMM which will increase the efficiency of small to medium-sized liquidations, adding value for both B.AMM LPs and the lending protocols which the B.AMM is used to backstop.

Through a modification of the B.AMM fees, KeeperDAO can extend the Coordination protocol to the B.AMM, creating a highly efficient environment that prevents MEV leakage and allows KeeperDAO keepers to perform rapid, continuous removal of small to medium-sized portfolio imbalances in the B.AMM. 

The fee modification will allow KeeperDAO keepers to reach arbitrage price sooner, hiding MEV and allowing execution to take place through the Coordination protocol, where it can be fairly re-distributed. The improved rebalance efficiency that results will in turn improve yields for Backstoppers, since less of the collateral will be lost to the discount, ultimately helping the B.AMM in its goal of incentivizing a steady reserve of backstop liquidity. The vast majority (~80%) of the MEV captured by KeeperDAO will be redistributed back to the B.AMM through the Coordination Game Economic System [4]. This is Coordinomics in action — everybody wins.

### KeeperDAO liquidity commitment

For every B.AMM that supports the Coordination protocol, KeeperDAO will commit seed liquidity to help the B.AMM reach immediate production readiness after deployment. This will allow integration partners to be assured of an adequate backstop and service level from the start, and have the added benefit of assuring our commitment to servicing the B.AMM.

Once a particular B.AMM is saturated with other LPs, KeeperDAO may withdraw the seed liquidity and make it available for a successive integration. Deposits in the B.AMM are yield-bearing, and are estimated to earn roughly 10% APY depending on the asset.

### Transaction flow for KeeperDAO Keepers

The initial B.AMM to support the Coordination protocol is planned to be the B.AMM currently supporting Liquity’s LUSD token.

The B.AMM currently handles approximately 25% of all LUSD liquidations. LUSD liquidation activity can be viewed using the Liquity Dune Analytics dashboard [5].

## Specification

1. Earmark $5,000,000 of stablecoins from the KeeperDAO Treasury for use as seed liquidity for new B.AMM deployments that support the Hiding Game.
2. Stand ready to deposit this liquidity in successive target B.AMM contracts after security review, auditing, and deployment is complete, as long as other capital requirements have been met.
3. Return this liquidity along with any yields accrued during its use, to the KeeperDAO Treasury on completion of the program, as determined by the relevant contributors.
