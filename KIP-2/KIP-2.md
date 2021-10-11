# KIP- Act IV Emissions Reduction

## Proposal
Reduce remaining Act IV daily emissions for the Hiding Vault by 50% or 75%. 

## Background

Now that the Hiding Vault has been established as an enhanced lending protocol, both in TVL and total amount borrowed, I am proposing that we reduce the amount ROOK rewards.

* Hiding Vaults already receive significant benefits from Compound (interest and COMP distribution) and JITU (liquidity buffer). The ROOK rewards should be some (light) icing on the cake. 

* Hiding Vault rewards are not currently motivating users to take positions that create MEV. Until we are able to dynamically distribute rewards to different assets in an effort to dissuade same token supply and borrowing, the Hiding Vault will not be utilized to its full potential. 


My proposal is to reduce current daily Hiding Vault Emissions by 50% or 75%, and not mint the excess ROOK. I would project that this decision will not significantly impact the usage of the Hiding Vault, due to the benefits described above. 

For reference, here is the current remaining emissions for the last quarter of Act IV: 

|Name|Percentage|# ROOK this Act|# ROOK per day|
|---|---|---|---|
|Hiding Vault|40|5197.5|231| 
|Hiding Game|40|5197.5|231|
|Liquidity Pools|20|2598.75|115.5| 
|Total|100|12993.75|577.5|
(note: Hiding Game and LP emissions have been fully minted for Act IV)

Assuming that this could go live right as the third quarter of Act IV's emissions for HV that were minted run out, the final proposed ROOK rewards for Act IV's final quarter would be: 

Option 1, 50% HV emissions cut:

|Name|Percentage|# ROOK Remaining |# ROOK per day|
|---|---|---|---|
|Hiding Game|40|5197.5|231|
|Hiding Vault|20|2598.75|115.5|
|Liquidity Pools|20|2598.75|115.5|
|Not Minted|20|2598.75|0|
|Total|100|12993.75|462|

Option 2, 75% HV emissions cut:

|Name|Percentage|# ROOK Remaining |# ROOK per day|
|---|---|---|---|
|Hiding Game|40|5197.5|231|
|Hiding Vault|10|1299.375|57.75|
|Liquidity Pools|20|2598.75|115.5|
|Not Minted|30|3898.125|0|
|Total|100|12993.75|462|

## Specification

(to be completed once the poll above receives sufficient votes)
Before block ____, mint and distribute remaining Act IV rewards per the schedule below:
Hiding Vault rewards, mint _____ ROOK and send to 0xae7b93a591c37ea37ed8bc7b6b999c85f2ed2405
Reduce per block rewards factor of Hiding Vaults by 50%

---
