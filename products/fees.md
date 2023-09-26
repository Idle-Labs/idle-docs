---
description: Products > Fee structure
---

# Fee structure

Idle strategies charge a **performance fee deducted from the earned yields**.&#x20;

### Best Yield

For _Best Yield_ strategies, the fees are charged at funds redeem. Accrued fees are routed to the [`FeeTreasury`](https://etherscan.io/address/0x69a62c24f16d4914a48919613e8ee330641bcb94)contract governed by $IDLE token holders and to the [`Treasury League multisig`](https://etherscan.io/address/0xFb3bD022D5DAcF95eE28a6B07825D4Ff9C5b3814).&#x20;

<table><thead><tr><th width="258.3333333333333">BY</th><th>10% performance fee</th><th>15% performance fee</th></tr></thead><tbody><tr><td>Senior Best Yield</td><td><span data-gb-custom-inline data-tag="emoji" data-code="2705">✅</span></td><td></td></tr><tr><td>Junior Best Yield</td><td></td><td><span data-gb-custom-inline data-tag="emoji" data-code="2705">✅</span></td></tr></tbody></table>

### Yield Tranches

For the _Yield Tranches_ strategies, a 10-15% performance fee is deducted from earned yield every time a YT auto-compound accrued rewards. Accrued fees are currently routed to the [`Treasury League multisig`](https://etherscan.io/address/0xFb3bD022D5DAcF95eE28a6B07825D4Ff9C5b3814).

<table><thead><tr><th width="306.3333333333333">YTs</th><th>10% performance fee</th><th>15% performance fee</th></tr></thead><tbody><tr><td><strong>Lido</strong>: stETH</td><td><span data-gb-custom-inline data-tag="emoji" data-code="2705">✅</span></td><td></td></tr><tr><td><strong>Lido</strong>: stMATIC</td><td></td><td><span data-gb-custom-inline data-tag="emoji" data-code="2705">✅</span></td></tr><tr><td><strong>Instadapp</strong>: stETH</td><td></td><td><span data-gb-custom-inline data-tag="emoji" data-code="2705">✅</span></td></tr><tr><td><strong>Morpho</strong>: DAI, USDC, USDT, WETH</td><td></td><td><span data-gb-custom-inline data-tag="emoji" data-code="2705">✅</span></td></tr><tr><td><strong>Clearpool</strong>: USDC, DAI, USDT</td><td></td><td><span data-gb-custom-inline data-tag="emoji" data-code="2705">✅</span></td></tr></tbody></table>

{% hint style="info" %}
Performance Fees are computed by difference using the average `IdleToken` or `IdleCDO`price paid by the user for all their deposits and the current `IdleToken` or `IdleCDO`price. All transfer methods (`tranfer` and `transferFrom`) of IdleToken will also transfer the eventual fee debt to the receiver.
{% endhint %}

## Product suite revenue

The revenue breakdown is available on Dune Analytics.&#x20;

{% embed url="https://dune.com/idle.finance/revenue-outlook" %}

The [Performance Reports](../governance/idle-dao/treasury/reports.md) published at every mandate's end summarize the overall financial health of the Idle DAO treasury and the performances of the Idle's strategies.

{% content-ref url="../governance/idle-dao/treasury/reports.md" %}
[reports.md](../governance/idle-dao/treasury/reports.md)
{% endcontent-ref %}
