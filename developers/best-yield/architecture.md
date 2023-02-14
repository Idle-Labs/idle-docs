---
description: Developers > Best Yield > Architecture
---

# Architecture

The main smart contracts used by Idle are the following:

* `IdleToken` holds pooled funds of all users for a specific asset and issues ERC20 shares of the pool (IdleTokens) for each deposit.
* `IdleCompound`, `IdleAave` wrappers contract used by `IdleToken` to interact with the lending protocols implemented

<figure><img src="../../.gitbook/assets/Idle BY Dev.png" alt=""><figcaption></figcaption></figure>

{% hint style="success" %}
BY strategies are also ERC-4626 compliant! Deployed wrappers can be found [here](deployed-contracts.md#erc-4626-wrappers-for-best-yield-tokens).
{% endhint %}

Idle Rebalancer automatically analyses supply rate functions across integrated protocols and total funds in the pool to constantly rebalance capital across any number of protocols to **earn the highest interest rate possible** with very high precision. When a new allocation can improve the aggregated APY of an IdleTokens, the Rebalancer submits new allocations to the contract.&#x20;

{% hint style="info" %}
New allocations are not enforced, but when they are submitted, any user can trigger a rebalance.
{% endhint %}

During the rebalance process, `IdleToken` contracts check if the new allocation is different and eventually accept it. This triggers a rebalance which mints or redeem the pooled funds on different lending protocols via the dedicated wrappers (`IdleCompound`, `IdleAave`, ...).

{% hint style="warning" %}
If no rebalance is triggered after some time (currently every \~3h), an off-chain bot rebalances the pool for everyone.
{% endhint %}

All Idle strategies use the same set of smart contracts, but each allocation uses a different instance of those contracts.
