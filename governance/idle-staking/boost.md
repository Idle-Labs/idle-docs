---
description: Governance > $IDLE staking > LPs rewards boost
---

# Boost

Liquidity providers for PYTs (or whitelisted pools for Gauges) can boost their $IDLE rewards by holding stkIDLE. The boost can be up to **2.5x** the base rewards, based on the amount of stkIDLE holding.

The liquidity providers balance counted in the liquidity gauge is eligible to get boosted (depending on LPs vote weight) if LPs lock/stake their $IDLE (then as a result of this, holding stkIDLE).

Holding stkIDLE gives users more weight when collecting certain farming rewards. Part of the farming rewards that are distributed directly through the protocol is eligible for stkIDLE boosts.

{% hint style="danger" %}
External farming promoted by other external protocols (such as Sushi, Onsen) is typically not available for stkIDLE boosts since it is independent of the Idle protocol itself.
{% endhint %}

In a given gauge, owning stkIDLE increases a user share of the pool thus increasing the rewards received. **Users holding no stkIDLE are anyway considered as providing 100% of their liquidity**. If a user owns enough stkIDLE, the user can be considered as bringing up to 250% of its original liquidity (or a 2.5x boost compared to the original 100%).

The 2.5x multiplier in liquidity provided translates into a boost on rewards depending on the total liquidity provided in the pool and how it is considered by the gauge boost calculator.

### Boosting formulae

Following the approach of the [Angle protocol](https://docs.angle.money/governance/veangle/boost), we set&#x20;

$$
liquidity_{user} = \text{user liquidity in the pool} \qquad 
    liquidity_{pool} = \text{total liquidity in the pool} \\
    stkIDLE_{user} = \text{user stkIDLE balance} \qquad
    stkIDLE_{tot\,supply} = \text{total stkIDLE supply}
$$

The boost mechanism calculates user **earning weight** by taking the smaller amount of two values: the first value is the amount of liquidity the user is providing, while the second one is the amount of his maximum earning weight

$$
\min\left(liquidity_{user} + 1.5 \times liquidity_{pool} \times \frac{stkIDLE_{user}}{stkIDLE_{tot\,supply}} ; 2.5 \times liquidity_{user}\right) \tag{1}
$$

To achieve the maximum boost on rewards, the user needs to get 100% of the provided liquidity taken into account by the protocol. That is an equivalent share of stkIDLE supply bigger or equal to the share of liquidity in the pool

$$
\frac{stkIDLE_{user}}{stkIDLE_{tot\,supply}} \ge \frac{liquidity_{user}}{liquidity_{pool}}
$$

{% hint style="info" %}
The gauge model considers a user with a share of stkIDLE higher than his share of liquidity provision in the pool as having 2.5x more liquidity than another user with no stkIDLE holding (in the same pool).
{% endhint %}

### Boosting examples

#### Example 1: One user with the complete majority of stkIDLE share in the pool

Users $$x$$ and $$y$$ provide the same liquidity (100 stETH) in the senior tranche of the Lido pool and stake their senior tranche tokens (i.e. AA\_wstETH) receiving an equal amount of rewards each (50% of $IDLE daily emission).

| User      | LP                     | % rewards                           |
| --------- | ---------------------- | ----------------------------------- |
| $$x$$     | 100 stETH (AA\_wstETH) | $$\frac{100}{200} = 0.5 \to 50\%$$  |
| $$y$$     | 100 stETH (AA\_wstETH) | $$\frac{100}{200} = 0.5 \to 50\%$$  |
| LIDO pool | 200 stETH              | $$100\%$$                           |

Now, let’s suppose that user __ $$x$$ owns the total supply of stkIDLE in the pool (100%). The gauges boost calculator, using Equation (1), will consider user $$x$$ as bringing 250 stETH of liquidity in the pool, consequently boosting $$x's$$ rewards by a multiplier of 1.42

| User (stkIDLE)             | Boosted liquidity        | % pool holding                              |
| -------------------------- | ------------------------ | ------------------------------------------- |
| $$x$$ with 100% of stkIDLE | $$100 \times 2.5 = 250$$ | $$\frac{250}{250 + 100} \times 100 = 71\%$$ |
| $$y$$ with 0% of stkIDLE   | $$100 \times 1 = 100$$   | $$\frac{100}{250 + 100} \times 100 = 29\%$$ |

$$
multiplier(x) = 1 + \left(\frac{71\% - 50\%}{50\%}\right) = 1.42
$$

#### Example 2: Two users with a significant difference in stkIDLE holding

User $$x$$ provides 100 stETH and user $$y$$ provides 9900 stETH in the senior tranche of the Lido pool. Assuming no stkIDLE holdings, user $$x$$ will earn 1% of the total pool rewards (AA\_wstETH) and user $$y$$ 99%.

| User      | LP          | % rewards                               |
| --------- | ----------- | --------------------------------------- |
| $$x$$     | 100 stETH   | $$\frac{100}{10000} = 0.01 \to 1\%$$    |
| $$y$$     | 9900 stETH  | $$\frac{9900}{10000} = 0.99 \to 99\%$$  |
| LIDO pool | 10000 stETH | $$100\%$$                               |

User $$x$$ decides to stake his $IDLE and now owns 1% of the stkIDLE supply in the pool, assuming$$stkIDLE_{user} \ge liquidity_{user}$$. The gauges boost calculator, using Equation (1) will consider user $$x$$ as bringing 250 stETH of the liquidity in the pool, consequently boosting $$x's$$ rewards by a multiplier of 2.5.

| User (stkIDLE)           | Boosted liquidity        | % pool holding                                |
| ------------------------ | ------------------------ | --------------------------------------------- |
| $$x$$ with 1% of stkIDLE | $$100 \times 2.5 = 250$$ | $$\frac{250}{250 + 9900} \times 100 = 2.5\%$$ |

$$
multiplier(x) = 1 + \left(\frac{2.5\% - 1\%}{1\%}\right) = 2.5
$$

Similarly, if user $$y$$ stakes her $IDLE, she would own 1% of the stkIDLE supply of the pool, as well. The gauges boost calculator, using Equation (1) will consider user $$y$$ as bringing 1005 stETH of the liquidity in the pool, consequently boosting $$y's$$ rewards by a multiplier of 2.5.

| User (stkIDLE)           | Boosted liquidity                              | % pool holding                                       |
| ------------------------ | ---------------------------------------------- | ---------------------------------------------------- |
| $$y$$ with 1% of stkIDLE | $$9900 + 1.5 \times 10000 \times 1\% = 10050$$ | $$\frac{10050}{250+ 10050} \times 100 \approx 98\%$$ |

Share of earnings for user $$y$$ would go from 97.54% to: $$\frac{10050}{250+ 10050} = 97.57\%$$&#x20;

{% hint style="info" %}
Users who own bigger shares of the pool need to hold bigger shares of the stkIDLE to boost significantly their rewards.&#x20;
{% endhint %}
