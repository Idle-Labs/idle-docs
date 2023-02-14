---
description: Other > FAQs
---

# FAQs

On this page, we summarize all the FAQs included in our documentation split by category.

## [Best Yield](../products/best-yield/faqs.md)

<details>

<summary>How can BY strategy provide higher returns than other options?</summary>

The algorithm is programmed to analyze the supply rate functions across integrated protocols and total funds in the pool, and it's able to constantly rebalance capital across any number of protocols to **earn the highest interest rate possible** with very high precision.

</details>

<details>

<summary><strong>How is the BY APY calculated in each pool?</strong></summary>

The displayed APY is the aggregated interest rate of the APYs coming from multiple lending providers, depending on the allocated funds and the governance tokens from the underlying protocols.

</details>

<details>

<summary><strong>When a BY rebalance is triggered?</strong></summary>

Several factors can trigger a rebalance. Factors related to network conditions/congestion, and if a new allocation exceeds the previous one by a significant percentage. Hence, the timing is variable.

In general, a rebalance happens every 3 hours on Ethereum and hourly on Polygon.

</details>

<details>

<summary><strong>Can I add more funds if I already deposited assets?</strong></summary>

Yes, any user who has already deposited funds within one or more pools can add additional funds to the current deposited assets.&#x20;

Each addition of new funds always requires a confirmation and signature via smart contract, and therefore require to pay the related network fees (not controlled or received by Idle in any case).

</details>

<details>

<summary><strong>Are there any protocol fees related to BY?</strong></summary>

Idle currently sets a 10% fee when deposited funds are withdrawn. For more information on Idle's fees, please visit the dedicated [Fees section](../products/fees.md)

</details>

## [Perpetual Yield Tranches](../products/perpetual-yield-tranches/faqs.md)

<details>

<summary>What happens in the case of a default, hack to PYT funds?</summary>

Read the[ PYTs Edge Cases ](../developers/perpetual-yield-tranches/edge-cases.md)section to learn more about default or hack scenarios and how they would be managed.

</details>

<details>

<summary>If a protocol is hacked wouldn't its underlying token be useless? How does Junior create value after an exploit?</summary>

If the attacker is able to completely drain a protocol, both Senior and Junior tranches would be affected. This event is extremely rare, as usually a hack is composed of recursive interactions that steal part of the funds. When the protocol itself is hacked, there are guardians that can pause the system and prevent further losses. Even if validators are directly hacked, it's unlikely that all the validators will suffer the same issue, just causing partial losses.

In this vision, Senior Tranche increases the security profile of the liquidity provider, adding an extra layer of protection: Junior Tranche deposits.

</details>

<details>

<summary>Is there a locking period when investing in PYT?</summary>

There are **no locking periods or epochs** and users are free to enter and exit at any time. The interest earned (and governance tokens, after being partially sold in the market) will be split between the two classes according to a predefined ratio called _trancheAPRSplitRatio_ (e.g. 10% interest to Senior tranche holders and 90% to Junior tranche).

</details>

<details>

<summary>Is there any locking period for staking?</summary>

There is no lockup period for staking.

</details>

<details>

<summary>How is the APY of PYT determined?</summary>

The base APY, before being split between tranches, is provided by the underlying strategy that takes into account the reinvestment of the accrued governance tokens (except for eventual IDLE rewards). The actual APY of each tranche class is determined by the ratio between the current underlying TVL of Senior and Junior tranches (i.e. APY = share of yield allocated to senior tranches/Senior TVL). The APY has to be considered net of fees.&#x20;

For more info [view the readme](https://github.com/Idle-Labs/idle-tranches#idle-dynamic-tranches) on GitHub.

</details>

<details>

<summary>How are fees collected?</summary>

Fees are collected at each harvest event. When the strategy auto-reinvest accrued tokens, the **Idle protocol charges a 10% performance fee**. Revenues get routed to the _FeeCollector_ address.

</details>

<details>

<summary>What are staking rewards?</summary>

To keep a good ratio between Senior and Junior tranches and a healthy APY, part of farmed governance tokens (e.g. IDLE) are redistributed to users who stake their tranche tokens in specific tranche rewards contracts.

</details>

<details>

<summary>Can I deposit and stake both on Senior and Junior Tranches?</summary>

You can always deposit in the Tranche of your preference. Staking is available only in Senior tranches. Next to Senior tranches APYs you can over the ℹ️ and see the breakdown of the APR.

</details>

## [Integration Partners programs](faqs.md#integration-partners-programs)

### [Ethereum](../products/integration-partners-program/faqs.md)

<details>

<summary>How do I earn fees?</summary>

Include your wallet address as part of the deposit transaction data. More information regarding the input parameters of the deposit method can be found in the BY [Methods](../developers/best-yield/methods/) section in the [Protocols](broken-reference) chapter.

</details>

<details>

<summary>When do you share fee payments on Ethereum?</summary>

Leagues process the $IDLE payments towards the vesting contracts weekly.\
\
The minimum threshold to execute the fee-sharing is 500 $IDLE.

</details>

<details>

<summary><strong>Do I lose the rewards if I do not reach the minimum threshold?</strong></summary>

Accrued shared fees that do not reach the minimum threshold are recorded in the dashboard until their sum is higher than 500 $IDLE. Once rewards reach that threshold, the fee-sharing payment is executed.

</details>

<details>

<summary>How do I claim fees through the vesting contracts?</summary>

The Treasury League deploys a vesting contract for each partner. Deployment is executed when the first payment is processed. The same contract will receive the following payments and only the referral address is entitled to redeem the vested tokens. Tokens are vested on a linear basis over a 3-month period and the partner can claim them anytime.

</details>

<details>

<summary>How is my reward tier calculated?</summary>

Your tier is calculated as the average Partner Deposited Asset (PDA) value between the first deposit and the first payment. When the fee-sharing transaction is executed, the tier is then calculated in the timeframe between that day and the next payment.\
You can check some helpful examples [here](../products/integration-partners-program/overview.md#fee-sharing-examples).

</details>

### [<mark style="color:purple;">Polygon</mark>](broken-reference)<mark style="color:purple;"></mark>

<details>

<summary>How do I earn the Performance Boost bonus?</summary>

Include your wallet address as part of the deposit transaction data. More information regarding the input parameters of the deposit method can be found in the BY [Methods](../developers/best-yield/methods/) section in the [Protocols](broken-reference) chapter.

</details>

<details>

<summary>When do I get <strong>the Polygon rewards</strong> payments?</summary>

$MATIC rewards are processed on a weekly basis.

</details>

<details>

<summary>Do I lose the rewards if I do not reach the minimum threshold?</summary>

Accrued bonuses that do not reach the minimum threshold are recorded in the dashboard until their sum is higher than 100 $MATIC. Once rewards reach the threshold, the bonus payment is executed.

</details>

<details>

<summary>Should I claim the bonus?</summary>

The Treasury League sends the bonus to the referral address attached to deposits, no need to claim it.

</details>

<details>

<summary>How do I track Polygon bonuses?</summary>

You can track the $MATIC rewards on the dedicated Polygon [Dune Analytics](https://dune.xyz/queries/210529) dashboard.

</details>

## [Idle DAO](../governance/idle-dao/faqs.md)

<details>

<summary>What is an IIP?</summary>

IIP, as explained in the docs [Glossary](golossary.md), stands for the _Idle Improvement Proposal_ and represents a proposal for a protocol change that needs to go through $IDLE token holders' on-chain vote.

</details>

<details>

<summary>Who can vote on-chain?</summary>

Every user that holds $IDLE can vote, but to get the eligibility before voting they must [self-delegate or delegate](https://gov.idle.finance/t/guide-how-to-delegate) to others their voting rights.

</details>

<details>

<summary>Who can submit an on-chain proposal?</summary>

Every address with at least 130,000 $IDLE delegated can submit on-chain proposals. \
At any stage, the proposal can be cancelled by its creator or if he/she loses the required delegated votes.

</details>

<details>

<summary>When a proposal is executed on-chain?</summary>

The quorum to execute any change on the protocol is 520,000 $IDLE and an IIP is executed if the majority (50% +1) of the voters cast a “_For_” vote.

</details>

### [Gauges](../governance/idle-staking/gauges/faqs.md)

<details>

<summary><strong>What are gauge weights?</strong></summary>

Gauge weights account how much $IDLE will be received by a liquidity gauge.

</details>

<details>

<summary><strong>Who can vote for gauge weights?</strong></summary>

Only users who stake/lock their $IDLE (i.e. stkIDLE holders) have access to gauge weight voting.

</details>

<details>

<summary><strong>When do gauges' weights change?</strong></summary>

Gauges’ weights change once a week, every Thursday (\~12:00 AM UTC).

</details>

<details>

<summary>How often can users change their weight preferences?</summary>

Users can change their weights once every 10 days. The 10-days window is counted since their last voting preference submission.

</details>

<details>

<summary>Do I need to re-submit my weight vote every week?</summary>

Users don't have to vote again every week except if they want to change their vote distribution.

</details>

<details>

<summary>What if I provide liquidity in multiple pools? </summary>

Your voting power applies to all gauges but may produce different boosts based on how much liquidity you are providing and how much total liquidity the PYT pool has.

</details>



Need further help? Check our [guides](guides/) list or get in contact on [Discord](https://discord.com/invite/mpySAJp).
