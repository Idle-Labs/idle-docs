---
description: Developers > Best Yield > mintIdleToken
---

# mintIdleToken

This method is used to deposit money into the Idle protocol. When you call `mintIdleToken` we will transfer the amount of underlying supplied to IdleToken contract and then mint interest-bearing tokens with that amount.&#x20;

Interest-bearing tokens of each user are pooled together inside the IdleToken contract and you will then receive $IDLE tokens which represent your share of Idle pools.

**Users should call `approve` on the underlying asset used (eg. DAI) to allow IdleToken contract to spend `_amount` of tokens before calling this method.**

{% hint style="info" %}
Please note that after the first mint all subsequent ones will also send governance tokens (e.g. IDLE) to `msg.sender` (if `msg.sender` had other previously minted idleTokens in the account).
{% endhint %}

### Function

```solidity
function mintIdleToken(
    uint256 _amount, 
    bool _skipWholeRebalance, 
    address _referral
) external returns (uint256 mintedTokens);
```

### **Parameters**

<table><thead><tr><th width="277">Parameter</th><th>Description</th></tr></thead><tbody><tr><td><code>_amount</code></td><td>The amount of underlying token to be lent</td></tr><tr><td><code>_skipWholeRebalance</code></td><td>Boolean flag. Not used anymore so can receive either true or false</td></tr><tr><td><code>_referral</code></td><td>Address for an eventual future referral program</td></tr></tbody></table>

### **Return values**

<table><thead><tr><th width="282">Value</th><th>Description</th></tr></thead><tbody><tr><td><code>mintedTokens</code></td><td>The amount of $IDLE tokens minted</td></tr></tbody></table>
