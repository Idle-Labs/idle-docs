---
description: Developers > Yield Tranches > Methods > depositAA
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

<table><thead><tr><th width="303">Parameter</th><th>Description</th></tr></thead><tbody><tr><td><code>_amount</code></td><td>Amount of <code>token</code> to deposit</td></tr></tbody></table>

### Return values

<table><thead><tr><th width="307">Value</th><th>Description</th></tr></thead><tbody><tr><td><code>_val</code></td><td>AA tranche tokens minted</td></tr></tbody></table>
