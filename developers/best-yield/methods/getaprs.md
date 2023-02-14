---
description: Developers > Best Yield > getAPRs
---

# getAPRs

This method gives the actual (counting eventual fees) APR of every implemented lending protocol.

### Function

```solidity
function getAPRs(
) external view returns (address[] memory addresses, uint256[] memory aprs);
```

### Return values

| Value       | Description                                                      |
| ----------- | ---------------------------------------------------------------- |
| `addresses` | An array of interest-bearing token addresses                     |
| `aprs`      | An array of APRs (ordered with respect to the `addresses` array) |
