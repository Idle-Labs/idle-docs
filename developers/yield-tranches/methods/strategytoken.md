---
description: Developers > Yield Tranches > Methods > strategyToken
---

# strategyToken

This method returns the interest bearing asset of the yield source used in the specific IdleCDO (e.g. idleDAI, stETH, ...).

### Function

```solidity
function strategyToken(
) external view returns(address);
```

### Return values

<table><thead><tr><th width="266">Value</th><th>Description</th></tr></thead><tbody><tr><td><code>_val</code></td><td>Address of the strategy token which represent the position in the lending provider</td></tr></tbody></table>
