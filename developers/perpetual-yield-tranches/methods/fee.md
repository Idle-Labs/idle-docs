---
description: Developers > Perpetual Yield Tranches > Methods > fee
---

# fee

This method returns the Performance fee.

### Function

```solidity
function fee(
) external view returns(uint256);
```

### Return values

| Value  | Description                                                          |
| ------ | -------------------------------------------------------------------- |
| `_val` | The performance fee (relative to FULL\_ALLOC where 100% is `100000`) |
