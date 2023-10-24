---
description: Governance > IDLE staking
---

# IDLE staking

Staking allows users to lock their IDLE for a flexible period (up to 4 years) in return for a series of benefits. The contracts for IDLE staking are based on the [Curve VotingEscrow contracts](https://curve.readthedocs.io/), decided via [community vote](./#undefined).&#x20;

{% hint style="info" %}
The [Gauges voting](gauges/) and the [Liquidity providers' rewards boost](boost.md) are currently paused after [IIP-31](https://gov.idle.finance/t/iip-31-idle-incentives-distribution-update-euler-staking-pyts-as-new-yield-sources-for-by/1107/3). The staking reward program for stkIDLE holders is paused following [IIP-36](https://gov.idle.finance/t/iip-36-update-best-yield-usdc-weth-yield-sources-and-pause-the-staking-rewards-for-idle-stakers/1171).
{% endhint %}

### Lock details

Depending on the lock time, a specific amount of stkIDLE is generated from the IDLE locked. The lock scale is as follows

| IDLE   | Locking time | stkIDLE            |
| ------ | ------------ | ------------------ |
| 1 IDLE | 1 year       | 0.25 stkIDLE (25%) |
| 1 IDLE | 2 years      | 0.50 stkIDLE (50%) |
| 1 IDLE | 4 years      | 1 stkIDLE (100%)   |

stkIDLE linearly decreases from the lockup date to the end date. Only at the end of the lock time, it is possible to withdraw the starting locked IDLE tokens. The general formula to compute the stkIDLE balance at any point in time is:

$$
Q_{\text{stkIDLE}} = \frac{\text{lock time remaining in seconds}}{\text{max lock time in seconds}} \times Q_{\text{IDLE lock}}
$$

{% hint style="info" %}
Users can increase their stkIDLE by either staking more IDLE into their existing lock increasing their lock end date, or both. The **maximum lockup** duration is **4 years**.
{% endhint %}

**Example:** 5000 IDLE locked for 3 years and 2 months (with 30 days/month) would give:

$$
Q_{\text{stkIDLE}} = \frac{(3\times12 + 2)_{m} \times30_{d}\times24_{h}\times3600_s}{4\times365\times24\times3600} \times 5000
$$

$$
Q_{\text{stkIDLE}} = \frac{1140}{1460} \times 12 = 3904.1095
$$

As described above, the quantity of stkIDLE decreases constantly in proportion to the reduction in lock time (lock expiration), down to 0 at expiration. For example, two months after the initial lock, the stkIDLE holder from the example above would have a stkIDLE balance of:

$$
Q_{\text{stkIDLE}} = \frac{1080}{1460} \times 12 = 3698.6301
$$

### stkIDLE

The staking contract is implemented as a non-standard ERC-20 token, which is _**non-transferable**_ and can only be created by staking IDLE by calling`create_lock(uint256 _value, utin256 _unlock_time)`.

{% hint style="warning" %}
By default, smart contracts cannot participate in staking, as this would allow for trivial which could be implemented to circumvent the non-transferable nature of stkIDLE.

However, Smart contracts can be whitelisted via a governance proposal as described [here](staking-integration.md).
{% endhint %}

The IDLE voting power deposited in the staking contract is delegated to a community multisig, which is used to vote on governance proposals based on the [snapshot polls for stkIDLE token holders](https://snapshot.org/#/staking.idlefinance.eth).

{% hint style="success" %}
The community multisig is located at: [`0xb08696efcf019a6128ed96067b55dd7d0ab23ce4`](https://etherscan.io/address/0xb08696efcf019a6128ed96067b55dd7d0ab23ce4)
{% endhint %}
