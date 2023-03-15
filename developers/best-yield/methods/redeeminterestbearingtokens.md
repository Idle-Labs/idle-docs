---
description: Developers > Best Yield > redeemInterestBearingTokens
---

# redeemInterestBearingTokens

This method calculates the pool share one can withdraw given the amount of idleTokens (idleDAI/idleUSDC/idleUSDT/idleWETH/...) it wants to burn and send interest-bearing tokens (aTokens from Aave, cTokens from Compound, ...) directly to the user. The underlying (e.g. DAI) is not redeemed here. This method can be called only in emergency situations when the contract is paused.

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
