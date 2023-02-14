# Idle Smart Treasury (deprecated)

{% hint style="info" %}
Smart Treasury is [available here](https://pools.balancer.exchange/#/pool/0xcaf467dfe064a1f54e4ece8515ddf326b9be801e/)
{% endhint %}

### What is a Smart Treasury?

The research article released by [Placeholder VC](https://www.placeholder.vc/blog/2020/9/17/stop-burning-tokens-buyback-and-make-instead) in September 2020 proposes, for the first time, an automated buyback mechanism applied to Governance’s capital efficiency.

The process consists of deploying a [Balancer “smart pool”](https://docs.balancer.finance/guides/smart-pool-templates-gui) (referred to as _Smart Treasury_ for this use case) which acts as an automatic buyback machine and liquidity provider.

![](https://lh3.googleusercontent.com/vttodgUNS4-WdM\_3qHnI6quRFwGxzlVFYfTwHGl3cq1c8PxJmkcndkyaFB7b3ovDCuy4C99VlbVvIPoJva8iLG5TVn4iODoxlVXCYkJ5yBl5GQ3MA9Z-FKqJcC1azEUgjy4mLQ\_d)

### Smart Treasury Rationale

Since the $IDLE governance token launch, [the forum has hosted several discussions](https://gov.idle.finance/t/establish-a-smart-treasury/69) on how to increase the on-chain liquidity of the token and provide new use cases. The community analyzed liquidity mining programs in decentralized exchanges but preferred a Smart Treasury approach to incentivize liquidity provision in the long run.

A [snapshot poll](https://snapshot.org/#/idlefinance.eth/proposal/QmY91JDh8Z5KB2NJgJHTfoun472pAKegvSyRABBGBpK8X9) confirmed the community decision in moving forward with this proposal, and a [protocol grant](https://gov.idle.finance/t/grant-develop-a-smart-treasury/111) assigned the code development task. Lastly, the [peer review](https://gov.idle.finance/t/smart-treasury-peer-review/193) enabled safe program deployment that was executed with [IIP-2](https://gov.idle.finance/t/iip-2-add-a-smart-treasury-to-idle/211).\


#### Ecosystem benefits

A Smart Treasury contributes to increasing token liquidity and reducing swap slippage. The fees generated from swaps are added into the pool and re-invested back into the Smart Treasury.

In addition, the pool is eligible for $BAL tokens from Balancer, serving as an additional income stream for the Idle protocol.

#### How the Smart Treasury works

The [Smart Treasury](https://pools.balancer.exchange/#/pool/0xcaf467dfe064a1f54e4ece8515ddf326b9be801e/) is controlled by the IDLE governance, which can adjust parameters such as pool weights, token additions/removals, swap fees, and pause/unpause swaps.

The pool manages the IDLE-WETH pair, with a 90/10 token weights.

130,000 $IDLE from the Ecosystem Fund along with \~$40k in WETH from the FeeTreasury bootstrapped the Smart Treasury.

Protocol fees are now routed across these ecosystem contracts:

* **FeeCollector**: this contract collects protocol fees and swaps tokens (stablecoin, $COMP, $WBTC) into $WETH using Uniswap.
* **Smart Treasury**: it receives 80% of the profits received by FeeCollector (in WETH).
* **FeeTreasury**: it’s the old Governance treasury, and it receives 15% of the profits in WETH.
* **Rebalancer**: this contract manages funds allocation for Best-Yield and Risk-Adjusted streategies. Due to continuous protocol rebalances, this mechanism is expensive and required a seamless stream of ETH. It is currently receiving 5% of processed fees.\


Example of fee routing scheme:

![](https://lh3.googleusercontent.com/qJpWXmxF-o3wTW-7MZ3bhuE1JQduffZZXkv-9EL8k6YqKu\_-QhiizH24N333\_yoVnfQJlZhMDhgQCebxhDwGSGVHIyWCsFgxv8SDPt3yRrCwbMCqyshzFxjLJ6x\_FvooYiOoWcCy)

#### Technical specifications

Smart Pool Parameters:

* Weights: 90 / 10
* Tokens: $IDLE / $WETH
* Swapping fee: 0.5%\


FeeCollector address: [0xBECC659BFC6EDCA552FA1A67451CC6B38A0108E4](https://etherscan.io/address/0xBECC659BFC6EDCA552FA1A67451CC6B38A0108E4)

Smart Treasury address: [0x859e4d219e83204a2ea389dac11048cc880b6aa8](https://etherscan.io/address/0x4ff95c83e874df9029a665a0aba31828bada9596#code)

FeeTreasury address: [0x69a62c24f16d4914a48919613e8ee330641bcb94](https://etherscan.io/address/0x69a62c24f16d4914a48919613e8ee330641bcb94)

Rebalancer address: [0xb3c8e5534f0063545cbbb7ce86854bf42db8872b](https://etherscan.io/address/0xb3c8e5534f0063545cbbb7ce86854bf42db8872b)

SmartTreasuryBootstrap Address: [0x4ff95c83e874df9029a665a0aba31828bada9596](https://etherscan.io/address/0x4ff95c83e874df9029a665a0aba31828bada9596#code)

ConfigurableRightsPool (Smart Treasury) address: [0x859e4d219e83204a2ea389dac11048cc880b6aa8](https://etherscan.io/address/0x859e4d219e83204a2ea389dac11048cc880b6aa8)

Underlying bPool address: [0xcaf467dfe064a1f54e4ece8515ddf326b9be801e](https://etherscan.io/address/0xcaf467dfe064a1f54e4ece8515ddf326b9be801e)

The technical implementation can be found in this [GitHub repo](https://github.com/AsafSilman/idle-smart-treasury)

Multisig TX to transfer FeeCollector ownership to Governance: [0xad11f1cd69f53acb729e243b82e2b1a706eaa82a4b032dea5ca726dd312e563c](https://etherscan.io/tx/0xad11f1cd69f53acb729e243b82e2b1a706eaa82a4b032dea5ca726dd312e563c) \
