---
description: Developers > Perpetual Yield Tranches > Architecture
---

# Architecture

The main contract used by users is called `IdleCDO` which allows depositing the underlying and mint tranche tokens (ERC-20), either AA or BB, and redeeming principal and interest from it.

{% hint style="success" %}
PYTs are also ERC-4626 compliant! Deployed wrappers can be found [here.](deployed-contracts.md#erc-4626-wrappers-for-tranche-tokens)
{% endhint %}

The IdleCDO contract pools users' funds together and uses `IIdleCDOStrategy` as a proxy for interacting with the underlying DeFi protocol to deposit funds and collect interest and rewards.

Governance tokens collected as rewards are not redistributed to users directly in the IdleCDO contract but rather sold to the market (`harvest` method) and the underlying reinvested in the downstream lending provider where possible.&#x20;

Other tokens, if any (e.g. IDLE that won't be sold or tokens that have no liquid markets) will get redistributed to people who staked their tranches in a `LiquidityGauge` contract usually one for AA and sometimes one for BB (for more info on Gauges, see [here](../gauges/)).

### Codebase and contracts

The codebase and a general overview of the architecture can be found at [https://github.com/Idle-Labs/idle-tranches](https://github.com/Idle-Labs/idle-tranches).

These are the core contracts used:

<details>

<summary>IdleCDO.sol</summary>

A contract that holds all the user pooled assets (both underlying, e.g. DAI, and interest-bearing tokens, e.g. _idleDAI_) and is an entry point for the user to mint tranche tokens and burn them to redeem principal and interest.&#x20;

When users deposit into the CDO they will:&#x20;

* update the global accounting of the system (i.e. split accrued rewards)
* mint their chosen tranche tokens.&#x20;

Funds won't get put in lending right away.&#x20;

The `harvest` method will be called periodically to put new deposits in lending, get fees and update the accounting.&#x20;

During the harvest call, some predefined rewards will be sold into the market (via Uniswap) and released linearly over _x_ (currently set a 1500) blocks, to increase the value of all tranche holders. \
On redeem, users will burn their tranche tokens and get underlying using a checkpointed price (set at last harvest to avoid potential theft of interest, updated when dumping governance tokens to increase the tranche price).

</details>

<details>

<summary>IdleCDOTranche.sol</summary>

ERC-20 representing a specific (either AA or BB) tranche token. Only IdleCDO contract can mint and burn tranche tokens.

</details>

On top of these, all the strategies (`IIdleCDOStrategy`) currently used can be found here [https://github.com/Idle-Labs/idle-tranches/tree/master/contracts/strategies](https://github.com/Idle-Labs/idle-tranches/tree/master/contracts/strategies).
