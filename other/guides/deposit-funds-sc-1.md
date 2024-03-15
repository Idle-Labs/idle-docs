---
description: Other > Guides > Redeem funds through smart contracts
---

# Redeem funds through smart contracts

This tutorial will guide you in the process of redeeming funds from Idle directly from the smart contracts in case the website has limited access or is down.&#x20;

### A. Redeem

1. Visit the vaults' addresses of [Best Yield](../../developers/best-yield/deployed-contracts.md) and [Yield Tranches](../../developers/yield-tranches/deployed-contracts/) and select the one you want to deposit to. For YTs, you need to always use the contract tagged as _CDO_
2. Click on the _Contract_ tab, and then on _Write as Proxy_
3. The majority of contracts have an implementation ABI, you should use it, i.e. click on the contract link next to the "ABI for the implementation contract at"
4. Click again on _Write Contract_ and on _Connect to Web3_ to connect your wallet
5. Select the function [`redeemIdleToken`](../../developers/best-yield/methods/redeemidletoken-1.md) for BY or [`withdrawAA`](../../developers/yield-tranches/methods/withdrawaa.md), [`withdrawBB`](../../developers/yield-tranches/methods/withdrawbb.md) for YTs (where AA stands for Senior and BB for Junior)
6. Input the amount you want to redeem unit converted. You can use [this tool](https://etherscan.io/unitconverter) to easily convert in multiple formats. Idle LP tokens have always 18 decimals (10^-18).&#x20;
7.  Click on _Write_ and execute your Tx. If successful, you will see an outflow of the LP token selected and an inflow of the principal token. \


    <figure><img src="../../.gitbook/assets/image (102).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
The same process can be done through a multisig, i.e. a smart contract, by building the Tx using the _Transaction Builder_ app. Safe fetches automatically the proper ABI of the contract.
{% endhint %}

Need further help? Check our [guides](./) list or get in contact on [Discord](https://discord.com/invite/mpySAJp).
