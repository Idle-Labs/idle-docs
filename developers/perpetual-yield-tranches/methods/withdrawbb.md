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

<table><thead><tr><th width="283">Parameter</th><th>Description</th></tr></thead><tbody><tr><td><code>_amount</code></td><td>Amount of BB tranche tokens to burn</td></tr></tbody></table>

### Return values

<table><thead><tr><th width="288">Value</th><th>Description</th></tr></thead><tbody><tr><td><code>_withdraw</code></td><td>Underlying tokens redeemed</td></tr></tbody></table>
