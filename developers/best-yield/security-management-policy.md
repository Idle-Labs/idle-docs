---
description: Developers > Best Yield > Security management policy
---

# Security management policy

## Best Yield vaults

`IdleTokenV4`, the factory contract for the _Best Yield_ strategy is an upgradable contract that uses [OpenZeppelin upgradability pattern](https://docs.openzeppelin.com/upgrades/2.8/proxies). Its upgradability is owned by the `Timelock` contract, which is controlled by IDLE token holders (as described in the [governance process](../../governance/idle-dao/governance-process/) section).

Each _Best Yield_ strategy consists of a proxy that points to a shared implementation of `IdleTokenV4` contracts. The implementation for each strategy can be upgraded through a shared Proxy Admin which is [`0x7740792812A00510b50022D84e5c4AC390e01417`](http://etherscan.io/address/0x7740792812A00510b50022D84e5c4AC390e01417).

The owner of the Proxy Admin and of Best Yield strategy's proxy is the `Timelock` contract which is owned by the `GovernorBravo`, controlled by `IDLE` holders.

There are a few administrative privileges that the `Timelock` have besides the ability to upgrade `IdleTokenV4` implementation logic:

* It can change Idle wrappers (`IdleCompound`, `IdleAave`, ...) and associated assets supported for lending protocols;
* It can add and or remove governance tokens supported for distribution;
* `fee` and `feeAddress`can be updated. \
  The fee is capped and can be at most 10% of the interest earned currently;
* It can set `maxUnlentPerc`, i.e. a percentage of unlent funds used for cheap redemption (currently 1% of all deposited assets).

### Additional functions

As part of the Security Management policy, there are 2 more functions with different privileges on the `IdleToken` contract

{% tabs %}
{% tab title="Pause Guardian" %}
`mintIdleToken` and `rebalance` can be paused during emergency situations, while `redeemIdleToken` and `redeemInterestBearingTokens` will always be available.

<table><thead><tr><th width="209">Product</th><th>Guardian</th></tr></thead><tbody><tr><td>Senior BY vaults</td><td><a href="https://etherscan.io/address/0xaDa343Cb6820F4f5001749892f6CAA9920129F2A">Idle Labs</a> multisig and <a href="https://etherscan.io/address/0xBaeCba470C229984b75BC860EFe8e97AE082Bb9f">Hypernative</a> pauser multisig</td></tr><tr><td>Junior BY vaults</td><td><a href="https://etherscan.io/address/0xFb3bD022D5DAcF95eE28a6B07825D4Ff9C5b3814">Treasury League</a> multisig, <a href="https://etherscan.io/address/0xe8eA8bAE250028a8709A3841E0Ae1a44820d677b">Development League</a> multisig and <a href="https://etherscan.io/address/0xBaeCba470C229984b75BC860EFe8e97AE082Bb9f">Hypernative</a> pauser multisig</td></tr></tbody></table>

where&#x20;

* Idle Labs multisig has a 2/4 threshold [`0xaDa343Cb6820F4f5001749892f6CAA9920129F2A`](http://etherscan.io/address/0xaDa343Cb6820F4f5001749892f6CAA9920129F2A)
* Treasury League multisig has a 3/6 threshold\
  [`0xFb3bD022D5DAcF95eE28a6B07825D4Ff9C5b3814`](https://etherscan.io/address/0xFb3bD022D5DAcF95eE28a6B07825D4Ff9C5b3814)
* Development League multisig has a 3/6 threshold\
  [`0xe8eA8bAE250028a8709A3841E0Ae1a44820d677b`](https://etherscan.io/address/0xe8eA8bAE250028a8709A3841E0Ae1a44820d677b)
* Hypernative pauser multisig has a 2/5 threshold\
  [`0xBaeCba470C229984b75BC860EFe8e97AE082Bb9f`](https://etherscan.io/address/0xBaeCba470C229984b75BC860EFe8e97AE082Bb9f)

The guardian can be changed at any time by the governance with a proposal.
{% endtab %}

{% tab title="Rebalancer" %}
The address designated to submit new allocations is currently set to [`0xB3C8e5534F0063545CBbb7Ce86854Bf42dB8872B`](https://etherscan.io/address/0xb3c8e5534f0063545cbbb7ce86854bf42db8872b).&#x20;

The Rebalancer can be changed at any time by the governance with a proposal.

For the Best Yield vaults, there is also the [`openRebalance`](broken-reference) available that allows anyone to submit new allocations, currently disabled for security reasons.
{% endtab %}
{% endtabs %}
