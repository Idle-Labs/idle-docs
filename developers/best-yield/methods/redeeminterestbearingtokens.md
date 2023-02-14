---
description: Developers > Best Yield > redeemInterestBearingTokens
---

# redeemInterestBearingTokens

This method calculates the pool share one can withdraw given the amount of $IDLE tokens he wants to burn and send interest-bearing tokens directly to the user. Underlying (e.g. DAI) is not redeemed here. This method can be called only in emergency situations when the contract is paused.

### Function

```solidity
function redeemInterestBearingTokens(
    uint256 _amount
) external;
```

### **Parameters**

| Parameter | Description                             |
| --------- | --------------------------------------- |
| `_amount` | The amount of $IDLE tokens to be burned |
