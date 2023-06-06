---
description: Developers > Best Yield > tokenPriceWithFee
---

# tokenPriceWithFee

This method returns $IDLE token price for a specific user considering fees, in underlying. This is useful when you need to redeem exactly X amount of underlying tokens.

### Function

```solidity
function tokenPriceWithFee(
    address _user
) external view returns (uint256 priceWFee);
```

### Parameters

<table><thead><tr><th width="292">Parameter</th><th>Description</th></tr></thead><tbody><tr><td><code>_user</code></td><td>The address of the user</td></tr></tbody></table>

### Return values

<table><thead><tr><th width="302">Value</th><th>Description</th></tr></thead><tbody><tr><td><code>priceWFee</code></td><td>The $IDLE token price with fees</td></tr></tbody></table>
