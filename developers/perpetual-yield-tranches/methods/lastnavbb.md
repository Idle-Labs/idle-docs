---
description: Developers > Yield Tranches > Methods > lastNAVBB
---

# lastNAVBB

This method returns the last saved net asset value (TVL) for BB (Junior) tranches only.

### Function

```solidity
function lastNAVBB(
) external view returns(uint256);
```

### Return values

| Value  | Description                                             |
| ------ | ------------------------------------------------------- |
| `_val` | last saved net asset value (in `token`) for BB tranches |
