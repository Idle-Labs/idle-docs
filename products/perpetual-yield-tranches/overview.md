---
description: Products > Perpetual Yield Tranches > Overview
---

# Overview

## How do Perpetual Yield Tranches work?

The product offers two classes of tranches, differentiated by the level of risk and the share of underlying yield assigned to each class.

<figure><img src="../../.gitbook/assets/image (59).png" alt=""><figcaption></figcaption></figure>

{% tabs %}
{% tab title="Senior Tranches" %}
This class of tranche offers **intrinsic protection on funds**, given by Junior class deposits. Each pool is composed of yield-bearing tokens, and the pool’s NAV is meant to only increase. A decrease in the NAV triggers the emergency shutdown to protect PYTs liquidity providers.\
\
Senior Tranches intrinsically **have a first lien on the underlying assets** — they’re first in line to be repaid in case of default (hack or loss of funds). This product provides **full-spectrum coverage**, as the loss is covered regardless of the dependency or underlying protocol that caused it. Junior TVL will cover Senior TVL from a full spectrum of oracle/smart contract risks on:&#x20;

* Perpetual Yield Tranches themselves;&#x20;
* Underlying yield source;&#x20;
* All the dependencies of the underlying yield source.
{% endtab %}

{% tab title="Junior Tranches" %}
This class of tranche achieves a **greater and leveraged yield** by dragging more risk, as Junior holders have a second lien or no lien at all in case of fund losses.&#x20;

Junior tranche is designed to receive a higher share of yield compared to the Senior class, which will proportionally compensate for the higher risk taken by Junior depositors.
{% endtab %}
{% endtabs %}

## Adaptive Yield Split

The [Adaptive Yield Split](https://medium.com/idle-finance/adaptive-yield-split-foster-pyts-liquidity-scalability-a796fa17ea35) is the mechanism that computes the APY split between Senior and Junior Tranches. It is dynamically conditional to the liquidity deposited on each tranche side. This mechanism lets:

* **Senior Tranche** receives most of the underlying yield when liquidity is low on the Junior side (i.e. low coverage on Senior funds), or receives a guaranteed minimum portion of the underlying yield when Junior liquidity is high (i.e. high coverage on Senior funds);
* **Junior Tranche** receives outperforming APYs on the Junior Tranches, no matter what the amount of deposited liquidity on the Senior is.

<figure><img src="../../.gitbook/assets/Adaptive Yield Split.png" alt=""><figcaption><p>Returns examples vs a Base APY of 10%</p></figcaption></figure>

More technical details regarding this split mechanism can be found in the dedicated section.

{% content-ref url="adaptive-yield-split.md" %}
[adaptive-yield-split.md](adaptive-yield-split.md)
{% endcontent-ref %}

## Protocols and assets

Perpetual Yield Tranches are available on Ethereum and Polygon for multiple protocols and underlying assets.

### Ethereum

{% tabs %}
{% tab title="Lido" %}
#### Integrated assets

* [stETH](https://etherscan.io/address/0x34dcd573c5de4672c8248cd12a99f875ca112ad8)
* [MATIC](https://etherscan.io/address/0xF87ec7e1Ee467d7d78862089B92dd40497cBa5B8)

{% hint style="info" %}
stMATIC PYTs accept MATIC as the deposited asset to give users a seamless experience by staking their tokens in a few clicks. When users want to redeem, stMATIC PYTs generate an NFT representing the underlying capital. After 2–3 days, the average waiting period for stMATIC unstaking, users can finalize their withdrawal.
{% endhint %}
{% endtab %}

{% tab title="Euler" %}
#### Integrated assets

* [DAI](https://etherscan.io/address/0x46c1f702a6aad1fd810216a5ff15aab1c62ca826)
* [USDC](https://etherscan.io/address/0xf5a3d259bfe7288284bd41823ec5c8327a314054)
* [USDT](https://etherscan.io/address/0xd5469df8ca36e7eaedb35d428f28e13380ec8ede)
* [agEUR](https://etherscan.io/address/0x2398bc075fa62ee88d7fab6a18cd30bff869bda4)
* [DAI staking](https://etherscan.io/address/0x264E1552Ee99f57a7D9E1bD1130a478266870C39)
* [USDC staking](https://etherscan.io/address/0xf615a552c000B114DdAa09636BBF4205De49333c)
* [USDT staking](https://etherscan.io/address/0x860B1d25903DbDFFEC579d30012dA268aEB0d621)
* [WETH staking](https://etherscan.io/address/0xec964d06cD71a68531fC9D083a142C48441F391C)
{% endtab %}

{% tab title="Morpho" %}
Morpho is a peer-to-peer layer built on top of the lending pools of Aave.

#### Integrated assets

* [DAI](https://etherscan.io/address/0xDB82dDcb7e2E4ac3d13eBD1516CBfDb7b7CE0ffc)
* [USDC](https://etherscan.io/address/0x9C13Ff045C0a994AF765585970A5818E1dB580F8)
* [USDT](https://etherscan.io/address/0x440ceAd9C0A0f4ddA1C81b892BeDc9284Fc190dd)
* [WETH](https://etherscan.io/address/0xb3F717a5064D2CBE1b8999Fdfd3F8f3DA98339a6)
{% endtab %}

{% tab title="Clearpool" %}
#### Integrated assets

* USDC
* DAI
* USDT

Borrowers: [Portofino](https://www.portofino.tech/), [Fasanara](https://twitter.com/FasanaraDigital)
{% endtab %}
{% endtabs %}

LPs receive `IdleCDO_AA_StrategyName` (e.g. `IdleCDO_AA_idleDAIYield`) for Senior deposits and `IdleCDO_BB_StrategyName` for asset provision in the Junior class. Both tokens are fully fungible ERC-20.

Some Tranches are labelled as _Experimental_, meaning some deposit limits (caps) exist.

## Yield and loss scenarios

> Given the nature of the two classes of tranches, which differ in terms of risks and gains opportunities, it is possible to explain their behavior through two scenarios: a **Yield case** and a **Loss case.**

Let's assume to have a DAI pool generating a 10% yield, where users deposit $10m split as follows

* 70% on Senior Tranche, i.e. $7m
* 30% on Junior Tranche, i.e. $3m

<figure><img src="../../.gitbook/assets/image (74).png" alt=""><figcaption></figcaption></figure>

There can be two scenarios:

1. When the loss is higher than the Junior liquidity, the Senior Tranche will also In the **Yield case**, the interests generated in the pool ($1m DAI in total) will be split as $490k DAI (70% of the interest) to the Senior Tranche and $510k DAI (30% of the interest) to the Junior Tranche. As expected, The yield is higher for the Junior Tranche because, as mentioned, this class takes more risk than the Senior one and is rewarded accordingly.
2. In the **Loss case** (with the loss being lower than the Junior liquidity), the only class of tranches affected by a possible loss will be the Junior one. Suppose, there is a $1m DAI hack loss, the Senior tranche will have the entire (100%) capital protected, while Junior tranches will bear a partial loss (33%) of the funds deposited.
   * In the case when the loss is higher than the Junior liquidity, also the Senior Tranche will suffer from the hack. Its loss will be anyway mitigated by the Junior counterparty.&#x20;

## Benefits of using Perpetual Yield Tranches

* Cheaper transactions’ deposits and redeems;
* Governance tokens (COMP, stkAAVE, LDO, CVX, CRV) automatically harvested to boost yields;
* Deposits and withdrawals are possible at any time due to no locking periods or epochs;
* No hidden fees: 10-15% performance fee.
