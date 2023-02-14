---
description: >-
  This strategy allows you to automatically rebalance the best risk/yield
  allocation
---

# Risk Adjusted (deprecated)

The risk-adjusted allocation strategy provides a way to earn the best rate at the lowest risk level. The risk-management algorithm takes account of the total assets within a pool, incorporates underlying protocol rate functions and levels of supply and demand, skimming protocols with a bad score/rate mix, and finally determining an allocation that achieves the highest risk-return score possible after the rebalance happens.&#x20;

It has been developed in collaboration with DeFiScore, a framework for quantifying risk in permissionless lending pools. DeFiScore is a single, consistently comparable value for measuring protocol risk, based on factors including smart contract risk, collateralization, and liquidity. The model outputs a 0–10 score that represents the level of risk on a specific lending protocol (where 10 is the _upper bound = lowest risk_, and 0 is the _lower bound = highest risk_).

You can read more about the risk assessment model [here](https://github.com/ConsenSys/defi-score/blob/master/whitepaper.md).

### Technical details

With this strategy, we are trying to find the right balance between risk and returns. We are weighting score and apr based on `k` parameter. This can be modeled as follows:

$$
max\ q(x) = \sum_{i=0}^{n} \frac{x_i}{tot} * (\frac{\frac{nextRate_i(x_i)}{maxNextRate} + k * \frac{nextScore_i(x_i)}{maxNextScore}}{k + 1})
$$

where `n` is the number of lending protocols used, `x_i` is the amount (in underlying) allocated in protocol `i` , `nextRate(x_i)` is a function which returns the new APR for protocol `i` after supplying `x_i` ,`nextScore(x_i)` is a function which returns the new Score for protocol `i` after supplying `x_i`amount of underlying, `maxNextRate` is the highest rate of all implemented protocols after supplying `x_i` amount, same for `maxNextScore` with regard to the score, `tot` is total amount to rebalance, finally `k` is a coefficient for expressing weights of score and apr (k = 1  means equally weighted, currently k = 2 so score weights twice the APR).

$$
tot=\sum_{i=0}^{n} x_i
$$
