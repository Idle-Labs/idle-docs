---
description: Products > Perpetual Yield Tranches > Covered risks
---

# Covered risks

Each Perpetual Yield Tranche is based on one or more yield sources, which are exposed to a set of dependencies and risks. Additionally, every PYT is subject to underlying strategy and [Idle PYTs infrastructure](../../developers/security/audits.md#perpetual-yield-tranches) risks.

{% hint style="info" %}
Given the nature of the two classes of tranches, which differ in terms of risks and gains opportunities, it is possible to explain their behaviour through two scenarios: a **Yield case** and a **Loss case**. **** See Yield and Loss scenarios in the [Overview](overview.md) section.&#x20;
{% endhint %}

In general, Senior PYTs holders always benefit from the payout priority (first in line to redeem their funds) after events that can cause _a decrease_ in:

* the exchange rate between PYTs-managed yield-bearing tokens'  and the underlying asset
* the exchange rate between PYTs tokens and the underlying asset

{% hint style="info" %}
Examples:

* A downstream lending market suffers a loss of funds and the price of the yield-bearing tokens deployed by PYTs decreases. The affected Junior and Senior PYTs are automatically paused.&#x20;
* The PYTs’ main contract, `idleCDO`, suffers a loss of funds, letting the attacker redeem deposited yield-bearing tokens. The price of the PYT token decreases. The affected Junior and Senior PYTs are manually paused.
{% endhint %}

PYTs interact with a range of DeFi primitives, each with its own specific risks. Every primitive, though, share a number of common risks:

| Risk           | Description                                          | Outcome                                      | Coverage |
| -------------- | ---------------------------------------------------- | -------------------------------------------- | -------- |
| Smart contract | Exploit of a bug in downstream yield protocols' code | Partial loss of funds                        | Yes      |
| Governance     | Adverse changes to protocol parameter                | Partial loss of funds                        | Yes      |
| Asset de-peg   | The peg of a token against another asset is lost     | Reduced value against other units of account | No       |

A list of specific risks affecting _Automated Market Makers_, _Lending protocols_, _Liquid Staking protocols_, _Leveraged strategies_ and _Options strategies_ follows.

### Automated Market Makers

| Risk             | Description                                      | Outcome                | Coverage |
| ---------------- | ------------------------------------------------ | ---------------------- | -------- |
| Impermanent loss | Change of the token price in the underlying pool | Reduced fiat ($) value | No       |

### Lending Protocols&#x20;

Lending protocols are mainly classified into two categories based on the type of loans they offer: _overcollateralized_ and _undercollateralized_.

#### Overcollateralized lending

| Risk                            | Descrption                            | Outcome           | Coverage |
| ------------------------------- | ------------------------------------- | ----------------- | -------- |
| Incorrect price feed            | Oracle manipulation or failure        | Bad debt creation | Yes      |
| Unappropiate collateral factors | Generation of untenable positions     | Bad debt creation | Yes      |
| Wrong liquidation               | Liquidation does not work as expected | Bad debt creation | Yes      |

#### **Undercollateralized lending**

| Risk             | Description                                                | Outcome               | Coverage |
| ---------------- | ---------------------------------------------------------- | --------------------- | -------- |
| Borrower default | Borrower is not able to pay back the loan and is insolvent | Partial loss of funds | Yes      |

### **Liquid staking protocols**

| Risk                     | Description                               | Outcome               | Coverage |
| ------------------------ | ----------------------------------------- | --------------------- | -------- |
| Validator key management | Loss of multisig keys holding staked ETH  | Partial loss of funds | Yes      |
| Slashing                 | Staking penalties for validators' network | Partial loss of funds | Yes      |

NB - PYTs do not cover Senior **** LPs funds in case of events leading to a de-peg.

### Leveraged strategies

| Risk        | Description                         | Outcome               | Coverage |
| ----------- | ----------------------------------- | --------------------- | -------- |
| Liquidation | Liquidation of the position at loss | Partial loss of funds | Yes      |

### **Options strategies**

| Risk      | Description                             | Outcome               | Coverage |
| --------- | --------------------------------------- | --------------------- | -------- |
| Financial | The strategy generates negative returns | Partial loss of funds | Yes      |
