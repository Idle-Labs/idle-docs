---
description: Developers > Yield Tranches > Edge cases
---

# Edge cases

In this section, we explain the Yield Tranches (YTs) risk situations, whether they are managed and covered automatically, and what the procedure is case by case.

### What if the underlying protocols’ contracts are hacked?&#x20;

Each YT contract (called `IdleCDO`) has an underlying token managed (e.g. DAI) and an associated interest-bearing asset (e.g. `idleDAI`) which is used through a specific strategy.

{% hint style="warning" %}
If the interest-bearing asset price decreases over time, this means that the underlying related protocol (accessed through a “strategy”) is hacked, and the YTs contract is automatically "paused", thus no redeems or deposits are allowed until the Idle governance reactivates those selectively (first for the Senior tranches).
{% endhint %}

### What if the YTs contract is hacked?&#x20;

If the YTs contract is hacked, there are no automatic triggers to block subsequent deposits and redeems. Nevertheless, the contract owner (currently the Idle Dev League multisig) or the Guardian can still pause the contract.

{% hint style="warning" %}
If the contract is manually paused or, in general, if Idle suffers an attack that is not automatically managed, and there are any funds left, those will get distributed to Senior holders first.
{% endhint %}

### Up to which amount are the Senior Tranches covered?&#x20;

Senior Tranches are first in line to be repaid in case of default, while Junior holders have a second lien or no lien at all in case of fund losses.&#x20;

The loss for Senior Tranches is covered by the Junior TVL.

> Let's imagine having $100m deposited in Senior Tranches and $400m deposited in Junior Tranches, for a total of $500m of the pool. In a hacking scenario, Senior tranches will be covered up to $400m (namely the Junior TVL) of losses; this means having coverage of 400% of the funds deposited in Senior and up to 80% coverage of pool hacks.

{% hint style="warning" %}
If a hack occurs, full protection for Senior Tranches happens only if there will be enough funds deposited in the Junior tranche to cover the hack.
{% endhint %}
