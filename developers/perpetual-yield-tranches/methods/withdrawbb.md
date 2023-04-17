---
description: Developers > Yield Tranches > Methods > withdrawBB
---

# withdrawBB

This method allows a user to burn a BB (Junior) tranche token and get the principal and interests back (if no emergency shutdown is in progress).

### Function

```solidity
function withdrawBB(
    uint256 _amount
) external returns (uint256)
```

### Parameters

| Parameter | Description                         |
| --------- | ----------------------------------- |
| `_amount` | Amount of BB tranche tokens to burn |

### Return values

| Value       | Description                |
| ----------- | -------------------------- |
| `_withdraw` | Underlying tokens redeemed |
