---
description: Developers > Best Yield > Security management policy
---

# Security management policy

## Best Yield strategy

`IdleTokenV4`, the factory contract for the _Best Yield_ strategy is an upgradable contract that uses [OpenZeppelin upgradability pattern](https://docs.openzeppelin.com/upgrades/2.8/proxies). Its upgradability is owned by the `Timelock` contract, which is controlled by IDLE token holders (as described in the [governance process](../../governance/idle-dao/governance-process/) section).

Each _Best Yield_ strategy consists of a proxy that points to a shared implementation of `IdleTokenV4` contracts. The implementation for each strategy can be upgraded through a shared Proxy Admin which is [`0x7740792812A00510b50022D84e5c4AC390e01417`](http://etherscan.io/address/0x7740792812A00510b50022D84e5c4AC390e01417).

The owner of the Proxy Admin and of Best Yield strategy's proxy is the `Timelock` contract which is owned by the `GovernorBravo`, controlled by `IDLE` holders.

There are a few administrative privileges that the `Timelock` have besides the ability to upgrade `IdleTokenV4` implementation logic:

* It can change Idle wrappers (`IdleCompound`, `IdleAave`, ...) and associated assets supported for lending protocols;
* It can add and or remove governance tokens supported for distribution;
* `fee` and `feeAddress`can be updated. \
  The fee is capped and can be at most 10% of the interest earned currently;
* It can set `maxUnlentPerc`, i.e. a percentage of unlent funds used for cheap redeem (currently 1% of all deposited assets).

### Additional functions

As part of the Security Management policy, there are 2 more functions with different privileges on the `IdleToken` contract

{% tabs %}
{% tab title="Pause Guardian" %}
`mintIdleToken` and `rebalance` can be paused during emergency situations, while `redeemIdleToken` and `redeemInterestBearingTokens` will always be available.\


The pause guardian is currently _Idle Labs Inc._ with a 2-of-4 multisig [`0xaDa343Cb6820F4f5001749892f6CAA9920129F2A`](http://etherscan.io/address/0xaDa343Cb6820F4f5001749892f6CAA9920129F2A).\


The guardian can be changed at any time by the governance with a proposal.
{% endtab %}

{% tab title="Rebalancer" %}
The address designated to submit new allocations is currently set to [`0xB3C8e5534F0063545CBbb7Ce86854Bf42dB8872B`](https://etherscan.io/address/0xb3c8e5534f0063545cbbb7ce86854bf42db8872b). \


The Rebalancer can be changed at any time by the governance with a proposal.\


For the Best Yield strategy, there is also the [openRebalance](broken-reference) available that allows anyone to submit new allocations, currently disabled for security reasons.
{% endtab %}
{% endtabs %}
