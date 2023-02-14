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

| Value          | Description                                                                      |
| -------------- | -------------------------------------------------------------------------------- |
| `_allocations` | array with lending protocols allocations. Sum is always equal to `100000` (100%) |
