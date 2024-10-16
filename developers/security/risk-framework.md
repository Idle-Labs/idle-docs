---
description: Developers > Security > Risk Framework
---

# Risk Framework

This framework aims to standardize analyses of new underlying markets to be integrated into [Yield Tranches](../../products/yield-tranches/) and [Best Yield](../../products/best-yield/) by quantifying and assessing the risks related to new underlying strategies. It is composed of four sections that lead to a final rating.&#x20;

* [Structure](risk-framework.md#structure)
  * [Third-party review](risk-framework.md#1.-third-party-review)
  * [Internal Security review](risk-framework.md#2.-internal-security-review)
  * [Strategy review](risk-framework.md#3.-strategy-review)
  * [Coverage](risk-framework.md#4.-coverage)
* [Risk rating](risk-framework.md#risk-rating)

Risks affecting DeFi protocols can be segregated into **systemic risks** or risks that impact a large part or all of the DeFi ecosystem such as currency, regulatory and chain risks, and **idiosyncratic risks** or risks that impact a single protocol or group of protocols, such as smart contract, governance, market, financial and oracle risks.

<table><thead><tr><th width="208">Risk</th><th>Metrics</th></tr></thead><tbody><tr><td>Smart contract</td><td>Immutable or upgradeable SC, audits, track record of auditors, number of hacks and third-party protocol dependencies</td></tr><tr><td>Governance</td><td>Team transparency, admin keys control, level of governance concentration and governance-related issues, emergency exit plan</td></tr><tr><td>Market &#x26; Financial</td><td>Total Value Locked, complexity, longevity, tokenomics</td></tr><tr><td>Oracle</td><td>Oracle dependencies, oracle fallbacks</td></tr></tbody></table>

## Structure

The framework is constituted of four parts:

1. [**Third-party review** ](risk-framework.md#1.-third-party-review)\
   (33%) considering the reports of [DeFi Safety](https://defisafety.com/app) and [Exponential](https://exponential.fi/pools/search). These reviews will ensure that part of the risk rating will be based on independent analyses, avoiding any centralization issue that could affect Idle’s risk-scoring impartiality.
2. [**Internal Security review** ](risk-framework.md#2.-internal-security-review)\
   (33%) focusing on [Protocols risks](https://gov.idle.finance/t/risk-framework-version-1/1143#Protocol-risks) from a smart contract, governance and market perspective. This review will be done by Idle DAO based on publicly available information and will use the same metrics for every protocol analyzed.
3. [**Strategy review** ](risk-framework.md#3.-strategy-review)\
   (34%) assessing the risks of each specific vertical, such as overcollateralized lending, uncollateralized lending, automated market makers, liquid staking and more.
4. [**Coverage** ](risk-framework.md#4.-coverage)\
   measuring the minimum coverage needed to let the Best Yield deposit funds into the Yield Tranches pools.

### 1. Third-party review

The DeFi Safety and Exponential scores consider the vast majority of the Protocol risks related to Idiosyncratic risks:

{% tabs %}
{% tab title="DeFi Safety metrics" %}
The DeFi Safety score will be time-adjusted, considering when the report was last updated. The older the analysis, the lower the score.

Components:

* Smart contracts and team
* Documentation
* Testing
* Security
* Admin controls
* Oracles
{% endtab %}

{% tab title="Exponential metrics" %}
where _PF_ stands for Protocol fundamentals and _PE_ for Pool economics.

Components:

* (PF) Asset strength
* (PF) Protocol code quality
* (PF) Protocol maturity
* (PF) Protocol design
* (PF) Chain design
* (PE) Collateralization and leverage
* (PE) Impermanent loss
* (PE) Yield outlook
* (PE) Chain reliability
{% endtab %}
{% endtabs %}

### 2. Internal Security review

This review mainly focuses on smart contracts and market/financial risks.

<table><thead><tr><th width="235">Type</th><th>Description</th></tr></thead><tbody><tr><td>Audit</td><td>Number of audits and quality of auditors</td></tr><tr><td>Bad debt, LP losses</td><td>Severity of losses incurred, if any (% vs TVL)</td></tr><tr><td>Bug bounty, Insurance</td><td>Size of bug bounty program</td></tr><tr><td>Protocol TVL</td><td>Total value locked across all chains (average since protocol inception)</td></tr><tr><td>Pool TVL</td><td>Total value locked on Ethereum (average since pool inception)</td></tr><tr><td>Protocol longevity</td><td>Months of activity</td></tr><tr><td>Pool longevity</td><td>Months of activity</td></tr></tbody></table>

### 3. Strategy review

The Strategy component refers to specific risks related to each underlying market integrated into Idle strategies. The strategy score will be composed of a fixed parameter associated with the vertical and a score associated with thematic risks.

**Current underlying sources**

* Best Yield: Aave, Compound and either Senior or Junior tranches.
* Yield Tranches: Euler, Morpho, Lido and Clearpool.

<table><thead><tr><th width="249">Vertical</th><th>Metric</th></tr></thead><tbody><tr><td>Overcollateralized lending</td><td>Collateral fully diluted value (FDV)</td></tr><tr><td></td><td>Maximum borrowed amount</td></tr><tr><td>Uncollateralized lending</td><td>Credora's borrower capacity</td></tr><tr><td></td><td>Credora's borrower rating</td></tr><tr><td>Liquid staking</td><td>Validator concentration</td></tr><tr><td></td><td>Validators key management</td></tr></tbody></table>

### 4. Coverage

The Coverage component measures **the minimum coverage needed to let the Best Yield deposit funds into the Yield Tranches pools**.&#x20;

This metric behaves differently with respect to the others listed and will be computed on a case by case need. It will be summed to the previous scores obtained with the reviews: Third-party, Internal Security and Strategy.

## Risk rating

The Risk Framework will assign a percentage score that will be then translated to a letter rating (A-E) based on the protocol risks evaluation, where

* A will be given to the highest-rated protocols in terms of overall risks
* E will be given to the lowest-rated protocols in terms of overall risks

| Rating      |   A  |  B  |  C  |  D  |  E  |
| ----------- | :--: | :-: | :-: | :-: | :-: |
| Upper bound | 100% | 85% | 70% | 55% | 40% |
| Lower bound |  85% | 70% | 55% | 40% |  0% |

{% hint style="success" %}
The Governance discussion can be found here: [Risk Framework (v1)](https://gov.idle.finance/t/risk-framework-version-1/1143)

The full analysis is available here: [Risk Framework \[PUBLIC\]](https://docs.google.com/spreadsheets/d/1vfnv49n688vYrxR9lk5ze0jCM7y2pLrCNPY0S9Yxc90/edit?usp=sharing)
{% endhint %}
