---
description: Developers > Yield Tranches > Methods > withdrawAA nonpayable
---

# withdrawAA

This method allows a user to burn a AA (Senior) tranche token and get the principal and interests back (if no emergency shutdown is in progress).

### Function

```solidity
function withdrawAA(
    uint256 _amount
) external returns (uint256)
```

### Parameters

| Parameter | Description                         |
| --------- | ----------------------------------- |
| `_amount` | Amount of AA tranche tokens to burn |

### Return values

| Value       | Description                |
| ----------- | -------------------------- |
| `_withdraw` | Underlying tokens redeemed |
