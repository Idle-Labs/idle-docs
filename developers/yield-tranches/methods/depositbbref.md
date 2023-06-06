---
description: Developers > Yield Tranches > Methods > depositBBRef
---

# depositBBRef

This method transfers `token` from the user to the contract and mint BB (Junior) tranche tokens for the user. It gives also the possibility to add a referral address.&#x20;

`msg.sender` should approve this contract first to spend `_amount` of `token`

### Function

```solidity
function depositBBRef(
    uint256 _amount
    address _referral
) external returns (uint256)
```

### Parameters

<table><thead><tr><th width="303">Parameter</th><th>Description</th></tr></thead><tbody><tr><td><code>_amount</code></td><td>Amount of <code>token</code> to deposit</td></tr><tr><td><code>_referral</code></td><td>Referral address</td></tr></tbody></table>

### Return values

<table><thead><tr><th width="307">Value</th><th>Description</th></tr></thead><tbody><tr><td><code>_val</code></td><td>BB tranche tokens minted</td></tr></tbody></table>
