---
description: Developers > Yield Tranches > Methods > depositBBnonpayable
---

# depositBB

This method transfer `token` from the user to the contract and mint BB (Junior) tranche tokens for the user.

`msg.sender` should approve this contract first to spend `_amount` of `token`

### Function

```solidity
function depositBB(
    uint256 _amount
) external returns (uint256)
```

### Parameters

| Parameter | Description                  |
| --------- | ---------------------------- |
| `_amount` | Amount of `token` to deposit |

### Return values

<table><thead><tr><th width="273">Value</th><th>Description</th></tr></thead><tbody><tr><td><code>_val</code></td><td>BB tranche tokens minted</td></tr></tbody></table>
