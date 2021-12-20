# KIP-10: Provide ROOK-ETH Uniswap v3 Liquidity with Visor Finance
```
kip: 10
title: Provide ROOK-ETH Uniswap v3 Liquidity with Visor Finance
author: bjp333 <brian@visor.finance>
status: last-call
tags: none
created: 2021-10-21
replaced-by: none
replaces: none
```
## Proposal
* Treasury management for KeeperDao’s protocol controlled assets for the ROOK-ETH pool on Uniswap v3

* KeeperDAO provides $1,000,000 USD of ROOK and $1,000,000 USD of ETH for active management by Visor Finance with the express goal of earning yield and providing liquidity

## Background
Visor Finance is an active manager focused on liquidity provisioning strategies on Uniswap v3. It provides an infrastructure for protocols to use their own treasury funds to provide liquidity and generate yield. By providing liquidity on Uniswap v3 via Visor Finance, there will be deeper liquidity for the ROOK-ETH pair and an opportunity to generate higher yield on KeeperDAO’s protocol controlled assets.

## Analysis

The capital efficiency of Uniswap v3 offers many advantages.  Given that much of the liquidity will be concentrated around the current price tick, there will be less slippage for same volume trades on the same amount of liquidity as on Sushiswap (or Uniswap v2).  For example, concentrating liquidity around +/-50% of the current price may have up to 4x the capital efficiency of Sushiswap and may require less than 25% of the liquidity as Sushiswap. Additionally, the lower liquidity threshold required on Uniswap v3 allows for KeeperDAO to provide the liquidity with its own treasury and diminishes the need to pay liquidity mining rewards for ROOK-ETH.

Managing the price range on Uniswap v3 requires active management, which is provided by Visor Finance and its research organization Gamma Strategies.  As the price of ROOK varies, Visor Finance will ensure that the price stays within range and that there is sufficient liquidity to support ROOK-ETH trade volume.

The current liquidity for ROOK-ETH is segregated among various AMMs which is inefficiently routing trades when using a DEX aggregator like 1inch or paraswap. The current liquidity situation is as follows:

* Bancor: BNT / ROOK liquidity of $11M
* Sushi: ETH / ROOK liquidity of $4.4M
* Uni v2: ETH / ROOK liquidity of $4.8M
* Uni v3: ETH / ROOK liquidity of $1.0M

Currently, a 10 ETH trade for ROOK is being routed partially to Bancor, Sushi, and/or Uni v2 when using a DEX aggregator like 1inch because 1inch is routing trades in a way that gets the most favorable price impact based on slippage. The current slippage for a 10 ETH trade on each of the AMMs are as follows:

* Bancor: 1.2%
* Sushi: 2.1%
* Uni v2: 1.4%
* Uni v3: 0.8 - 3% (can vary depending on price action & placement of other liquidity)

Therefore, in order to provide liquidity on Uni v3 to maximize profitability for KeeperDAO, the slippage should be lowered to 1.2% or below for a 10 ETH purchase.

According to our analysis here: https://docs.google.com/spreadsheets/d/1eCyNRl1jmk5f6Ndqk2V_BSVyCCO3hCTzUhgFYgy8K5Y/edit#gid=0, we believe $3M of total liquidity, placed in at least a +/- 40% range would be ideal for absorbing most of the trade volume from ETH to ROOK on Uni v3. Given the existing liquidity of $1M already in the Uni v3 pool, at least $2M should be provided by the KeeperDAO treasury to increase the likelihood of trades being routed to v3 and capturing the most volume & profitability.

## Risks
*Other liquidity:*  Currently, the majority (or over 80% of the liquidity) is currently being provided by a single address:  0xD6Cb7a7b544E24e5160A948a16C45b1096276F9d.  This could potentially leave KeeperDAO in a vulnerable position if all of that liquidity were to be removed by that single provider, and trades were continuously being routed through other venues.

*Impermanent loss:*  Providing liquidity in a narrower price range can lead to earning higher fees, but can subject the liquidity provider to greater impermanent loss as prices of the underlying assets diverge.  Conversely, providing liquidity in a wider range will earn less fees than a narrower one, but are accordingly at lower risk of  suffering impermanent losses when there is price divergence.  

Gamma Strategies aims to reduce the risks of impermanent loss by widening the ranges during periods of high volatility and narrowing the ranges in periods of low volatility in order to maximize yields.

## Process
KeeperDAO will supply $1,000,000 USD of ROOK and $1,000,000 USD of ETH to the Visor position manager contract called the Hypervisor (https://github.com/VisorFinance/hypervisor/blob/master/contracts/Hypervisor.sol) , which will mint fungible ERC-20 LP tokens to a whitelisted address provided by KeeperDAO. 
Only the whitelisted address provided by KeeperDAO will have the right to deposit / withdraw assets to and from the Hypervisor.  The position manager contract has the right to a few functions which are to set base ranges, set limit ranges, collect fees, rebalance, and mint/burn LP tokens to the whitelisted address.  Therefore, the Hypervisor contract has only management rights and is non-custodial in that only the provided whitelisted address may deposit / withdraw assets into and out of the contract.

Visor Finance takes 10% of earned fees, which get distributed to VISR stakers.  90% of earned fees will be automatically re-invested into the LP position upon each rebalance.  Visor Finance will cover all gas fees for rebalancing positions and re-investing earned fees. 


## Specification
1. Send $1,000,000 USD of ROOK and $1,000,000 USD of ETH to the ROOK-ETH Hypervisor to be managed on the ROOK-ETH pool on Uniswap v3
2. Receive ERC-20 LP tokens in the whitelisted address provided by KeeperDAO

