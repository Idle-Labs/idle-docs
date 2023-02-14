---
description: Developers > Best Yield > userAvgPrices
---

# userAvgPrices

This method gives the average price paid for $IDLE tokens of one specific user.

### Function

```solidity
function userAvgPrices(
    address _user
) external view returns (uint256 avgPrice);
```

### Parameters

| Parameter | Description             |
| --------- | ----------------------- |
| `_user`   | The address of the user |

### Return values

| Value      | Description                             |
| ---------- | --------------------------------------- |
| `avgPrice` | The average price paid for $IDLE tokens |
