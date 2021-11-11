# KIP-9 Act V Emissions Balance (Effective 11/14)

```
kip: 9
title: Act V Emissions Balance (Effective 11/14)
author: lapras <lapras@keeperdao.com>
status: draft
created: 2020-11-02
```

## Proposal
Update emissions to reflect taper schedule and account for trading (Hiding Game) focus

## Background

Upon the passing of KIP-2 and KIP-4, we have seen a decrease in Hiding Vault emissions and an increase in demand for the ROOK token. For those unfamiliar, KeeperDAO emissions are generally set to decrease every Act by ~30%. At this current time, with KIP-2 having passed, we are already emitting 30% less than planned.

Accordingly, I believe we should emit the same amount of ROOK as we do today (and was anticipated for Act V, before KIP-2). This is 404.25 ROOK per day. This is 38808 ROOK for the whole epoch (~96 days, depending on block speed).

---

### KIP-2 Context
The key tenants of KIP-2, from @whatsthedeetz, were:

* Hiding Vaults already receive significant benefits from Compound (interest and COMP distribution) and JITU (liquidity buffer). The ROOK rewards should be some (light) icing on the cake. 

* Hiding Vault rewards are not currently motivating users to take positions that create MEV. Until we are able to dynamically distribute rewards to different assets in an effort to dissuade same token supply and borrowing, the Hiding Vault will not be utilized to its full potential. 

### KIP-4 Context
With the passing of KIP-4, we also turn Hiding Game emissions into buy pressure with the beneath flywheel:

Emission Value -> Volume -> Revenue -> Buy back -> Higher ROOK price -> Higher Emission Value

### Buy Back (Continuation)

We would continue with buy backs until the release of the Coordination Game, as outlined in KIP-4.

Overall, we will see about 30% more emissions (than today) go towards the Hiding Game, which we know correlates to volume.

### Allocation
Accordingly, I propose the following be default emissions for Act V:

|Name|Percentage|# ROOK |# ROOK per day|
|---|---|---|---|
|Hiding Game|70|27165.6|282.975|
|Liquidity Pools|20|7761.6|80.85|
|Hiding Vault|10|3880.8|40.425|
|Total|100|38808|404.25|

I propose these emissions be minted in 102528 block (~16 day) increments. This means every 102528 blocks, 6468 ROOK would be minted as outlined above. This will change with the release of the Coordination Game.

### KIPnd Key Blocks

**Act IV ends:** [Block 13617668](https://etherscan.io/block/countdown/13617668)
**Second mint:** [Block 13720196](https://etherscan.io/block/countdown/13720196)
**Third mint:** [Block 13822724](https://etherscan.io/block/countdown/13822724)
**Fourth mint:**  [Block 13925252](https://etherscan.io/block/countdown/13925252)
**Fifth mint:** [Block 14027780](https://etherscan.io/block/countdown/14027780)
**Sixth (final) mint:** [Block 14130308](https://etherscan.io/block/countdown/14130308)
**Act V ends:** [Block 14232836](https://etherscan.io/block/countdown/14232836)

---

## Specification

1. For the duration of Act V, every 102528 blocks we will emit 6468 ROOK for users of the protocol (consistent with planned emission rate before KIP-2).
2. This ROOK will be distributed with a ratio of 70% to the Hiding Game, 20% to Liquidity Pools, and 10% to Hiding Vault borrowers.
3. Continue KIP-4 Buy back and burns with 100% of net revenue
