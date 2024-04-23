---
description: Products > Best Yield > Overview
---

# Overview

The Best Yield vaults aggregate and optimize multiple lending markets:

* Over-collateralised, top-tier lending protocols such as Aave, Compound
* Idle's [Senior Yield Tranches](../yield-tranches/) to maintain a conservative risk profile while extending and improving the yield spectrum.

It either optimizes allocation continuously using an algorithm or uses fixed weights allocation.

## How does Best Yield work?

The Best Yield vaults constantly monitor interest rates on various DeFi yield sources to ensure the current allocation is yielding the best aggregate interest rate available on the market. Users' funds are pooled together and programmatically deposited into one or more of the available lending protocols.&#x20;

<figure><img src="../../.gitbook/assets/BY.png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
By analyzing supply rate functions across integrated platforms and total funds in the pool, the strategy is able to constantly rebalance capital across any number of protocols to **earn the highest interest rate possible** with very high precision.
{% endhint %}

When users deposit funds, they receive `idleTokens` from Idle in exchange. `idleTokens` are ERC-20 tokens that can be redeemed for their underlying assets at any time. As interest accrues to the assets supplied, `idleTokens` are redeemable at an exchange rate (relative to the underlying asset) that constantly increases over time, based on the interest earned by the underlying asset.

## Allocation model

Best Yield vaults maximise the current aggregated interest rate, modeled as follows

$$
max\ q(x)= \sum_{i=0}^{n} \frac{x_i}{tot} * nextRate_i(x_i)
$$

where `n` is the number of lending protocols used, `x_i` is the amount (in underlying) allocated in the protocol `i` , `nextRate(x_i)` is a function that returns the new APR for protocol `i` after supplying `x_i` amount of underlying and is `tot` the total

$$
tot=\sum_{i=0}^{n} x_i
$$

## Protocols and assets&#x20;

{% tabs %}
{% tab title="Ethereum" %}
Best Yield with algorithmic optimization

**Integrated protocols**

* [Compound](https://compound.finance/)
* [Aave](https://aave.com/)
* [Senior tranches](../yield-tranches/overview.md#senior-tranches) of [Clearpool](https://clearpool.finance/) markets

#### Integrated assets

* [DAI](https://etherscan.io/address/0x3fe7940616e5bc47b0775a0dccf6237893353bb4)
* [USDC](https://etherscan.io/address/0x5274891bEC421B39D23760c04A6755eCB444797C)
* [USDT](https://etherscan.io/address/0xF34842d05A1c888Ca02769A633DF37177415C2f8)
{% endtab %}

{% tab title="Optimism" %}
Best Yield with fixed allocation on RWA markets

**Integrated protocols**

* [Senior tranches](../yield-tranches/overview.md#senior-tranches) of [Clearpool](https://clearpool.finance/) markets

#### Integrated assets

* [USDT](https://etherscan.io/address/0xF34842d05A1c888Ca02769A633DF37177415C2f8)
{% endtab %}
{% endtabs %}

{% hint style="info" %}
Idle DAO has established a series of [Integration Standard Requirements](../../developers/security/integration-standard-requirements.md) to integrate new yield sources or assets in the BY vaults.
{% endhint %}

## Benefits of using Best Yield

* A superior _optimisation algorithm_ for automatic management of users' funds;&#x20;
* Gas fees savings for funds rebalance (which the user would have to pay to deposit funds/interact from one platform to another);&#x20;
* Participating in the $IDLE liquidity mining program and leveraging all the advantages linked to its [multiple use cases](../../governance/idle/use-cases/);&#x20;
* By depositing into BY pools users can get other underlying governance tokens as a form of incentives (e.g. COMP or AAVE);&#x20;
* For integrators, no need to stitch together disparate protocols or spend months integrating and updating yield functionality.
