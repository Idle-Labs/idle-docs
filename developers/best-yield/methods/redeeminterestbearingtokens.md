---
description: Developers > Best Yield > redeemInterestBearingTokens
---

# redeemInterestBearingTokens

{% hint style="info" %}
This method can be called only in emergency situations when the BY contract is paused.
{% endhint %}

This method calculates the pool share one user can withdraw given the amount of idleTokens (idleDAI, idleUSDC, idleUSD, ...) he wants to burn and send interest-bearing tokens (aTokens from Aave, cTokens from Compound, ...) directly to the user's wallet alongside his share of unlent underlying (e.g. DAI) present in the vault.

### Function

```solidity
function redeemInterestBearingTokens(
    uint256 _amount
) external;
```

### **Parameters**

| Parameter | Description                           |
| --------- | ------------------------------------- |
| `_amount` | The amount of idleTokens to be burned |
