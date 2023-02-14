---
description: Developers > Perpetual Yield Tranches > Methods > trancheAPRSplitRatio
---

# trancheAPRSplitRatio

This method returns the set interest split ratio between the Senior and Junior holders.

### Function

```solidity
function trancheAPRSplitRatio(
) external view returns(uint256);
```

### Return values

| Value  | Description                                                                        |
| ------ | ---------------------------------------------------------------------------------- |
| `_val` | Percentage of interest that will go to AA tranche holders (where 100% is `100000`) |
