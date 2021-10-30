# KIP-5 Acquire CVX position

```
kip: 5
title: Acquire CVX position
author: Destroyr, 10delta, Curmudgeon, AlCappuccino, Yung Peso, Apeseason, Akin Sawyerr, Shahar, 2x, Cryptomessiah, DaddyMatty, Doge♜♜♜, spcxta, lapras, Pai-Sho, anon intern, pen, thereal
status: las-call
created: 2020-10-28
```

## Preface

### Proposal

Use a maximum of $40,000,000 of treasury funds to acquire a floor of one million [Convex ](https://etherscan.io/token/0x4e3fbd56cd56c3e72c1403e103b45db9da5b9d2b).

Use CVX stake for high Curve v2 Pool yield (when available).

Use CVX for yield, bribes, and potential coordination with other DAOs.

### Definitions

**Curve v2 Pool** refers to Curve 2 ROOK/Tricrypto (or ROOK/ETH, depending on the available base pair) pool, with gauged emissions.

## Abstract

Curve v1 is the most liquid stablecoin to stablecoin exchange in cryptocurrency. Their upcoming offerings related to Curve v2 (stable/BTC/ETH or ETH v2 Pools) offer a very enticing opportunity for ROOK to gain substantial liquidity, as these could form the basis of composite pools (e.g. ROOK/Tricrypto) in the same manner that the 3pool (USDC/USDT/DAI) forms the basis of composite pools with other stables (e.g. 3pool/MIM).

Furthermore, owning a substantial portion of voting weight within the protocol can not only drive very profitable emissions to the KeeperDAO protocol but also allow KeeperDAO to earn additional revenue through receiving substantial bribes from other protocols, which seek the same influence over the Curve protocol.

Convex offers an optimization that would allow KeeperDAO to aggressively gain more significant influence over the Curve protocol. This is because each vote-locked CVX token currently controls more than 7 vote-locked CRV tokens.

KeeperDAO has grown its treasury to over $100 million (non-ROOK NAV) - this would be a novel and profitable way to exercise its power.

In this proposal, we put forth the option of purchasing a significant stake in Convex through the acquisition of at least 1,000,000, and no more than 2,000,000 CVX tokens. We strive to accomplish this within the year. This purchase would not only allow the treasury to earn a significant yield on its position but would also let KeeperDAO function as a “Meta DAO” through exchanging its newly acquired votes for positions in other desired protocols governance tokens.

## Motivation

### Yield

- Bribe yield (acceptance of bribes)
- Inflationary yield (of CVX and CVXCRV)
- High yield (With bribes ~44%)
- Distribute bribes into the treasury

### ROOK pool

1. Create a Curve v2 Pool
2. Vote to ensure the pool has a significant gauge that is eligible for CRV rewards using our CRV voting power
3. Ensure an appropriate level of CRV emissions are directed to this gauge through voting power
4. Now people want to LP ROOK in the well-incentivized pool

### Inter-DAO coordination

- Using our voting power to help fellow DAOs to unlock shared value

## Implementation

A maximum of $40,000,000 from the DAO treasury will be used to acquire a CVX position, using a combination of USDC, DAI, ETH, and wETH, with a target minimum of 1,000,000 and a target maximum of 2,000,000 CVX, or a maximum average price of $40 per CVX.

The precise execution strategy is left opaque to minimize the risk of market speculation, front-running, et cetera. Upon completion, an update will be announced on Discord and Twitter with the full transaction details.

When roughly $25 million of CVX has been acquired, this will be communicated with the DAO and we will collectively decide if we would like to proceed. The same action will be taken, if and once the next benchmark of ~$32.5 million of CVX has been acquired.

### Asset Usage

The acquired CVX will be vote locked with Convex Finance for vlCVX. vlCVX will yield CVXCRV. This CVXCRV will be swapped for more CVX, which will be locked for vlCVX.

This initial strategy is subject to change at the discretion of the KeeperDAO core team with community involvement.

This position comes with no predetermined time horizon, but there is a 16-week lockup upon vote locking.

Initially, management of the position, including voting and token decisions, will be at the collaborative discretion of the KeeperDAO core team and the community, with execution being performed by the core team. This allows for agile response and risk management while leaving open the option for the future structure.

By default, bribe yield will be deposited to the KeeperDAO treasury but may be put to use if an applicable staking mechanism applies. Collaborative discretion of the KeeperDAO core team and the community can amend this.

## Risks

- This involves substantial use of DAO treasury funds, gaining exposure to a volatile and risky asset.
- Convex and Curve smart contracts have been audited, but still carry smart contract risk (see below).
- CVX price could move outside of our parameters before the acquisition is completed. In addition, this position incurs opportunity costs that may limit other potential uses of those funds or alternative strategies.

### Security reviews

- [Convex Review by Defisafety ](https://docs.defisafety.com/finished-reviews/convex-finance-process-quality-review), July 2021
- [Curve Review by Defisafety](https://docs.defisafety.com/v/0.6/finished-reviews/curve-finance-process-quality-audit), October 2020

## Appendix

[Notion Appendix ](https://keeperdao-labs.notion.site/Convex-Acquisition-Appendix-a9b5149cbb3b4cf297d25b0ea5958e2f)

## Specification

1. Purchase between 1 and 2 million CVX before the end of 2021
2. Establish a system to accept bribes for CVX vote
3. Establish Curve v2 Pool
4. Use 1,000 ROOK (from the DAO treasury) as bribes for voters for the gauge
