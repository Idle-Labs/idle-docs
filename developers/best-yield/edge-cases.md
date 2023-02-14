---
description: Developers > Best Yield > Edge cases
---

# Edge cases

If one of the implemented lending providers does not have all the liquidity requested available when the `redeemIdleToken` is called and no unlent balance is left then the tx will revert.&#x20;

The only options are to either wait for new liquidity to be returned (the rebalance method already takes this into account and tries to redeem as much as possible) or reduce the redeemed amount.
