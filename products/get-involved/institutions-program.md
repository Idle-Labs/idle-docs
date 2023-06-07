---
description: Products > Institutions program
---

# Institutions program

<figure><img src="../../.gitbook/assets/Institutional.png" alt=""><figcaption></figcaption></figure>

The **Institutions program** is suited for liquidity providers that deposit in size, i.e. >$500k, into Idle's strategies. Any depositors that embed their wallet address can earn up to a <mark style="color:blue;">**50% profit share**</mark> from the contributed TVL.

{% hint style="info" %}
If you are interested in leveraging this program, we’d love to hear from you! \
Reach out to us by filling out the [Institutions program form](https://idlefinance.typeform.com/to/Bumd4UjV).
{% endhint %}

### Program details

Best Yield strategies and Yield Tranches are deployed on the Ethereum and the Polygon chain. The program is then available on both chains.&#x20;

The [Treasury League](../../governance/idle-dao/idle-leagues/treasury-league.md) periodically executes reward transfers, which will then be replaced by an automated on-chain fee-sharing mechanism.

{% tabs %}
{% tab title="Tiers" %}
These nine tiers of fee sharing apply to both the Ethereum and the Polygon Integration Partners programs.

<table><thead><tr><th data-type="number">Tier</th><th align="right">Partner's TVL</th><th align="right">Fee share</th></tr></thead><tbody><tr><td>1</td><td align="right">$1 - 5m</td><td align="right">10%</td></tr><tr><td>2</td><td align="right">$5 - 10m</td><td align="right">15%</td></tr><tr><td>3</td><td align="right">$10 - 50m</td><td align="right">20%</td></tr><tr><td>4</td><td align="right">$50 - 100m</td><td align="right">25%</td></tr><tr><td>5</td><td align="right">$100 - 200m</td><td align="right">30%</td></tr><tr><td>6</td><td align="right">$200 - 400m</td><td align="right">35%</td></tr><tr><td>7</td><td align="right">$400 - 700m</td><td align="right">40%</td></tr><tr><td>8</td><td align="right">$700m - 1b</td><td align="right">45%</td></tr><tr><td>9</td><td align="right">> $1b</td><td align="right">50%</td></tr></tbody></table>
{% endtab %}

{% tab title="Ethereum program" %}
The Ethereum program distributes the rewards on a monthly basis through a [vesting contract](https://legacy.idle.finance/#/tools/b2b-vesting-contract) available under the [Tool section of the legacy app](https://legacy.idle.finance/#/tools/b2b-vesting-contract). Tokens are vested on a linear basis over a 3-month period.&#x20;

The minimum threshold to distribute the rewards is 500 IDLE.

* Rewards: IDLE
* Frequency: monthly
* Distribution: [vesting contract](https://legacy.idle.finance/#/tools/b2b-vesting-contract) with a 3-month length

Integrators can use the following Dune dashboards to track the rewards of the program.

{% embed url="https://dune.com/idle.finance/ipp-ethereum" %}
{% endtab %}

{% tab title="Polygon program" %}
The Polygon program distributed rewards on a weekly basis to the partner's wallet address.

The minimum threshold to distribute the rewards is 100 MATIC.

* Rewards: MATIC
* Frequency: weekly
* Distribution: direct transfer to partner's wallet

Integrators can use the following Dune dashboards to track the rewards of the program.

{% embed url="https://dune.com/idle.finance/integration-partners-program-polygon" %}
{% endtab %}
{% endtabs %}

<details>

<summary>How to join to program</summary>

#### **Best Yield**

Please append your address in the Idle's pool URL as a referral during the deposit process `?_referral=ADDRESS` or use the function [`mintIdleToken`](../../developers/best-yield/methods/mintidletoken.md) adding as a `_referral` your address.&#x20;

_Example_ `app.idle.finance/#/earn/protected-yield/0x3eb6318b8d9f362a0e1d99f6032edb1c4c602500?_referral=ADDRESS`

#### **Yield Tranches**

Please append your address in the Idle's pool URL as a referral during the deposit process `?_referral=ADDRESS`  or use the functions [`depositAARef`](../../developers/yield-tranches/methods/depositaaref.md), [`depositBBRef`](../../developers/yield-tranches/methods/depositbbref.md) depending on your interest in depositing into the Senior (AA) or the Junior (BB) side.&#x20;

_Example_ `app.idle.finance/#/earn/protected-yield/0x3eb6318b8d9f362a0e1d99f6032edb1c4c602500?_referral=ADDRESS`

The [Best Yield](../../developers/best-yield/) and the [Yield Tranches](../../developers/yield-tranches/) sections under the Developers chapter provide more technical and detailed information regarding the strategies.

</details>

<details>

<summary>Benefits</summary>

Idle is a battle-tested protocol since 2019 with a strong focus on protocol safety and the continuous development of its products suite.

* Overperforming yields for a suite of assets
* High-security standards

</details>

<details>

<summary>FAQs</summary>

* **How do I earn fees?**\
  Include your wallet address as part of the deposit transaction data. More information regarding the input parameters of the deposit method can be found in the BY and YTs methods sections in the [Developers](broken-reference) chapter.
* **When do you share fees?**\
  Leagues process the IDLE distribution towards the vesting contracts on a monthly basis on Ethereum. The MATIC distribution on Polygon is done on a weekly basis.
* **Should I claim the tokens?**\
  The Ethereum fees should be claimed in the [vesting contract](https://legacy.idle.finance/#/tools/b2b-vesting-contract). The Polygon fees instead are sent to the referral address attached to deposits, no need to claim it.
* **Do I lose the rewards if I do not reach the minimum threshold?**\
  Accrued fees that do not reach the minimum threshold are recorded in Dune's dashboards. Once rewards reach the distribution threshold, the fee-sharing payments are executed.
* **How is the fee sharing calculated?**\
  Let's see a practical example: For the first 30 days the Partner's TVL deposited is $90m, enabling him to receive a 20% fee-share. Ten days after the first sharing event, its TVL is worth $200m and holds the same value for the remaining 20 days of the second month. The time-weighted TVL for this 30-day timeframe would then be worth $163M, letting him access Tier 2.&#x20;

</details>

