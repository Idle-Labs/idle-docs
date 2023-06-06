---
description: Developers > Yield Tranches > Methods > trancheAPRSplitRatio
---

# trancheAPRSplitRatio

This method returns the set interest split ratio between the Senior and Junior holders.

### Function

```solidity
function trancheAPRSplitRatio(
) external view returns(uint256);
```

### Return values

<table><thead><tr><th width="276">Value</th><th>Description</th></tr></thead><tbody><tr><td><code>_val</code></td><td>Percentage of interest that will go to AA tranche holders (where 100% is <code>100000</code>)</td></tr></tbody></table>
