---
description: Developers > Yield Tranches > Methods > getContractValue
---

# getContractValue

This method calculates the current total value locked (in `token` terms).

{% hint style="info" %}
**Note 1**: `unclaimedFees`are not included in the contract value.

**Note 2**: fees that _will_ be taken (in the next `_updateAccounting` call) are counted
{% endhint %}

### Function

```solidity
function getContractValue(
) external view returns (uint256)
```

### Return values

<table><thead><tr><th width="270">Value</th><th>Description</th></tr></thead><tbody><tr><td><code>_val</code></td><td>TVL (is the sum of unlent balance in the contract + the balance in lending - the reduction for harvested rewards - unclaimedFee)</td></tr></tbody></table>

{% hint style="info" %}
Unlent balance (`unlentPerc`) is currently set at 2% of the total funds.&#x20;
{% endhint %}
