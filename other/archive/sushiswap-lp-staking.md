---
description: Governance > Idle DAO > $IDLE token > Use-cases > Ethereum LP Staking
---

# Ethereum LP staking (deprecated)

{% hint style="warning" %}
**Please note that Ethereum LP staking program ended on October 23rd, 2021**
{% endhint %}

### **What is LP staking?**

Whenever liquidity is deposited into an AMM pool, specific tokens known as _liquidity providers tokens (_LP tokens) are minted and sent to the provider’s address. The proportion of the pool’s liquidity provided determines the number of liquidity tokens the provider receives. A liquidity pool is a core mechanism of AMM (Automated Market Makers), where at least two assets are deposited to form a trading pair.&#x20;

By staking your LP tokens into the Idle LP Staking Program, users are entitled to receive additional rewards in the form of $IDLE.

### **LP Staking program rationale**

LP staking is a way to incentivize liquidity provisioning for IDLE/ETH pairs on decentralized exchanges. The Idle Governance [extensively discussed](https://gov.idle.finance/t/final-discussion-for-the-lp-staking-implementation-for-idle/346) this reward mechanism and executed [IIP-6](https://gov.idle.finance/t/iip-6-lp-staking-fund-transfer-treasury-transfer-for-protocol-operations/409) to let the Pilot League deploy the staking contracts. Idle Governance launched an LP staking program to reward liquidity providers and enable LPs to become part of the Idle ecosystem.

### **Program outline**

📅 Start date: **April 26, 2021**

📅 End date: **October 23rd, 2021** (6 months)

💼 Program budget: **180,000 $IDLE**



🔀 Staking model: [**Ampleforth Geyser model fork**](https://www.ampleforth.org/dapps/)

🛠 Solidity code: [**Idle Geyser Github**](https://github.com/Idle-Finance/idle-geyser)

⛓ Contract addresses: [**TokenGeyser**](https://etherscan.io/address/0xcc0b9f7ed0e6bc7c2e69dbd247e8420f29aeb48d#code)**,** [**Tokenizer**](https://etherscan.io/address/0x076ff8e6402b02855ff82119b53e59bbdd67f0ee#code)

### **How does LP staking work?**

1. Deposit `WETH` and `IDLE` into [IDLE-WETH SushiSwap pool](https://analytics.sushi.com/pairs/0xa7f11e026a0af768d285360a855f2bded3047530)
2. Receive `SUSHI LP` tokens
3. Stake `SUSHI LP` tokens in the [Idle staking page](https://idle.finance/#/dashboard/stake), and monitor stats and accrued tokens
4. Withdraw your `SUSHI LP` tokens anytime and get your `IDLE` rewards

### **Time-Weighted distribution mechanism**

The Geyser contract has a built-in mechanism intended to incentivize long-term liquidity providers. While there are no hard lockups for staking, there is a benefit to keeping your staked position longer.&#x20;

The reward multiplier linearly increases over the following periods:

* 0-2 months -> from 1x up to 2x
* 2-4 months -> from 2x up to 3x
* 4-6 months -> 3x

![](../../.gitbook/assets/IdleGyserTW\_distribution\_schedule.png)

By holding the funds in the staking contract until the final rewarding block, LPs will receive the token bonuses not accrued by LPs that withdrew funds earlier.

**Example:**&#x20;

`User A, B, and C join the LP staking at the program launch and with the same stake.` \
\
`- User A withdraws funds in the third month, receiving a 2.5x multiplier.` \
\
`- User B and C hold the deposit until the end: on top of their multiplier (3x), they will split the 0.5x bonus (referred to 3 months) left by user A according to their pool weights.`\
\
`The final multiplier will be 3.125x per user.`

### FAQs

#### #Who holds the funds?

SushiSwap smart contracts hold IDLE and WETH funds, and LP tokens are deposited into Idle protocol’s smart contracts. The address that you used to deposit LP tokens is the only one entitled to withdraw the funds. The original Ampleforth geyser contracts were [audited by CertiK](https://github.com/ampleforth/ampleforth-audits/tree/master/token-geyser).

#### #How does the process work from a technical perspective?

The **end-end flow for staking** is:

* Sushi LP Token (SLP) → SLP token staked in Tokenizer, wrapped Idle Sushi LP (wiSLP) token minted → wiSLP token is staked in IdleGeyser contract, accumulating IDLE rewards based on time-weighted multiplier

![](../../.gitbook/assets/LP\_staking\_flow.png)

The **end-end flow for unstaking** is:

* wiSLP token unstaked from geyser → IDLE rewards sent to user (based on time-weighted multiplier) → wiSLP token burned, SLP token unstaked from Tokenized and sent back to user

![](../../.gitbook/assets/LP\_unstaking\_flow.png)

This process has been [automated in Idle dashboard](https://idle.finance/#/dashboard/stake), so as a user you won’t have to worry about this detail.
