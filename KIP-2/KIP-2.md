# KIP-2 Act IV Emissions Reduction

```
kip: 2 
author: WhatsTheDeetz <whatsthedeetz@keeperdao.com>
status: draft 
created: 2021-09-24
```

## Proposal
Reduce Act IV (second half) emissions for the Hiding Vault by 50%. 

## Background

Now that the Hiding Vault has been established as an enhanced lending protocol, both in TVL and total amount borrowed, I am proposing that we reduce the amount of ROOK rewards.

- Hiding Vault users already receive significant benefits from the underlying Compound position (both interest and COMP token distribution), and also enjoy the functional value-add of the JITU system (liquidity buffer, MEV-safe liquidation).

- Hiding Vault rewards are not currently motivating users to take positions that create MEV. Until we are able to dynamically distribute rewards to different assets in an effort to dissuade same token supply and borrowing, the Hiding Vault will not be utilized to its full potential. 

- Act IV emissions were divided into two "halves," with the second half remaining un-minted. This is what allows us to adjust the second half emissions. The first half of Act IV emissions will end at block 13318598 (https://etherscan.io/block/countdown/13318598).

In light of these facts, I suggest that the current ROOK incentive being offered is excessive and propose that Hiding Vault emissions be reduced to 50% of their current level during the second half of Act IV. I would project that this decision will not significantly impact the usage of the Hiding Vault, due to the existing benefits described above.

Left unaltered, the second half of Act IV emissions will break down as follows:

|Name|Percentage|# ROOK minted at block 13318598|# ROOK emitted per day|
|---|---|---|---|
|Hiding Vault|40|10395|231|
|Hiding Game|40|10395|231|
|Liquidity Pools|20|5197.5|115.5|
|**Total**|**100**|**25987.5**|**577.5**|

If this proposal is adopted, the second half of Act IV emissions will instead break down as follows:

|Name|Percentage|# ROOK minted at block 13318598|# ROOK emitted per day|
|---|---|---|---|
|Hiding Game|50|10395|231|
|Hiding Vault|25|5197.5|115.5|
|Liquidity Pools|25|5197.5|115.5|
|**Total**|**100**|**20790**|**462**|

## Specification

Before block 13318598, when the second half of Act IV emissions are scheduled to begin:

- Mint 10395 ROOK and transfer it to the Hiding Game distributor at 0xc00ba24ebcb6fb4aecbe5b78431ea49d608f5565.
- Mint 5197.5 ROOK and transfer it to the Hiding Vault distributor at 0xae7b93a591c37ea37ed8bc7b6b999c85f2ed2405.
- FIXME: Do we need to mint the rewards for the Liquidity Pools also?
