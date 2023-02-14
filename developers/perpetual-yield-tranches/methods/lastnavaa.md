---
description: Developers > Perpetual Yield Tranches > Methods > lastNAVAA
---

# lastNAVAA

This method returns the last saved net asset value (TVL) for AA (Senior) tranches only.

### Function

```solidity
function lastNAVAA(
) external view returns(uint256);
```

### Return values

| Value  | Description                                             |
| ------ | ------------------------------------------------------- |
| `_val` | last saved net asset value (in `token`) for AA tranches |
