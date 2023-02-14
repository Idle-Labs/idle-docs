---
description: Developers > Perpetual Yield Tranches > Methods > getAPR
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

| Parameter  | Description                    |
| ---------- | ------------------------------ |
| `_tranche` | AA or BB Tranche token address |

### Return values

| Value  | Description                  |
| ------ | ---------------------------- |
| `_val` | APR for the specific tranche |
