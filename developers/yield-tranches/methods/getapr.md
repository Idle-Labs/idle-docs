---
description: Developers > Yield Tranches > Methods > getAPR
---

# getApr

This method returns the current apr for a tranche based on `trancheAPRSplitRatio` and the provided AA (Senior) ratio.

### Function

```solidity
function getApr(
    address _tranche
) external view returns (uint256);
```

### Parameters

<table><thead><tr><th width="276">Parameter</th><th>Description</th></tr></thead><tbody><tr><td><code>_tranche</code></td><td>AA or BB Tranche token address</td></tr></tbody></table>

### Return values

<table><thead><tr><th width="278">Value</th><th>Description</th></tr></thead><tbody><tr><td><code>_val</code></td><td>APR for the specific tranche</td></tr></tbody></table>
