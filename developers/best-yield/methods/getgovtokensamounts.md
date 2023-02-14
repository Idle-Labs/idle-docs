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

| Parameter | Description             |
| --------- | ----------------------- |
| `_user`   | The address of the user |

### **Return value**

| Value      | Description                                                                                                                                                            |
| ---------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `_amounts` | An array of gov tokens amounts ordered following the `govTokens` order of the storage variable of the contract containing all the governance token addresses supported |
