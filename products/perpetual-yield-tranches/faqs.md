---
description: Products > Perpetual Yield Tranches > FAQs
---

# FAQs

<details>

<summary>What happens in the case of a default, hack to PYT funds?</summary>

Read the[ PYTs Edge Cases ](../../developers/perpetual-yield-tranches/edge-cases.md)section to learn more about default or hack scenarios and how they would be managed.

</details>

<details>

<summary>If a protocol is hacked wouldn't its underlying token be useless? How does Junior create value after an exploit?</summary>

If the attacker is able to completely drain a protocol, both Senior and Junior tranches would be affected. This event is extremely rare, as usually a hack is composed of recursive interactions that steal part of the funds. When the protocol itself is hacked, there are guardians that can pause the system and prevent further losses. Even if validators are directly hacked, it's unlikely that all the validators will suffer the same issue, just causing partial losses.

In this vision, Senior Tranche increases the security profile of the liquidity provider, adding an extra layer of protection: Junior Tranche deposits.

</details>

<details>

<summary>How is the liquidation managed in case of a default of an uncollateralized lending borrower?</summary>

PYTs would follow the [Clearpool default process](https://docs.clearpool.finance/clearpool/how-it-works/protocol/default) (insurance, auction) and then redistribute $USDC reimbursed to the Tranches token holders.

There can be 2 scenarios:

* Senior tranche is fully covered and Junior tranche redeems a portion of deposited assets: Senior LPs withdraw their entire deposit; Junior LPs will proportionally redeem their funds using a redistribution contract.&#x20;
* Senior tranche redeems a portion of deposited assets and no liquidity is left on Junior tranche: Senior LPs will proportionally redeem their funds using a redistribution contract.

In the case of borrower default on Clearpool, where the NAV does not decrease, the pausing process will be the following:

* on Clearpool itself, you cannot redeem because utilization rate is 100% and the pool is locked until auction.
* the PYTs is manually paused, but the underlying is already locked.
* once the USDC refund is processed by Clearpool, PYTs are unpaused (according to the 2 scenarios described above).

</details>

<details>

<summary>Is there a locking period when investing in PYTs?</summary>

There are **no locking periods or epochs** and users are free to enter and exit at any time. The interest earned (and governance tokens, after being partially sold in the market) will be split between the two classes using the [Adaptive Yield split](overview.md#adaptive-yield-split).

</details>

<details>

<summary>Is there any locking period for staking?</summary>

There is no lockup period for staking.

</details>

<details>

<summary>How is the APY of PYTs determined?</summary>

The base APY, before being split between tranches, is provided by the underlying strategy that takes into account the reinvestment of the accrued governance tokens (except for eventual IDLE rewards). The actual APY of each tranche class is determined by the ratio between the current underlying TVL of Senior and Junior tranches (i.e. APY = share of yield allocated to senior tranches/Senior TVL). The APY has to be considered net of fees.

</details>

<details>

<summary>How are fees collected?</summary>

Fees are collected at each harvest event. When the strategy auto-reinvest accrued tokens, the **Idle protocol charges a 10-15% performance fee** (see the [Fee structure](../fees.md#perpetual-yield-tranches) section).&#x20;

</details>

<details>

<summary>What are staking rewards?</summary>

To keep a good ratio between Senior and Junior tranches and a healthy APY, part of farmed governance tokens (e.g. IDLE) are redistributed to users who stake their tranche tokens in specific tranche rewards contracts.

</details>

<details>

<summary>Can I deposit and stake both on Senior and Junior Tranches?</summary>

You can always deposit in the Tranche of your preference. Staking is avaiable only in Senior tranches. Next to Senior tranches APYs you can over the ℹ️ and see the breakdown of the APR.

</details>

<details>

<summary>PYTs emergency pause is triggered manually or automatically?</summary>

As a general rule, the PYTs contracts automatically detect a NAV decrease and activate on-chain the pausing feature. No need for a DAO vote or multisig tx.

</details>

<details>

<summary>What is the difference between the APY and the realized APY shown in the dashboard?</summary>

The APY displayed is a spot gross return, while the realized APY is the average return, considering the time-based dependencies. \
\
The realized APY already counts the performance fee.

</details>



Need further help? Check our [guides](../../other/guides/) list or get in contact on [Discord](https://discord.com/invite/mpySAJp).
