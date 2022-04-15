# KIP-20: Fund an R&D grant to study a dedicated arbitrage service for TWAMM

```
kip: 20
title: Extend an R&D grant to study a dedicated arbitrage service for TWAMM
author: 0x70626a
status: last-call
tags: none
created: 2022-03-30
replaced-by: none
replaces: none
```

## Proposal
Fund research and development of arbitrage facilities for on-chain liquidity pools, with immediate application to the time-weighted average market maker (TWAMM).

## Background
### About the team

AC and I are software developers with over 35 years of experience in FPGA tools (simulation, place & route, analysis), web technology, and building tooling for blockchain ecosystems.

We’ve built Web3 tooling and infrastructure products for our past startups, MakerDAO, Aave, Balancer, Uniswap, the Graph, and others.

We have been independently researching and developing TWAMM for the past 4+ months. See below our various monthly blog posts on TWAMM:

- [November 2021: infrastructure & testing exploration](https://mirror.xyz/0x70626a.eth/0uIph6x5knS_QRfG2mluFb-83P9NF1w01JQ-GNjCgVY)
- [Decemer 2021: sales rate research & simple arbitrage bots](https://mirror.xyz/0x70626a.eth/SIpA5Z4M6VYqCfvSKpTpRFw6bftE2ghi7fc7TA4c3LE)
- [January 2022: end-to-end TWAMM simulator featuring historical market data and transactions, arbitrage bots, simulated long-term swaps](https://mirror.xyz/0x70626a.eth/SzxME01JrrVRmu_H9q_07kZCBLzzHyxV_fmp1WmZvWo)
- [February 2022: gas optimization & TWAMM failure mode research](https://mirror.xyz/0x70626a.eth/yOP-PpK8pWE15SQ_Lte2srD_3lbqx89D5xFKfaVic8Y)
- [February 2022: in depth parameter and gas cost research](https://mirror.xyz/0slippage.eth/5zKJW4Zx9zYHpB4jNln16HuU8d8EtawmA17usNfIje4)

### About TWAMM

We’re building a new type of AMM purpose-built for time-insensitive trades that happen over multiple blocks. These trades can range from very large — think OTC trades for DAOs, Funds, whales, to small trades for retail (dollar-cost averaging).

As this is new and unexplored territory, there will be a heavy emphasis on research and development like optimal AMM designs, fee structures, gas optimizations, attack vectors, testing, and simulations. 

### Arbitrage and TWAMM

*TLDR; Prove TWAMM with KeeperDAO (MEV share + “right to first arbitrage”) is more profitable for LPs than Uniswap V2 fee structure.*

Arbitrageurs play a very important role to ensure the proper functionality of TWAMM and keeping the asset prices in the liquidity pools in line with the wider market. Unlike traditional AMMs, when there’s an active long-term swap, the cost to interact with the underlying AMM increases every block. See the section under inactivity in our last blog post for more information: [https://mirror.xyz/0slippage.eth/5zKJW4Zx9zYHpB4jNln16HuU8d8EtawmA17usNfIje4](https://mirror.xyz/0slippage.eth/5zKJW4Zx9zYHpB4jNln16HuU8d8EtawmA17usNfIje4)

When there are frequent arbitrages happening, traders get lower slippage and a significantly better return than trading on DEX aggregators for large swaps. Here’s how a pseudo-TWAMM performed vs 1Inch: [https://twitter.com/0xdramaone/status/1490397794452054018](https://twitter.com/0xdramaone/status/1490397794452054018). The arbitrage powered trade netted $5.4M vs $3.5M quoted by 1Inch, a +54% improvement!

Similar to Uniswap V2, we could build TWAMM with a flat fee and allow arbitrageurs in the free market to correct the prices and extract all the MEV. However, we’ve seen how that has adversely affected LPs in the long run — see [https://explore.flashbots.net/](https://explore.flashbots.net/). Uniswap V2 is the largest MEV leaker accounting for 64% of MEV extracting arbitrage trades, something that could have been avoided: [https://twitter.com/haydenzadams/status/1504543109396504577](https://twitter.com/haydenzadams/status/1504543109396504577)

TWAMM’s underlying AMM will allow LPs to passively deposit tokens similar to Uniswap V2 across the entire range from 0 → infinity. Additionally, we expect almost the entirety of the trade traffic on the underlying AMM to be from arbitrageurs. Therefore, we are interested in researching the advantages a system like KeeperDAO provides in order to add MEV protection for passive LPs: [https://twitter.com/hasufl/status/1504524010717077504](https://twitter.com/hasufl/status/1504524010717077504)

### About the research

This grant will focus on the delivery of methods for efficient arbitrage of TWAMM contracts, in collaboration with developers at KeeperDAO. Though focused on TWAMM, we expect that any findings will generalize to other types of AMM.

Research topics will include:

- Simulation and experimental measurement of arbitrage rates under different network conditions, fee regimes, liquidity conditions, and coordination scenarios.
- Investigation of static and dynamic liquidity fees and their impact on arbitrage rates TWAMM performance.
- Design considerations of integrating arbitrageurs with TWAMM, taking into account factors such as smart contract design, performance, trustlessness, security, and gas efficiency.

### About the grant

The grant is structured as a 3-month research and development investment, in the form of:

1. 200,000 USDC, streaming
2. 200 ROOK, on successful completion

These amounts are derived from the KeeperDAO Contributor Incentive Guidelines. We computed three months total compensation for two L4 engineers, then discounted it by 20%. We believe this is a fair balance between recognizing that we will not be full-time contributors for KeeperDAO, but that we will be building in concert with KeeperDAO engineers, and ultimately contributing potentially large amounts of value.

Receiving the majority of the value in stable coins will help us plan and cover living expenses and other operational costs more easily so that we can dedicate our full time to the development of TWAMM. It will also reduce the need to liquidate ROOK to cover those costs.

However because we also value long-term incentive alignment, we include a 200 ROOK completion bonus.

## Specification


1. 200,000 USDC and 200 ROOK from the DAO Treasury shall be set aside to fund the research and development of the TWAMM project.
    - 200,000 USDC from (1) shall be deposited into a Sablier stream ending June 28, 2022, claimable by an address controlled by the TWAMM project.
    - 200 ROOK from (1) shall be transferred to an address controlled by the TWAMM project on successful completion of the grant goals.
2. Research progress will be continually monitored by developers and a grant project manager from KeeperDAO to ensure adequate progress.
3. The grant project manager from KeeperDAO may terminate the grant at their discretion. Any unpaid funds at the time of termination shall be returned to the DAO Treasury.
