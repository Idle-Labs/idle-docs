---
description: Governance > IDLE staking > Gauges
---

# Gauges

{% hint style="info" %}
In [January 2023](https://gov.idle.finance/t/idle-incentives-distribution-update-2/1104), the DAO decided to pause the IDLE distribution to Gauges.
{% endhint %}

The gauge voting system allows stkIDLE holders to control IDLE emissions that go through gauges. In other words, by voting for a specific gauge, stkIDLE holders increase the amount of IDLE tokens sent to the related staking contract with respect to the others.&#x20;

IDLE rewards distributed via Gauges are initially routed to the **Senior Tranche** of the [Perpetual Yield Tranches](../../../products/yield-tranches/).

This system strongly favours LPs who continually lock their rewards into stkIDLE to increase their pool's gauge weight. Fundamentally, this allows stkIDLE holders, who are the most long-term users of the protocol, to have complete control over the future $IDLE emission for Gauges.

The Idle liquidity gauge measures how much a user is providing liquidity to PYTs. Each PYT pool has its own liquidity gauge where users can stake their LPs tokens.&#x20;

{% hint style="info" %}
Users can also [boost](./#farming-boost) their balance in the liquidity gauge by locking their $IDLE, seeing their individual rewards enhanced.
{% endhint %}

## Gauge weight voting

Gauges weights are updated weekly, every Thursday at \~12:00 AM UTC. After that moment, the IDLE distribution for Gauges is updated based on the votes and will stay constant for 1 week.

stkIDLE holders can allocate their voting power to the available gauges to balance the IDLE rewards distribution.&#x20;

When a user applies a new weight vote, it gets applied at the start of the next epoch week. The weight vote for any gauge cannot be changed more often than once in 10 days. Users don't have to vote again every week except if they want to change their vote distribution.

## $IDLE distribution rate to Gauges

The Idle protocol is distributing IDLE to Perpetual Yield Tranches (PYT) via the `Controller` contract. The overall [IDLE emission rate](../../idle/distribution.md) stays at 3,300 IDLE per day (including both BY and PYT reward programs).

{% hint style="warning" %}
Currently, the **Senior class of** [**PYTs**](../../../products/yield-tranches/) is eligible to receive gauge incentives.
{% endhint %}

{% hint style="info" %}
**Gauges distribution:** 30% of the IDLE allocated to the liquidity mining program will be moved into Gauges for 6 months, resulting in a **990 $IDLE/day** distribution over the next semester.
{% endhint %}

## **Voter Extractable Value (**VEV)

Anyone who stakes/locks IDLE can allocate his stkIDLE towards one or more liquidity gauges. Thanks to this, there are even more benefits in addition to the APY that can be seen by simply locking IDLE via single staking.

stkIDLE holders can vote to direct more IDLE to their respective gauge and get an extra reward on top of the staking APY by earning yield through receiving bribes to vote to direct IDLE to a specific gauge.

{% hint style="info" %}
Thanks to VEV, protocols interested in having more weight in their liquidity gauge (higher distribution of IDLE reward in that specific gauge) will be able to incentivize stkIDLE holders to vote for the protocol's pool.
{% endhint %}

## **Gauges ownership and permissions**

The ownership of the Gauges contracts can be summarized as follows:

* The [`GaugeProxy`](../../../developers/gauges/deployed-contracts.md#gauges-system) and [`GaugeController`](../../../developers/gauges/deployed-contracts.md#gauges-system) contracts are owned by the Treasury League multisig.
* The `LiquidityGauge` contract is owned by the `GaugeProxy` contract. Initially was owned by the Development League multisig during the gauges guarded launch. This change will let new PYTs partners adhere to the [gauges whitelisting framework](broken-reference) and launch IIPs to add their PYTs pools to the $IDLE Gauges system.
* The [`MultiRewards` contracts](../../../developers/gauges/deployed-contracts.md#multirewards) are owned by the Treasury League multisig letting TL distribute additional rewards on top of the IDLE emission coming from Gauges.
* The [`Distributor`](../../../developers/gauges/deployed-contracts.md#gauges-system) contract is owned by the `Timelock` contract, i.e. the IDLE token holders.
