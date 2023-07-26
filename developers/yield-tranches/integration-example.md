---
description: Developers > Yield Tranches > Integration example
---

# Integration example

## Routing Contract

One way for external protocols to integrate Yield Tranches is to create a Routing Contract around the [`IdleCDO`](https://github.com/Idle-Labs/idle-tranches/blob/master/contracts/IdleCDO.sol) contracts.

{% hint style="info" %}
Integrators use a routing contract to keep track of users' deposits in Yield Tranches originally made through their platforms.
{% endhint %}

### How it works

1. Users deposit funds into the Routing Contract
2. The Routing contract moves funds deposited into the [`IdleCDO`](https://github.com/Idle-Labs/idle-tranches/blob/master/contracts/IdleCDO.sol) contracts on behalf of users
3. IdleCDO contract issues `IdleCDO_AA_StrategyName` (if Senior tranche) or `IdleCDO_BB_StrategyName` (if Junior tranche) tokens to users

### Example

An example of a Routing contract used by [ShapeShift](https://shapeshift.com/) to integrate Best Yield and Yield Tranches, with related tests, is available [on GitHub](https://github.com/shapeshift/idle-router).

### Integrators program

Protocols deploying funds into the Yield Tranches are eligible to join the [Integrators program](../../products/get-involved/integrators-program.md).
