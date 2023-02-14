---
description: Developers > Perpetual Yield Tranches > Methods > depositBBnonpayable
---

# depositBB

This method transfer `token` from the user to the contract and mint BB (Junior) tranche tokens for the user.

`msg.sender` should approve this contract first to spend `_amount` of `token`

### Function

```solidity
function depositBB(
    uint256 _amount
) external returns (uint256)
```

### Parameters

| Parameter | Description                  |
| --------- | ---------------------------- |
| `_amount` | Amount of `token` to deposit |

### Return values

| Value  | Description              |
| ------ | ------------------------ |
| `_val` | BB tranche tokens minted |
