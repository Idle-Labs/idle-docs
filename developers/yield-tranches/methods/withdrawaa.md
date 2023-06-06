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

<table><thead><tr><th width="263">Parameter</th><th>Description</th></tr></thead><tbody><tr><td><code>_amount</code></td><td>Amount of AA tranche tokens to burn</td></tr></tbody></table>

### Return values

<table><thead><tr><th width="265">Value</th><th>Description</th></tr></thead><tbody><tr><td><code>_withdraw</code></td><td>Underlying tokens redeemed</td></tr></tbody></table>
