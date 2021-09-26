# KIP- Act IV Emissions Reduction

## Proposal
Reduce Act IV emissions for the Hiding Vault by 50%. 

## Background

Now that the Hiding Vault has been established as an enhanced lending protocol, both in TVL and total amount borrowed, I am proposing that we reduce the amount ROOK rewards.

* Hiding Vaults already receive significant benefits from Compound (interest and COMP distribution) and JITU (liquidity buffer). The ROOK rewards should be some (light) icing on the cake. 

* Hiding Vault rewards are not currently motivating users to take positions that create MEV. Until we are able to dynamically distribute rewards to different assets in an effort to dissuade same token supply and borrowing, the Hiding Vault will not be utilized to its full potential. 


My proposal is to reduce Hiding Vault Emissions by 50%, and not mint the excess ROOK. I would project that this decision will not significantly impact the usage of the Hiding Vault, due to the benefits described above. 

For reference, here is the current remaining emissions for Act IV: 

|Name|Percentage|# ROOK this Act|# ROOK per day|
|---|---|---|---|
|Hiding Vault|40|10395|231|
|Hiding Game|40|10395|231|
|Liquidity Pools|20|5197.5|115.5|
|Total|100|51975|577.5|

Assuming that this could go live right as the first half of Act IV's emissions that were minted ran out (https://etherscan.io/block/countdown/13318598), the final proposed ROOK rewards for Act IV's second half would be: 

|Name|Percentage|# ROOK Remaining |# ROOK per day|
|---|---|---|---|
|Hiding Game|40|10395|231|
|Hiding Vault|20|5197.5|115.5|
|Liquidity Pools|20|5197.5|115.5|
|Not Minted|20|5197.5|0|
|Total|100|25987.5|462|
 


## Specification

Before block 13318598, mint and distribute remaining Act IV rewards per the schedule below:
For Hiding Game rewards, mint 10395 ROOK and send to 0xc00ba24ebcb6fb4aecbe5b78431ea49d608f5565
For Hiding Vault rewards, mint 5197.5 ROOK and send to 0xae7b93a591c37ea37ed8bc7b6b999c85f2ed2405
Reduce per block rewards factor of Hiding Vaults by 50%

