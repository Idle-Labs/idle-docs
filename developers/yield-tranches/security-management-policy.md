---
description: Developers > Yield Tranches > Security management policy
---

# Security management policy

## Yield Tranches

The implementation for each Tranche can be upgraded through a shared Proxy Admin, which is [`0x9438904ABC7d8944A6E2A89671fEf51C629af351`](https://etherscan.io/address/0x9438904abc7d8944a6e2a89671fef51c629af351).

The owner of the Proxy Admin and of Yield Tranches' contracts  is the `Treasury League Multisig`, which is [`0xFb3bD022D5DAcF95eE28a6B07825D4Ff9C5b3814`](https://etherscan.io/address/0xFb3bD022D5DAcF95eE28a6B07825D4Ff9C5b3814).

### Additional functions

As part of the Security Management policy, there is one more function in the `IdleCDO` contract.

{% tabs %}
{% tab title="Pause Guardian" %}
The pause guardian can pause, unpause and call `emergencyShutdown`. YTs contracts can be paused during emergency situations.

<table><thead><tr><th width="209">Product</th><th>Guardian</th></tr></thead><tbody><tr><td>Yield Tranches</td><td><a href="https://etherscan.io/address/0xBaeCba470C229984b75BC860EFe8e97AE082Bb9f">Hypernative</a> pauser multisig</td></tr></tbody></table>

where&#x20;

* Hypernative pauser multisig has a 2/5 threshold\
  [`0xBaeCba470C229984b75BC860EFe8e97AE082Bb9f`](https://etherscan.io/address/0xBaeCba470C229984b75BC860EFe8e97AE082Bb9f)

The guardian can be changed at any time by the governance with a proposal.
{% endtab %}
{% endtabs %}
