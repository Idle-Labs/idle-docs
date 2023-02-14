---
description: Developers > Perpetual Yield Tranches > Methods > depositAA
---

# depositAA

This method transfers `token` from the user to the contract and mint AA (Senior) tranche tokens for the user.

`msg.sender` should approve this contract first to spend `_amount` of `token`

### Function

```solidity
function depositAA(
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
| `_val` | AA tranche tokens minted |
