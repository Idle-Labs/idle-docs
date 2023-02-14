---
description: Governance > $IDLE staking > Staking integration
---

# Staking integration

Externally Owned Accounts (EOA) were the only ones enabled to interact with the $IDLE staking contract and lock $IDLE (locking system).&#x20;

The implementation of [IIP-22](https://gov.idle.finance/t/iip-22-stkidle-whitelisting-process-implementation/962) introduced the _`SmartWalletChecker`_ contract to manage the contracts interacting with the $IDLE staking module letting Smart Contracts (such as multisig wallets) mint stkIDLE, as well.&#x20;

{% hint style="info" %}
The minting limitation for Smart Contracts was initially introduced to avoid trivial that could have circumvented the non-transferable nature and tokenization of stkIDLE that could nullify the effectiveness of its locking.&#x20;
{% endhint %}

This approach created an on-top whitelisting layer, with no core changes to the underlying DAO governance infrastructure, similar to what [Curve implemented](https://gov.curve.fi/t/cip-3-add-smartwalletwhitelist-with-dao-maintained-whitelist/25).

The Treasury League, acting as an owner of the `SmartWalletChecker`, is temporarily processing the whitelisting requests with the final aim to fully decentralize the process. The Treasury League will act as a facilitator to reduce the frictions to onboard new smart contract-based liquidity providers.&#x20;

{% hint style="info" %}
**The TL will accept all the requests unless there are clear proofs that a specific whitelisting would harm the protocol**. In such cases, the issues will be publicly discussed in the Idle DAO Governance with the community.
{% endhint %}

{% hint style="success" %}
The`SmartWalletChecker`contract address is: [`0x2D8b5b65c6464651403955aC6D71f9c0204169D3`](https://etherscan.io/address/0x2D8b5b65c6464651403955aC6D71f9c0204169D3)``
{% endhint %}



The **$IDLE staking contracts integration** process is mainly composed of **2 steps**:

### 1. Leagues check&#x20;

Smart contracts interested to interact with the $IDLE staking contract should [get in contact](https://discord.gg/mpySAJp) with the Leagues, first. After a security check, Leagues will add the new contract address to the `SmartWalletChecker`.

### 2. Address whitelisting

Leagues broadcast the whitelisting TX to enable the address that applied to interact with the $IDLE staking module and publish in the [Governance forum](https://gov.idle.finance/) the new whitelisted address to let DAO track new and past additions.
