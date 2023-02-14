---
description: >-
  Products > Perpetual Yield Tranches > Deposit > Live PYTs guides > QuickSwap
  cxETH-WETH
---

# QuickSwap cxETH-WETH

This tutorial will guide you in the process of depositing new funds on the Polygon Quickswap PYTs on top of the cxETH-WETH market.

To deposit into the cxETH-WETH pool, you should follow 3 steps:

1. Deposit funds on Celsius and bridge them on CelsiusX
2. Use QuickSwap to provide liquidity for the CelsiusX pairs
3. Deposit QuickSwap LP tokens in Idle's PYTs

## <mark style="color:purple;">Polygon</mark>

### 1. Deposit funds on Celsius and bridge them on CelsiusX

Celsius’s dashboard allows users to bridge wrapped ETH from the Celsius Network to Polygon right from within the Celsius app, free of charge. To bridge assets to Polygon using the CelsiusX Bridge, follow these simple steps:

1. Create an account on Celsius and get verified
2. Add funds to Celsius
3. Bridge assets from Celsius to the Polygon Network

An in-deep step by step guide can be found on the [CelsiusX Medium page](https://medium.com/@CelsiusX/how-to-receive-assets-using-the-celsiusx-bridge-to-polygon-8d2bce60cd7b).

### 2. Use QuickSwap to provide liquidity for the CelsiusX pairs

1. Connect wallet to QuickSwap
2. Swap CelsiusX tokens (i.e. cxETH for ETH)

Once you have equal parts of cxETH and ETH in your Polygon-compatible wallet, you’re ready to provide liquidity for the cxETH-ETH pool on QuickSwap. From QuickSwap’s user interface, select the Pool tab, and click on Add Liquidity.

In-deep step by step guides can be found on the CelsiusX Medium page [\[1\]](https://medium.com/@CelsiusX/how-to-swap-celsiusx-tokens-using-quickswap-on-polygon-8e558e0e9aa0), [\[2\]](https://medium.com/@CelsiusX/how-to-provide-liquidity-for-the-celsiusx-incentivized-pairs-using-quickswap-on-polygon-3201d70a2169).

### 3. Deposit QuickSwap LP tokens in Idle's PYTs

After having added funds to Celsius, bridged them to Polygon using CelsiusX and provided liquidity on the Celsius pairs on QuickSwap, you can finally go back to Idle Finance and enjoy the different risk-return tranches of the Perpetual Yield Tranches.&#x20;

* Choose the _Perpetual Yield Tranches strategy_ in the Idle dashboard sidebar.
* Choose whether to invest in Senior or Junior tranches.

{% hint style="success" %}
Using the **Senior Tranche**, in the case of a Smart-Contract breach, your funds will be covered by the funds deposited in the Junior Tranche.
{% endhint %}

{% hint style="warning" %}
Using the **Junior Tranche**, in the case of a Smart-Contract breach, your funds will be employed to cover eventual losses on the Senior Tranche.
{% endhint %}

![QuickSwap cxETH/WETH PYTs dashboard overview](<../../.gitbook/assets/image (47).png>)

1. Type in the amount you want to deploy on the tranche
2. Click on _Approve_ to approve the token spend limit (1st Tx)
3. Once the spending approval is confirmed, you will be able to deposit cxETH-ETH QuickSwap LP tokens
4. Click on _Deposit_ to deposit your funds (2nd Tx)
5. You will now own cxETH/wETH-LP tokens for the asset you deposited depending on the side of PYTs you chose (AA\_cxETH/wETH-LP for Senior, BB\_cxETH/wETH-LP for Junior)

{% hint style="info" %}
By staking the cxETH/wETH-LP tokens (either Senior or Junior) you can also obtain on-top staking rewards in the form of [dQUICK](https://polygonscan.com/token/0xf28164a485b0b2c90639e47b0f377b4a438a16b1).&#x20;
{% endhint %}
