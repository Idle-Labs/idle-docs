---
description: Developers > Perpetual Yield Tranches > Security management policy
---

# Security management policy

## Perpetual Yield Tranches

The implementation for each Tranche can be upgraded through a shared Proxy Admin which is [`0x9438904ABC7d8944A6E2A89671fEf51C629af351`](https://etherscan.io/address/0x9438904abc7d8944a6e2a89671fef51c629af351).

The owner of the Proxy Admin and of Perpetual Yield Tranches' contracts  is the `Treasury League Multisig` which is [`0xFb3bD022D5DAcF95eE28a6B07825D4Ff9C5b3814`](https://etherscan.io/address/0xFb3bD022D5DAcF95eE28a6B07825D4Ff9C5b3814).

### Additional functions

As part of the Security Management policy, there is one more function on the `IdleCDO` contract:

{% tabs %}
{% tab title="Pause Guardian" %}
The pause guardian can pause, unpause and call `emergencyShutdown`.\
PYTs contracts can be paused during emergency situations.\
\
The pause guardian is currently the Idle Dev Multisig: [0xe8eA8bAE250028a8709A3841E0Ae1a44820d677b](https://etherscan.io/address/0xe8eA8bAE250028a8709A3841E0Ae1a44820d677b)
{% endtab %}
{% endtabs %}
