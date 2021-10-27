# KIP-2 Act IV Emissions Reduction
```
kip: 2
use: none
author: whatsthedeetz <whatsthedeetz@keeperdao.com>
status: last-call
created: 2021-09-24
```
## Preface

### Proposal
This proposal aims to reduce daily ROOK emissions to the Hiding Vaults by 75% through the end of Act IV.

### Background

Now that the Hiding Vault has been established as an enhanced lending protocol, both in total value locked (TVL) and total amount borrowed, I proposing that we reduce the amount of ROOK that is emitted to users of the Hiding Vault.

* Hiding Vaults already receive significant benefits from Compound (interest and COMP distribution) and JITU (liquidity buffer). The ROOK rewards should be some (light) icing on the cake. 

* Hiding Vault rewards are not currently motivating users to take positions that create MEV. Until we are able to dynamically distribute rewards to different assets in an effort to dissuade same token supply and borrowing, the Hiding Vault will not be utilized to its full potential. 

For reference, here is the current remaining emissions for the last quarter of Act IV: 

|Name|Percentage|# ROOK this Act|# ROOK per day|
|---|---|---|---|
|Hiding Vault|40|5197.5|231| 
|Hiding Game|40|5197.5|231|
|Liquidity Pools|20|2598.75|115.5| 
|Total|100|12993.75|577.5|

Note: Hiding Game and LP emissions have been fully minted for Act IV and cannot be adjusted until the beginning of Act V.

Assuming that this could go live right as the third quarter of Act IV's emissions for Hiding Vault that were minted run out, the final proposed ROOK rewards for Act IV's final quarter would be: 

|Name|Percentage|# ROOK Remaining |# ROOK per day|
|---|---|---|---|
|Hiding Game|40|5197.5|231|
|Hiding Vault|10|1299.375|57.75|
|Liquidity Pools|20|2598.75|115.5|
|Not Minted|30|3898.125|0|
|Total|100|12993.75|404.25|

## Specification

Before block 13468133:
 1. Mint 1299.375 ROOK
 2. Transfer the minted ROOK to the Hiding Vault distributor contract [0xae7b93a591c37ea37ed8bc7b6b999c85f2ed2405](https://etherscan.io/address/0xae7b93a591c37ea37ed8bc7b6b999c85f2ed2405).
 3. Reduce the per-block reward factor for Hiding Vaults by 75%.

