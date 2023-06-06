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

<table><thead><tr><th width="264">Value</th><th>Description</th></tr></thead><tbody><tr><td><code>address _val</code></td><td>Address of the StakingRewards contract for AA tranche staking (can be <code>address(0)</code> which means that staking is disabled for AA)</td></tr></tbody></table>
