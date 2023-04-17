---
description: Developers > Yield Tranches > Methods > getIncentiveTokens
---

# getIncentiveTokens

This method returns an array of tokens used to incentive tranches via `IdleCDOTrancheRewards`.

### Function

```solidity
function getIncentiveTokens(
) external view returns (address[] memory)
```

### Return values

| Value             | Description                                            |
| ----------------- | ------------------------------------------------------ |
| `incentiveTokens` | Array with addresses of incentiveTokens (can be empty) |
