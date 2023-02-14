---
description: Developers > Perpetual Yield Tranches > Methods > strategyToken
---

# strategyToken

This method returns the interest bearing asset of the yield source used in the specific IdleCDO (e.g. idleDAI, stETH, ...).

### Function

```solidity
function strategyToken(
) external view returns(address);
```

### Return values

| Value  | Description                                                                        |
| ------ | ---------------------------------------------------------------------------------- |
| `_val` | Address of the strategy token which represent the position in the lending provider |
