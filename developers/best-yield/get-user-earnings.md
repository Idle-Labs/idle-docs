---
description: Developers > Best Yield > Get user earnings
---

# Get user earnings

Tracking earnings on Idle is easy, you just need the avg buy price of the IdleTokens, the amount of IdleTokens held by a user and the current price.

IdleToken contract saves and updates the `userAvgPrices` mapping which contains the avg price paid for each IdleToken of a user, so to calculate earnings (in underlying) one can do the following:

```javascript
address user = <address_of_user>;
IIdleToken idleDAI = IIdleToken(<address_idle_token>);
uint256 userBalance = idleDAI.balanceOf(user);
uint256 avgCost = userBalance.times(idleDAI.userAvgPrices(user)).div(10**18);
uint256 currentValue = userBalance.times(idleDAI.tokenPriceWithFee()).div(10**18);
uint256 earnings = currentValue.minus(avgCost);
```

{% hint style="info" %}
Note: `tokenPriceWithFee` is available only for IdleToken of the Best yield strategy. For the Risk adjusted strategy fee must be accounted on the integrators side or by using [this helper](https://etherscan.io/address/0x04Ce60ed10F6D2CfF3AA015fc7b950D13c113be5#code).\
\
[Here](https://twitter.com/emilianobonassi/status/1344419709597458432) you can find more info and also a [follow up here](https://twitter.com/emilianobonassi/status/1344550511538802688).
{% endhint %}
