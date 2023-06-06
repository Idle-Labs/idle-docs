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

<table><thead><tr><th width="265">Value</th><th>Description</th></tr></thead><tbody><tr><td><code>addresses</code></td><td>An array of interest-bearing token addresses</td></tr><tr><td><code>aprs</code></td><td>An array of APRs (ordered with respect to the <code>addresses</code> array)</td></tr></tbody></table>
