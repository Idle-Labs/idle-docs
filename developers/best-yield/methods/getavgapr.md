---
description: Developers > Best Yield > getAvgApr
---

# getAvgApr

This method gives the base layer aggregated APR of $IDLE token. This method does not take into account fees, unlent percentage and additional APR given by $IDLE governance token.

### Function

```solidity
function getAvgAPR(
) external view returns (uint256 avgApr);
```

### Return values

| Value    | Description                      |
| -------- | -------------------------------- |
| `avgApr` | The average APR for $IDLE tokens |
