---
description: Developers > Yield Tranches > Methods > AAstaking
---

# AAStaking

This method returns the address of the StakingRewards contract for AA (Senior) tranche staking.

### Function

```solidity
function AAStaking(
) external view returns(address);
```

### Return values

| Value          | Description                                                                                                                     |
| -------------- | ------------------------------------------------------------------------------------------------------------------------------- |
| `address _val` | Address of the StakingRewards contract for AA tranche staking (can be `address(0)` which means that staking is disabled for AA) |
