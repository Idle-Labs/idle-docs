---
description: Governance > Idle DAO > $IDLE token
---

# $IDLE token

<figure><img src="../../.gitbook/assets/IDLE.png" alt=""><figcaption></figcaption></figure>

The Idle protocol is governed and upgraded by $IDLE token-holders, using three distinct components:&#x20;

1. $IDLE token:[`0x875773784Af8135eA0ef43b5a374AaD105c5D39e`](https://etherscan.io/address/0x875773784Af8135eA0ef43b5a374AaD105c5D39e)``
2. Governance contract (Governor Bravo):[`0x3D5Fc645320be0A085A32885F078F7121e5E5375`](https://etherscan.io/address/0x3D5Fc645320be0A085A32885F078F7121e5E5375)``
3. Timelock contract:[`0xD6dABBc2b275114a2366555d6C481EF08FDC2556`](https://etherscan.io/address/0xD6dABBc2b275114a2366555d6C481EF08FDC2556#code)``

{% hint style="info" %}
Together, these contracts allow the community to propose, vote and implement changes to the contracts owned by the _Timelock_. The ownership of _idleTokens_ from BY strategies, _idleCDO_ from PYTs, and the _IdleController_ contracts have been all transferred to the _Timelock_ contract.

The _Timelock_ contract can modify system parameters, logic, and contracts in a 'time-delayed, opt-out' upgrade pattern, as reported here [\[1\]](../../developers/best-yield/security-management-policy.md), [\[2\]](../../developers/perpetual-yield-tranches/security-management-policy.md).
{% endhint %}

When a proposal is created, the community can submit their votes during a _3-day voting period_.\
If a majority and at least 520,000 (4% of the total supply) votes are cast for the proposal, it is queued in the Timelock and can be implemented after 2 days.
