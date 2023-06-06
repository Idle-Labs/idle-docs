---
description: Developers > Best Yield > getAllocations
---

# getAllocations

This method returns an array with the last allocations in lending protocols (100% = `100000`)

### Function

```solidity
function getAllocations(
) external view returns (uint256[] memory);
```

### Return values

<table><thead><tr><th width="312">Value</th><th>Description</th></tr></thead><tbody><tr><td><code>_allocations</code></td><td>array with lending protocols allocations. Sum is always equal to <code>100000</code> (100%)</td></tr></tbody></table>
