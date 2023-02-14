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

| Parameter             | Description                                                        |
| --------------------- | ------------------------------------------------------------------ |
| `_amount`             | The amount of underlying token to be lent                          |
| `_skipWholeRebalance` | Boolean flag. Not used anymore so can receive either true or false |
| `_referral`           | Address for an eventual future referral program                    |

### **Return values**

| Value          | Description                       |
| -------------- | --------------------------------- |
| `mintedTokens` | The amount of $IDLE tokens minted |
