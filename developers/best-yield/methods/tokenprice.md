---
description: Developers > Best Yield > tokenPrice
---

# tokenPrice

This method returns the current $IDLE token price, in underlying (e.g. DAI) terms.

{% hint style="info" %}
Note: the **price does not include fees.** If you need the token price with fee you should take a look at the `tokenPriceWithFee` method.
{% endhint %}

### Function

```solidity
function tokenPrice(
) external view returns (uint256 price);
```

### Return values

| Value   | Description                       |
| ------- | --------------------------------- |
| `price` | Return the underlying token price |

{% hint style="info" %}
Note: $IDLE tokens for Risk-Adjusted strategy do not have a `tokenPriceWithFee` method so you need to take account of those on your side or use [this](https://etherscan.io/address/0x04Ce60ed10F6D2CfF3AA015fc7b950D13c113be5#code) helper.
{% endhint %}

[Here](https://twitter.com/emilianobonassi/status/1344419709597458432) you can find a Twitter thread with more info about Idle Token Helper and also a [follow up here](https://twitter.com/emilianobonassi/status/1344550511538802688).
