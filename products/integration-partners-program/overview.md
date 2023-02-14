---
description: Integration Partners program > Overview
---

# Overview

This program is an opportunity to join the Idle ecosystem and receive a part of protocol fees for deposits that originate from your dApp, wallet, or payment gateway.

Best Yield strategies and Perpetual Yield Tranches are deployed on the Ethereum and on the Polygon chain.

{% hint style="info" %}
Partners can join the program anytime, and receive **up to 50%** of the generated fees by embedding their referral wallet into deposits routed via their product.
{% endhint %}

### Programs details

Integrators will receive a share of the generated fees, based on the TVL brought in.

The [Treasury League](../../governance/idle-dao/idle-leagues/treasury-league.md) periodically execute reward transfers, which will then be replaced by an automated on-chain fee-sharing mechanism.

{% tabs %}
{% tab title="Ethereum program" %}
The Ethereum program distributes the rewards on a monthly basis through a [vesting contract](https://legacy.idle.finance/#/tools/b2b-vesting-contract). Tokens are vested on a linear basis over a 3-month period.&#x20;

The minimum threshold to distribute the rewards is 500 IDLE.

* Rewards: IDLE
* Frequency: monthly
* Distribution: [vesting contract](https://legacy.idle.finance/#/tools/b2b-vesting-contract) with a 3-month length
{% endtab %}

{% tab title="Polygon program" %}
The Polygon program distributed rewards on a weekly basis to the partner's wallet address.

The minimum threshold to distribute the rewards is 100 MATIC.

* Rewards: MATIC
* Frequency: weekly
* Distribution: direct transfer to partner's wallet
{% endtab %}
{% endtabs %}

<figure><img src="../../.gitbook/assets/image (24).png" alt=""><figcaption><p>Tiers overview</p></figcaption></figure>

Integrators can use the dedicated Dune dashboards to track the rewards of the program on Ethereum and Polygon.&#x20;

{% embed url="https://dune.com/idle.finance/ipp-ethereum" %}

{% embed url="https://dune.com/idle.finance/integration-partners-program-polygon" %}

### Examples

**Example 1**: For the first 30 days the Partner's TVL deposited is $90m, enabling him to receive a 20% fee-share. Ten days after the first sharing event, its TVL is worth $200m and holds the same value for the remaining 20 days of the second month. The time-weighted TVL for this 30-day timeframe would then be worth $163M, letting him access the Tier 2

$$
{\small Time\ weighted}\ TVL_{Partner} = \frac{(\$90m*10\ days +\$200m*20\ days)}{30\ days}= \$163m \\
$$

**Example 2**: Partners' users deposit $2m in the first 28 days. On the 29th day, a $350m deposit is executed. The month's PDA is $25m, and the partner receives 20% of the fees. If that liquidity level remains the same, the partner will be ranked in Tier 3 in the next month

$$
{\small Time\ weighted}\ TVL_{Partner} = \frac{(\$2m*28\ days +\$350m*2\ days)}{30\ days}= \$25m \\
$$
