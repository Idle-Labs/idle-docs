---
description: Developers > Best Yield > Methods
---

# Methods

Idle allows you to lend different underlying assets (e.g. _DAI_, _USDC_) through the use of IdleTokens. So for each underlying asset supported there is a corresponding IdleToken (e.g. IdleDAI, IdleUSDC) implemented as an IdleToken instance.

### Core methods

[`mintIdleToken`](mintidletoken.md)**:** lends assets in Idle and receives IdleTokens back.

[`redeemIdleToken`](redeemidletoken-1.md)**:** redeems your assets and interests and burns IdleTokens.

[`redeemInterestBearingTokens`](redeeminterestbearingtokens.md)**:** redeems interest-bearing assets and burns IdleTokens.

[`rebalance`](rebalance.md)**:** reads allocations from IdleRebalancer and changes IdleToken pool allocations if needed.

[`tokenPrice`](tokenprice.md)**:** gets current IdleToken price without fees.

[`getAPRs`](getaprs.md)**:** gets APRs from all implemented protocols.

[`getAvgApr`](getavgapr.md)**:** gets current IdleToken average APR.

[`userAvgPrices`](useravgprices.md): gets avg price per IdleToken paid by a user (used to calculate earnings).

[`getGovTokensAmounts`](getgovtokensamounts.md): gets the number of redeemable governance tokens a user can withdraw.

[`getAllocations`](getallocations.md): gets an array with the last allocations.

[`getGovTokens`](getgovtokens.md): gets an array with the governance token addresses distributed.

[`getAllAvailableTokens`](getallavailabletokens.md): gets an array with all interest-bearing token addresses supported.

[`getProtocolTokenToGov`](getprotocoltokentogov.md): gets the governance token associated with a specific interest bearing token, if any.

[`tokenPriceWithFee`](tokenpricewithfee.md): gets the current IdleToken price for a specific user, counting fees
