**KIP-24: Strategic Use of ETH for Yield Generation**

```
kip: 24
title: Strategic Use of ETH for Yield Generation
author: DaddyMatty <matt@rook.fi>, starfire <starryfire777@gmail.com>, Wes2 <wes@rook.fi>
status: review
tags: none
created: 2022-6-2
replaced-by: none
replaces: none
dependency: none
```

# Proposal

This document proposes that Rook DAO make its currently idle ETH holdings more productive by deploying a maximum of 75% of them across three liquid staking protocols for yield generation, using the methodology and process outlined below.

# References

1. [Rook treasury holdings](https://dune.com/0x_stubbs/Rook-Ecosystem)
2. [ETH2 liquid staking dashboard by @eliasimos](https://dune.xyz/eliasimos/Eth2-Liquid-Staking)
3. [Stakewise website](https://stakewise.io/)
4. [Rook research report on Stakewise](https://docs.google.com/document/d/1ImvNvrZq4pd2xsvosl8o_NjaeF1axIlPcUI8oofx7K8/edit#)
5. [sETH2/ETH2 liquidity, from Uniswap](https://info.uniswap.org/#/pools/0x7379e81228514a1d2a6cf7559203998e20598346)
6. [rETH2/sETH2 liquidity, from Uniswap](https://info.uniswap.org/#/pools/0xa9ffb27d36901f87f1d0f20773f7072e38c5bfba)
7. [Rocket Pool website](https://rocketpool.net/)
8. [Rook research report on Rocket Pool](https://docs.google.com/document/d/1TwQ_GvPOEd3sOHHt5abM5mt1RcrIpx5Q6taZq7en17U/edit#)
9. [rETH/wstETH liquidity on Curve](https://curve.fi/factory/89) (Factory 89)
10. [rETH/ETH on Uniswap](https://info.uniswap.org/#/pools/0xa4e0faa58465a2d369aa21b3e42d43374c6f9613)
11. [Lido website](https://lido.fi/)
12. [Rook research report on Lido](https://docs.google.com/document/d/189IeIuGHpVPmhowfrvcF66YSnRZp4AcwALuAcgYUSzs/edit#)
13. [stETH/ETH on Curve](https://curve.fi/steth)

# Background

As of June 1, 2022, Rook DAO holds a total of 10,537 ETH [1] that is currently not productive and not accruing additional yield. These holdings can be broken down as follows:

|Asset|Units|
| --- | --- |
|ETH|5,953|
|WETH|3,838|
|KWETH|787|
|Total|10,578|

This KIP proposes to deploy a maximum of 7,934 ETH, or 75% of Rook DAO's total ETH position as of June 1, 2022 across three liquid staking protocols: Stakewise, Rocket Pool and Lido. While the amounts will vary as the Official Team responds to market conditions, the baseline allocation derived from our modeling would be as follows:

|Protocol/Product|Max Amount (Units)|% of Total|
| --- | --- | --- |
|Stakewise|3,137|39.54%|
|Rocket Pool|2,768|34.88%|
|Lido|2,030|25.58%|
|Total|7,934|100%|

This baseline allocation between the selected investments is based on a scorecard methodology developed by the Official Team that weighed key attributes and KPI’s of these protocols in relation to one another. Critical factors that materially impacted our proposed allocations to these assets were:

* Stakewise has agreed to provide an advance on 50% of one year’s staking fee, or 5% of the earnings on staked ETH, in SWISE tokens upon staking funds. Assuming RD stakes 3,317 ETH at an average staking yield of 8%, this would result in an additional $22.5k in net revenues. 
* Rocket Pool is the newest platform and therefore is the least battle tested.
* Lido is the dominant provider of liquid ETH staking, with a roughly 90% market share as of June 1, 2022. [2] While the protocol scored well enough in our research to merit an allocation in this proposal, we also believe that both Rook's treasury and the broader Ethereum ecosystem would benefit from limiting this level of concentration. This led us to propose slightly larger exposures to the other two protocols relative to Lido.

# Official Team

This proposal was developed by the following members of Rook DAO.

* DaddyMatty - Labs Treasury Specialist
* Starfire - DeFi Analyst
* Stubbs - Treasury Analyst
* Wes2 - Moderator
* Breeze - Moderator

This proposal establishes these same members as the Official Team responsible for the execution and monitoring of the staking investments articulated in this proposal, subject to oversight by and reporting to the Rook DAO as established below.

# Investment Analysis

The analysis supporting this proposal proceeded through two stages: analysis of individual protocols, and the development of a scorecard-based allocation to each. We describe each of these further below.

## Protocol Analysis

The Official Team evaluated the liquid staking landscape using a combination of metrics and sourcing: Trustlessness/Concentration, Tokenomics, Security/risks, and Composability/Liquidity. These metrics gave context to the different trade-offs between liquid staking providers and allowed the team to discern the protocols aligned with Rook’s best interests. The analysis presented below represents a summary of the main takeaways from our research. For more analysis, see the protocol-specific research reports at [4], [8], [12], and below.

Note: All figures in the remainder of this section are as of June 1, 2022.

### Stakewise [3]

The following summarizes the findings of Rook’s original research on Stakewise, available at [4].

### Tokennomics

* Current APR is 4.04% [3]
* Current fee is 10% [3]
* Dual token model where sETH2 represents users’ initial staking deposits and rETH2 that represents accrued rewards.
  * Pro: dual token model ensures rewards do not get diluted
  * Con: demand and liquidity are required for two tokens instead of one. Users have to manually swap rETH2 → sETH2 in order to compound rewards.

### Trustlessness/Concentration

* Permissioned validator onboarding process requiring node operators to apply and be vetted by the Stakewise DAO.
* Open-source deployment package provided by Stakewise

### Composability

* Low composability right now, but Stakewise is exploring launching sETH2/stETH curve pool.
* Integrated with Babylon Finance

### Liquidity

* ETH/sETH2 (Uniswap) - TVL $99.5m [5]
* rETH2/sETH2 (Uniswap) - TVL $14.79m [6]

### Rocket Pool [7]

The following summarizes the findings of Rook’s original research on Rocket Pool, available at [8].

### Tokennomics

* Current APR is 4.03%. [7]
* Current fee is 15% [7]
* Rocket Pool issues rETH to represent staked Ether deposits on the Beacon Chain. Instead of a rebasing mechanism Rocket Pool increases the rETH/ETH exchange rate to account for accrued staking rewards. Rewards are realized simultaneously.
  * Pro: rewards are realized instantaneously
* Rocket Pool requires node operators to stake a minimum of 10% RPL (Rocket Pool’s native token) in the value of ETH they are staking. This serves as collateralization in the event the node operator gets slashed.

### Trustlessness/Concentration

* Permissionless node onboarding process mitigated by the RPL collateralization requirement

### Composability

* rETH is integrated with Curve, Yearn and Alchemix.

### Liquidity

* rETH/wstETH (Curve) - TVL $35.46m [9]
* rETH/ETH (Uniswap) - TVL $3.24m [10]

### Lido [11]

The following summarizes the findings of Rook’s original research on Lido, available at [12].

### Tokennomics

* Current APR is 4.00% [11]
* Current fee: 10% [11]
* Single token model, stETH, with daily rebasing.
  * Pro: rewards are realized instantaneously
  * Con: pool dilutes at the expense of late participants given it consists of interest bearing ETH deposits and non-interest bearing staking rewards

### Trustlessness/Concentration

* Permissioned node operator application process
  * Plans to decentralize this process through distributed validator technology
* Protocol is controlled by the Lido DAO through LDO governance token
  * Checks and balances such as quorum and timelocks for proposals being introduced

### Composability

* Highly composable and integrated with protocols such as [AAVE](https://app.aave.com/reserve-overview/?underlyingAsset=0xae7ab96520de3a18e5e111b5eaab095312d7fe84&marketName=proto_mainnet), [Curve](https://curve.fi/steth), [Ribbon Finance](https://app.ribbon.finance/v2/theta-vault/T-stETH-C), and [Yearn](https://yearn.finance/#/vault/0xdCD90C7f6324cfa40d7169ef80b12031770B4325)

### Liquidity

* stETH/ETH (Curve) - TVL $1.8b [13]

## Allocation Methodology

To determine the allocations to the selected investments, the Official Team used a scorecard methodology to weigh each of the protocols’ key attributes and KPI’s in relation to one another. The team used following attributes in this analysis:

Trustlessness & Asset Concentration

* Decentralization - Is the protocol fully permissionless? What is the structure of the DAO? How are node operators onboarded?
* ETH Concentration - What is the protocol’s commitment to client diversity? Is the protocol committed to maintaining the decentralization of Ethereum?
* Node Count - How many individual node operators has the protocol onboarded? What client is the node operator running?

Tokenomics

* APR - What is the annual percentage return for staking?
* Reward Asset - How are the accrued rewards paid out? Does the protocol use a single token model or a dual token model? Is the reward pool socialized?
* Fee - What is the fee on accrued rewards?
* Inflation - Does the token reward model introduce elements of inflation at the expense of stakers?

Security & Risk

* Audits Performed - How many audits has the protocol received? Are the audit firms reputable?
* Bug Bounties Offered - Are there any bounties the protocol has offered to the public in order to incentivize individuals to find bugs?
* Length of Operation - How long has the protocol offered liquid staking?
* Slashing Insurance - Does the liquid staking service offer native protection for slashing penalties?

Composability & Liquidity

* Total Value Locked in Liquidity Pools - What are the main venues for trading the liquid staking derivative? Is there sufficient liquidity for Rook DAO to exit the position?
* Additional Yield Opportunities - Is the liquid staking derivative integrated in protocols across the DeFi space? Are there additional opportunities for Rook DAO to increase the yield of the position?

### Scoring and Allocations

Using the attributes referenced above, we then determined a weighting scale that reflected our assessment of the relevant importance of each attribute. We then scored each option on each attribute and weighted its total score as a percent of the grand total to establish a recommended allocation of funds.

|Max Score|Attribute|Rocket Pool|Lido|Stakewise|
| --- | --- | --- | --- | --- |
|35|Trustlessness/Concentration|35|5|25|
|30|Tokenomics|20|15|30|
|20|Security/Risks|15|20|20|
|15|Composability/Liquidity|5|15|10|
||Total Score|75|55|85|
||Allocation Weight|34.88%|25.58%|39.53%|


Mechanistically following the scorecard’s output would translate into the following allocations of ETH: 

|Protocol/Product|Max Amount (ETH)|% of Total Staked|
| --- | --- | --- |
|Stakewise|3,137|39.54%|
|Rocket Pool|2,768|34.88%|
|Lido|2,030|25.58%|
|Total|7,934|100%|

While these recommendations will remain a primary input into allocation decisions by the Official Team, the volatility of the current market landscape in general - and the current situation around stETH in particular - necessitates some flexibility to adapt to changes. Because of this, these amounts represent a baseline allocation between the 3 protocols; the Official Team can choose to change these allocations to take advantage of changes to key criteria used to monitor these positions.

## Financial Analysis

### Expected Return

Based on a total initial, maximum investment of 7,934 ETH and assuming stable APYs and an average ETH price of $1,800, Rook DAO can expect to earn $575,028 or 319.46 ETH in the first year with the allocations above. The schedule below presents the anticipated rewards by protocol/product:

|Protocol/ Product|APY*|Annual Reward (Units)|Additional Incentives|
| --- | --- | --- | --- |
|Stakewise|4.04%|126.73 ETH|5% SWISE Incentive|
|Rocket Pool|4.03%|111.53 ETH|None|
|Lido|4.00%|81.2 ETH|None|
|Total||319.46 ETH|5% SWISE Incentive|

*APYs listed here is as of June 1, 2022 [4][8][12]

Factors that may impact these forecasted returns include:

* Changes to ETH’s price
* Changes to APYs of staking protocols
* Total ETH market volume and conditions
* Adverse movements in SWISE price
* Number of active stakers
* Timing of the merge to POS ETH
* Changes to staking and ETH protocol tokenomics

In addition to the yield gained from the staked assets, Stakewise has agreed to provide half of RD’s anticipated staking fees for one year (or 5% of the earnings of the ETH Rook DAO stakes on their platform)  in SWISE tokens upon staking funds. Assuming Rook DAO stakes 3,317 ETH at an average staking yield of 8%, this would result in an additional $22.5k in net revenues upon staking of funds. Although Stakewise has not relayed any lockup period for these funds, the Official Team recommends that Rook DAO through this proposal commit to not selling any SWISE tokens for 120 days after staking with Stakewise to establish good faith with the Stakewise community. Assuming prices remain consistent for both the SWISE incentives and the ETH earned, this would bring the total expected income from these investments to $597,528. 


Note: it is expected that yield derived from staking ETH will significantly improve post-merge. These yields are expected to be anywhere between 8-15%. Because the timing of the merge to PoS ETH is unknown we have excluded these returns from this analysis.

### Risks

As with all investments, the benefits earned come with numerous risks that are both financial and non-financial in nature. These risks should be assessed by the Official Team in conjunction with the potential returns and would include:

* Smart contract risk
* Protocol business risk
* Market conditions and directional asset exposure
* Opportunity cost
* Execution risk during Ethereum’s transition from PoW to PoS
* Protocol concentration

Protocol concentration risk will be managed in light of the established maximums from the allocation process.

## Execution and Management

### Implementation

Actual execution to deploy these funds will be performed by the Treasury Multisig (0x9a67f1940164d0318612b497e8e6038f902a00a4). The treasury will make its best effort to deploy these funds within 120 days of adoption of this proposal, consistent with its ongoing commitment to minimizing the risk of market speculation and front-running Upon completion, an update will be announced on Discord and Twitter with the full transaction details.

### Position Maintenance and Unwinding

Full management of the positions will be at the collaborative discretion of the Rook Labs and the Official Team as outlined above, with execution being performed by the Treasury Multisig. While management of the position will be at the discretion of the Official Team, this team will communicate current results and planned actions on a weekly basis. Additionally, a dune dashboard monitoring these investments in real time. This allows for agile response and risk management while also continuing to minimize the speculative and front-running risks described above.

Review: The liquid staking assets will be subject to a formal review and analysis 90 days after full deployment has been completed. The goal of this review is to assess the productivity of the positions and communicate the findings to the DAO.

Exiting the Position: This proposal imposes no timeframes on when and how to unwind the position. Full management of the position will be at the collaborative discretion of the Rook DAO Labs and the Official Team involved in drafting the KIP.

# Specification

* Stake 7,934 ETH into Stakewise, Rocket Pool and Lido in amounts described above
* Treasury Multisig (0x9a67f1940164d0318612b497e8e6038f902a00a4) to deploy assets and make best effort to do so within 120 days of adoption
* Official team to report weekly to community along with real-time dashboard
