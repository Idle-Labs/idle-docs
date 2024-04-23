---
description: Products > Best Yield
---

# Best Yield

<figure><img src="../../.gitbook/assets/BY 1.png" alt=""><figcaption></figcaption></figure>

The Best Yield vaults are single-sided liquidity pools that aim to offer the highest yield for supported stablecoins at all times. This is achieved by programmatically allocating these assets across several lending pools.&#x20;

Best Yield benefits users by socializing gas costs, automating the yield generation and rebalancing process, and automatically shifting capital as opportunities arise. End users and integrators do not need proficient knowledge of the underlying protocols or DeFi.&#x20;

Users' funds are pooled together in the main contract (one for each supported token) to minimize gas expenses for reallocating funds and provide, at the same time, the highest aggregated APY for all pooled funds.&#x20;

Interest rates are constantly monitored, and an off-chain bot computes the exact allocations to maximize aggregated APY. If, for a given pool, the current on-chain allocations are different from the newly calculated one, the smart contract receives new allocations, and the pool gets rebalanced.

{% hint style="info" %}
This strategy has been battle-tested since mid-2019, and it’s considered one of the most resilient in the entire DeFi space.
{% endhint %}
