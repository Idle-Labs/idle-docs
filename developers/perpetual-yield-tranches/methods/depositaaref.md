---
description: Developers > Yield Tranches > Methods > depositAARef
---

# depositAARef

This method transfers `token` from the user to the contract and mint AA (Senior) tranche tokens for the user. It gives also the possibility to add a referral address.&#x20;

`msg.sender` should approve this contract first to spend `_amount` of `token`

### Function

```solidity
function depositAARef(
    uint256 _amount
    address _referral
) external returns (uint256)
```

### Parameters

| Parameter   | Description                  |
| ----------- | ---------------------------- |
| `_amount`   | Amount of `token` to deposit |
| `_referral` | Referral address             |

### Return values

| Value  | Description              |
| ------ | ------------------------ |
| `_val` | AA tranche tokens minted |
