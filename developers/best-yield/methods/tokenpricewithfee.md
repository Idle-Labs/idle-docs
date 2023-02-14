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

| Parameter | Description             |
| --------- | ----------------------- |
| `_user`   | The address of the user |

### Return values

| Value       | Description                     |
| ----------- | ------------------------------- |
| `priceWFee` | The $IDLE token price with fees |
