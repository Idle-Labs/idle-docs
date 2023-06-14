---
description: Products > Integrators program
---

# Integrators program

<figure><img src="../../.gitbook/assets/Integrators.png" alt=""><figcaption></figcaption></figure>

The **Integrators program** allows DeFi protocols to efficiently integrate the Idle product suite into their own services and workflow. Any partners that integrate Idle products can earn up to a <mark style="color:blue;">**50% profit share**</mark> from the contributed TVL originating from dApps, wallets, or payment gateways.

{% hint style="info" %}
If you are interested in partnering with us, we’d love to hear from you! \
Please reach out to us by filling out the [Integrator program form](https://idlefinance.typeform.com/to/PUC7nO).
{% endhint %}

### Programs details

Best Yield strategies and Yield Tranches are deployed on the Ethereum and on the Polygon chain. The program is then available on both chains.&#x20;

The [Treasury League](../../governance/idle-dao/idle-leagues/treasury-league.md) periodically execute reward transfers, which will then be replaced by an automated on-chain fee-sharing mechanism.

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

<summary>How to integrate</summary>

As an integrator partner, the methods you should look for are

#### **Best Yield**

* [<mark style="color:blue;">`mintIdleToken`</mark>](../../developers/best-yield/methods/mintidletoken.md) method, where you should add the Ethereum or Polygon <mark style="color:blue;">`_referral`</mark> address

#### **Yield Tranches**

* [`depositAARef`](../../developers/yield-tranches/methods/depositaaref.md) or [`depositBBRef`](../../developers/yield-tranches/methods/depositbbref.md) methods depending on which side of the tranche you want to integrate, Senior (AA) or Junior (BB).&#x20;

The [Best Yield](../../developers/best-yield/) and the [Yield Tranches](../../developers/yield-tranches/) sections under the Developers chapter provide more technical and detailed information regarding the strategies.

</details>

<details>

<summary>Benefits</summary>

Idle is a battle-tested protocol since 2019 with a strong focus on protocol safety and the continuous development of its products suite. Starting a partnership with Idle would bring to the partner value, a solid reputation from the DeFi industry and would open the door to effortless financial autonomy opportunities.

**Best Yield**

* Get access to a seamless yield generation from multiple underlying sources with just one integration
* Optimize capital allocation in the best-performing strategies
* Deposit single-sided assets, with no impermanent loss
* Save money, with Idle subsidizing rebalance's fees
* Save time, with Idle taking care of underlying codebase upgrades

**Yield Tranches**

* Get access to risk-adjusted profiles to accommodate a wider audience, introducing coverage features and yield boosts
* Simplify integration, as Idle strategies are compatible with the ERC-4626 standard
* Increase returns thanks to periodic compounding
* Do not lock your users' funds, as YTs have no locking periods or epochs

</details>

<details>

<summary>Current integrators</summary>

Multiple partners have integrated either the Best Yield strategies or the Yield Tranches. \
A list of current on-top integrators follows.

**Best Yield**

* [ShapeShift](https://shapeshift.com/)
* [Spool](https://www.spool.fi/)
* [Enzyme](https://enzyme.finance/)
* [Yearn](https://yearn.finance/)
* [Harvest](https://harvest.finance/)
* [Balancer](https://balancer.fi/)

**Yield Tranches**

* [ShapeShift](https://shapeshift.com/)
* [Swissborg](https://swissborg.com/)
* [Spool](https://www.spool.fi/)
* [Harvest](https://harvest.finance/)
* [Sense](https://sense.finance/)
* [Clearpool](https://clearpool.finance/)

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

