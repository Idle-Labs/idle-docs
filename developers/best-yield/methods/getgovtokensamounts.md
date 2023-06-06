---
description: Developers > Best Yield > getGovTokensAmounts
---

# getGovTokensAmounts

This method gets a lower bound estimate of the fair share of governance tokens a user is entitled to. The actual amount is calculated during redeem only.

### Function

```solidity
function getGovTokensAmounts(
    address _user
) external view returns (uint256[] calldata _amounts);
```

### **Parameters**

<table><thead><tr><th width="286">Parameter</th><th>Description</th></tr></thead><tbody><tr><td><code>_user</code></td><td>The address of the user</td></tr></tbody></table>

### **Return value**

<table><thead><tr><th width="290">Value</th><th>Description</th></tr></thead><tbody><tr><td><code>_amounts</code></td><td>An array of gov tokens amounts ordered following the <code>govTokens</code> order of the storage variable of the contract containing all the governance token addresses supported</td></tr></tbody></table>
