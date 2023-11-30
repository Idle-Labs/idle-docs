---
description: Developers > Gauges > Architecture
---

# Architecture

A comprehensive description of the $IDLE Gauges system can be found [here](../gauges-1/)

{% content-ref url="../gauges-1/" %}
[gauges-1](../gauges-1/)
{% endcontent-ref %}

$IDLE gauges are based on the [Curve gauge](https://curve.readthedocs.io/dao-gauges.html) system with the following modifications.

The main difference is that $IDLE is not mintable, so a mechanism to release $IDLE linearly to Gauges is introduced which allows fine-grained control of the epochs and the inflation rate.\
Such a system replaced the CRV token with a contract that distributes $IDLE to Liquidity Gauges following parameters governed by the Idle DAO.

The $IDLE Gauge system consists of the following smart contracts:

* `LiquidityGauge`: specific for each pool, measures the liquidity provided by users.
* `GaugeController`: maintains a list of gauges and their respective weight. Allow users to vote for gauges.
* `Distributor`: used to distribute $IDLE rewards across epochs. Epochs have a length of one week and the total amount of rewards to be distributed in a given epoch (or week) can be changed during the previous epoch (or week).
* `DistributorProxy`: used by users to claim $IDLE rewards.
* `GaugeProxy`: allows setting additional rewards on top of liquidity gauges deposits.

**GitHub repository:** [https://github.com/Idle-Finance/idle-gauges](https://github.com/Idle-Finance/idle-gauges/)

Figure 1 shows a diagram of the contracts flow.

<figure><img src="../../../.gitbook/assets/Dev scheme.png" alt=""><figcaption></figcaption></figure>
