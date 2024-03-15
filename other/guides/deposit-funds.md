---
description: Other > Guides > Deposit funds through Idle
---

# Deposit funds through Idle

This tutorial will guide you in the process of depositing new funds into Idle.

### **Before you start**

To ensure a smooth process be sure to have the following items ready:

* A supported EVM wallet (_Metamask_, _Coinbase wallet_,  Rabby)
* Tokenized assets (DAI, USDC, USDT, WETH)
* Ether (ETH) to cover network fees (i.e. gas)

### Deposit&#x20;

1. Visit the Idle app at [app.idle.finance](https://app.idle.finance/#/dashboard)
2. In the header, select the _Earn_ tab and then choose either the [Best Yield](../../products/best-yield/) or the [Yield Tranches](../../products/yield-tranches/) vaults
3. In the top-right corner click on _Connect Wallet_ and then select the chain you want to deposit to from the drop-down menu
4. If the connection is successful, in the top right corner you will see the address of the wallet connected, as well as any IDLE balance (zero for new users)
5. Pick the vault you want to deposit to. For Yield Tranches you will need to select on which side (Senior/Junior) you want to deposit to
6. If it's the first time interacting with a vault, you will need first to approve the token spending
7. After the spending approval, you can deposit
8. The amount deposited will be transferred to the Idle smart contract and you will receive in back the LP token of the strategy you selected

{% hint style="warning" %}
Please note that you should not decrease the gas limit, and you should set the gas price to ensure the transaction completes promptly, otherwise, you will risk failed transactions and wasted gas fees.
{% endhint %}

If the Idle's website is down and you can't interact from the UI, you can always do so directly with the smart contracts. See the [Deposit funds through smart contracts](deposit-funds-sc.md) guide.&#x20;

Need further help? Check our [guides](./) list or get in contact on [Discord](https://discord.com/invite/mpySAJp).
