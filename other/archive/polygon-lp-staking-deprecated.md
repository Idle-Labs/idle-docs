---
description: Governance > Idle DAO > $IDLE token > Use-cases > Polygon LP staking
---

# Polygon LP staking (deprecated)

### **What is LP Staking?**

Whenever liquidity is deposited into an AMM pool, specific tokens known as _liquidity providers tokens (_LP tokens) are minted and sent to the provider’s address. The proportion of the pool’s liquidity provided determines the number of liquidity tokens the provider receives. A liquidity pool is a core mechanism of AMM (Automated Market Makers), where at least two assets are deposited to form a trading pair.&#x20;

By staking your LP tokens into the Polygon LP Staking Program, users are entitled to receive additional rewards in the form of $IDLE.

### **LP Staking Program Rationale**

LP staking is a way to incentivize liquidity provisioning for IDLE/WETH pairs on decentralized exchanges. Idle Leagues [proposed](https://gov.idle.finance/t/3-phase-proposal-to-foster-liquidity-provision-lp-staking-analysis/681) this reward mechanism and Governance approved the deployment of the staking contracts. Idle Governance launched this LP staking program using the same model applied for [Ethereum LP Staking program](sushiswap-lp-staking.md) (Ampleforth Geyser model) to reward liquidity providers that became part of the Idle ecosystem on Polygon.

## **Program Outline**

{% hint style="info" %}
📅 Start date: **November 2, 2021**

📅 End date: **January 31rd, 2021** (3 months)

💼 Program budget: **20,000 $IDLE**

🔀 Staking model: [**Ampleforth Geyser model fork**](https://www.ampleforth.org/dapps/)

🛠 Solidity code: [**Idle Geyser Github**](https://github.com/Idle-Finance/idle-geyser)

⛓ Contract addresses: [**TokenGeyser**](https://polygonscan.com/address/0x0ac74Fe6f3C9123254418EEfcE37E4f7271a2b72)**,** [**Tokenizer**](https://polygonscan.com/address/0x59CDF902b6A964CD5dB04d28f12b774bFB876Be9)
{% endhint %}

### **How LP staking works**

Check out the [How to join LP staking on Polygon](../guides/idle-on-polygon/) guide.

### **Time-Weighted Distribution Mechanism**

The Geyser contract has a built-in mechanism intended to incentivize long-term liquidity providers. While there are no hard lockups for staking, there is a benefit to keeping your staked position longer.&#x20;

The reward multiplier linearly increases over the following periods:

* 0-1 month    -> from 1x up to 2x
* 1-2 months  -> from 2x up to 3x
* 2-3 months  -> 3x

By holding the funds in the staking contract until the final rewarding block, LPs will receive the token bonuses not accrued by LPs that withdrew funds earlier.

For detailed information on the staking model and FAQ, please visit the [Ethereum LP Staking page](sushiswap-lp-staking.md).
