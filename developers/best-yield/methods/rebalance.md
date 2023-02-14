---
description: Developers > Best Yield > rebalance
---

# rebalance

This method dynamically allocates all the pooled funds across different lending protocols if needed.&#x20;

Everyone should be incentivized in calling this method if they spot an allocation that is not the optimal one.

This method will read allocations set by IdleRebalancer and check if current IdleToken allocations should be updated. It then calculates the exact amount to redeem and mint for each protocol.

In case of low liquidity on a protocol where we are trying to redeem, the rebalance process will try to redeem all the liquidity available, but it won't update the IdleToken allocations. In this way every subsequent rebalance (and also mint and redeem which calls the rebalance method) will try to redeem all the liquidity available at that moment until the correct allocations submitted by IdleRebalancer are enforced.

If a `maxUnlentPerc` is set in the contract this method will lend everything except for a small unlent pool (usually 1%) used for cheap redeems

### Function

```solidity
function rebalance(
) external returns (bool);
```

### **Return values**

| Value  | Description                                                          |
| ------ | -------------------------------------------------------------------- |
| `bool` | A boolean representing whether a rebalance has been performed or not |
