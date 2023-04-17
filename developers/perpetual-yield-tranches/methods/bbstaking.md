---
description: Developers > Yield Tranches > Methods > BBStaking
---

# BBStaking

This method returns the address of the StakingRewards contract for BB (Junior) tranche staking.

### Function

```solidity
function BBStaking(
) external view returns(address);
```

### Return values

| Value          | Description                                                                                                                   |
| -------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| `address _val` | Address of the StakingRewards contract for BB tranche staking (can be address(0) which means that staking is disabled for BB) |
