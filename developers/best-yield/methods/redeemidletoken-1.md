---
description: Developers > Best Yield > redeemIdleToken
---

# redeemIdleToken

With this method, users can redeem their underlying balance by burning $IDLE tokens. We calculate the pool share one can withdraw given the amount of $IDLE tokens they want to burn and redeem the corresponding underlying amount from each lending protocol currently used (if the unlent pool is not sufficient). We then send the underlying to the `msg.sender` .

With this call also governance tokens accrued by a user will be redeemed and sent to the user. This method can be called with `_amount` equal to 0 in order to redeem governance tokens only and maintain the position in Idle.&#x20;

### Function

```solidity
function redeemIdleToken(
    uint256 _amount
) external returns (uint256 redeemedTokens);
```

### **Parameters**

| Parameter | Description                             |
| --------- | --------------------------------------- |
| `_amount` | The amount of $IDLE tokens to be burned |

### **Return values**

| Value            | Description                              |
| ---------------- | ---------------------------------------- |
| `redeemedTokens` | The amount of underlying tokens redeemed |
