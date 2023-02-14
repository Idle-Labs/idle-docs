---
description: Developers > Perpetual Yield Tranches > Integration example
---

# Integration example

## Routing Contract

One way for external protocols to integrate Perpetual Yield Tranches is to create a Routing Contract around the [`IdleCDO`](https://github.com/Idle-Labs/idle-tranches/blob/master/contracts/IdleCDO.sol) contracts.

{% hint style="info" %}
Integrators use a routing contract to keep track of users' deposits in Perpetual Yield Tranches originally made through their platforms.
{% endhint %}

### How it works

1. Users deposit funds into the Routing Contract
2. The Routing contract moves funds deposited into the [`IdleCDO`](https://github.com/Idle-Labs/idle-tranches/blob/master/contracts/IdleCDO.sol) contracts on behalf of users
3. IdleCDO contract issues `IdleCDO_AA_StrategyName` (if Senior tranche) or `IdleCDO_BB_StrategyName` (if Junior tranche) tokens to users

### Example

An example of a Routing contract used by ShapeShift to integrate Best Yield and Perpetual Yield Tranches, with related tests, is available [on Github](https://github.com/shapeshift/idle-router).

### Integration Partners program

Protocols deploying funds into the Perpetual Yield Tranches are eligible to join the [Integration Partners program](../../products/integration-partners-program/).
