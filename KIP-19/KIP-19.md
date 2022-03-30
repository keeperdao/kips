
```
kip: 19
title: Sunset the Liquidity Pools product
author: YungPeso
status: last-call
tags: none
created: 2022-03-09
replaced-by: none
replaces: none
```

## Proposal 
Sunset the KeeperDAO Liquidity Pools by ending ROOK emissions and providing a timeline for withdrawal of DAO Treasury deposits.

## Background 
The Liquidity Pools are a waste of our treasury, they dilute the token while adding no revenue and the upcoming trading protocol upgrade removes the need for flash loan pools as user funds are used for MEV capture. Given this, it no longer makes sense for us to dedicate resources to its maintenance as more is gained from sunsetting the product and reallocating the deposited funds to more directly align with KeeperDAO's long-term vision.

As it stands, we have ~48 million dollars worth of assets deposited to the liquidity pools. A summary is given below.

Asset | Amount | Today's Value
----- | ------ | -------------
kETH  | 4,615.85 | $12,532,032.75
kwETH | 4,604.02 | $12,499,914.30
kDAI | 12,741,904.44 | $12,741,904.44
kBTC | 134.803 | $5,648,245.70
kUSDC | 4,369,935.23 | $4,369,935.23
Total |           | $47,792,032.42

According to the core team, the amount of liquidity required for flash loans is approximately $5M of each asset. As this is already covered by existing DAO Treasury deposits, we propose to cease ROOK emissions for liquidity providers, and allow excess DAO Treasury funds deposited in the pools to be withdrawn, while leaving at least the required amount of assets in each pool to provide effective flash loan liquidity. When the trading protocol upgrade is live, the entirety of deposited DAO Treasury funds can be withdrawn, and we may declare the liquidity pools obsolete.

## Specification 
1. Mint an amount of ROOK to cover LP emissions for the period between the end of Act V and the block in which this KIP is ratified.
2. Notify all LP users of a scheduled phase-out of the LP.
3. Emit no further ROOK to LPs after the emissions minted in (1) are exhausted.
4. Maintain, for 1 year, a UI that will allow users to withdraw their capital from the Liquidity Pools. After that, provide instructions for users to call the LP smart contracts directly.
5. Make a best effort to maintain in the pools only sufficient liquidity to cover flash loan needs (estimated to be approximately $5M worth of assets in each pool at present) until the pools become obsolete.
