---
description: Products > Yield Tranches > Covered risks
---

# Covered risks

Each Yield Tranche is based on one or more yield sources, which are exposed to a set of dependencies and risks. Additionally, every YT is subject to underlying strategy and [Idle YTs infrastructure](../../../developers/security/audits.md#perpetual-yield-tranches) risks.

{% hint style="info" %}
Given the nature of the two classes of tranches, which differ in terms of risks and gains opportunities, it is possible to explain their behaviour through two scenarios: a **Yield case** and a **Loss case**. See Yield and Loss scenarios in the [Overview](../overview.md) section.&#x20;
{% endhint %}

In general, Senior YTs holders always benefit from the payout priority (first in line to redeem their funds) after events that can cause _a decrease_ in:

* the exchange rate between YTs-managed yield-bearing tokens'  and the underlying asset
* the exchange rate between YTs tokens and the underlying asset

{% hint style="info" %}
Examples:

* A downstream lending market suffers a loss of funds and the price of the yield-bearing tokens deployed by YTs decreases. The affected Junior and Senior YTs are automatically paused.&#x20;
* The YTs’ main contract, `idleCDO`, suffers a loss of funds, letting the attacker redeem deposited yield-bearing tokens. The price of the YT token decreases. The affected Junior and Senior YTs are manually paused.
{% endhint %}

YTs interact with a range of DeFi primitives, each with its own specific risks. Every primitive, though, share a number of common risks:

<table><thead><tr><th>Risk</th><th width="184.0554663848362">Description</th><th width="174.06957708049114">Outcome</th><th width="150">Coverage</th></tr></thead><tbody><tr><td>Smart contract</td><td>Exploit of a bug in downstream yield protocols' code</td><td>Partial loss of funds</td><td>Yes</td></tr><tr><td>Governance</td><td>Adverse changes to protocol parameter</td><td>Partial loss of funds</td><td>Yes</td></tr><tr><td>Asset de-peg</td><td>The peg of a token against another asset is lost</td><td>Reduced value against other units of account</td><td>No</td></tr></tbody></table>

A list of specific risks affecting _Automated Market Makers_, _Lending protocols_, _Liquid Staking protocols_, _Leveraged strategies_ and _Options strategies_ follows.

### Automated Market Makers

<table><thead><tr><th>Risk</th><th width="184.0554663848362">Description</th><th width="174.06957708049114">Outcome</th><th width="150">Coverage</th></tr></thead><tbody><tr><td>Impermanent loss</td><td>Change of the token price in the underlying pool</td><td>Reduced fiat ($) value</td><td>No</td></tr></tbody></table>

### Lending Protocols&#x20;

Lending protocols are mainly classified into two categories based on the type of loans they offer: _overcollateralized_ and _undercollateralized_.

#### Overcollateralized lending

<table><thead><tr><th>Risk</th><th width="184.0554663848362">Description</th><th width="174.06957708049114">Outcome</th><th width="150">Coverage</th></tr></thead><tbody><tr><td>Incorrect price feed</td><td>Oracle manipulation or failure</td><td>Bad debt creation</td><td>Yes</td></tr><tr><td>Unappropiate collateral factors</td><td>Generation of untenable positions</td><td>Bad debt creation</td><td>Yes</td></tr><tr><td>Wrong liquidation</td><td>Liquidation does not work as expected</td><td>Bad debt creation</td><td>Yes</td></tr></tbody></table>

#### **Undercollateralized lending**

<table><thead><tr><th>Risk</th><th width="184.0554663848362">Description</th><th width="174.06957708049114">Outcome</th><th width="150">Coverage</th></tr></thead><tbody><tr><td>Borrower default</td><td>Borrower is not able to pay back the loan and is insolvent</td><td>Partial loss of funds</td><td>Yes</td></tr></tbody></table>

### **Liquid staking protocols**

<table><thead><tr><th>Risk</th><th width="184.0554663848362">Description</th><th width="174.06957708049114">Outcome</th><th width="150">Coverage</th></tr></thead><tbody><tr><td>Validator key management</td><td>Loss of multisig keys holding staked ETH</td><td>Partial loss of funds</td><td>Yes</td></tr><tr><td>Slashing</td><td>Staking penalties for validators' network</td><td>Partial loss of funds</td><td>Yes</td></tr></tbody></table>

NB - YTs do not cover Senior LPs funds in case of events leading to a de-peg.

### Leveraged strategies

<table><thead><tr><th>Risk</th><th width="184.0554663848362">Description</th><th width="174.06957708049114">Outcome</th><th width="150">Coverage</th></tr></thead><tbody><tr><td>Liquidation</td><td>Liquidation of the position at loss</td><td>Partial loss of funds</td><td>Yes</td></tr></tbody></table>

<details>

<summary>Instadapp Yield Tranches</summary>

Instadapp lite vaults have automation functions, which automatically rebalance the vault during market changes. If the vault gets risky, it can first refinance into another protocol to maintain safety, or it can deleverage by selling stETH and paying back the ETH debt. This kind of automation, if required or occurs, may incur losses caused by trading slippage:

* if the loss is less than or equal to 0.5%, the loss is distributed proportionally among the funds deposited in the tranches.
* if the loss is greater than 0.5%, the Junior tranche will absorb the entire loss.

</details>

### **Options strategies**

<table><thead><tr><th>Risk</th><th width="184.0554663848362">Description</th><th width="174.06957708049114">Outcome</th><th width="150">Coverage</th></tr></thead><tbody><tr><td>Financial</td><td>The strategy generates negative returns</td><td>Partial loss of funds</td><td>Yes</td></tr></tbody></table>
