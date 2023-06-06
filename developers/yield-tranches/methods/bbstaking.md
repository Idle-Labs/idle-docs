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

<table><thead><tr><th width="247">Value</th><th>Description</th></tr></thead><tbody><tr><td><code>address _val</code></td><td>Address of the StakingRewards contract for BB tranche staking (can be address(0) which means that staking is disabled for BB)</td></tr></tbody></table>
