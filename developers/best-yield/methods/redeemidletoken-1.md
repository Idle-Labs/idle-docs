---
description: Developers > Best Yield > redeemIdleToken
---

# redeemIdleToken

With this method, users can redeem their underlying balance by burning Idle LP tokens. We calculate the pool share one can withdraw given the amount of Idle LP tokens they want to burn and redeem the corresponding underlying amount from each lending protocol currently used (if the unlent pool is not sufficient). We then send the underlying to the `msg.sender` .

With this call also governance tokens accrued by a user will be redeemed and sent to the user. This method can be called with `_amount` equal to 0 to redeem governance tokens only and maintain the position in Idle.&#x20;

### Function

```solidity
function redeemIdleToken(
    uint256 _amount
) external returns (uint256 redeemedTokens);
```

### **Parameters**

<table><thead><tr><th width="303">Parameter</th><th>Description</th></tr></thead><tbody><tr><td><code>_amount</code></td><td>The amount of Idle LP tokens to be burned</td></tr></tbody></table>

### **Return values**

<table><thead><tr><th width="307">Value</th><th>Description</th></tr></thead><tbody><tr><td><code>redeemedTokens</code></td><td>The amount of underlying tokens redeemed</td></tr></tbody></table>
