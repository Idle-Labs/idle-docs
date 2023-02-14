---
description: Developers > Perpetual Yield Tranches > Methods
---

# Methods

## Core Methods

[`AAStaking`](aastaking.md): returns the address of the StakingRewards contract for AA tranche staking.

[`BBStaking`](bbstaking.md): returns the address of the StakingRewards contract for BB tranche staking.

[`AATranche`](aatranche.md): returns the address of the AA Tranche token contract (ERC20).

[`BBTranche`](bbtranche.md): returns the address of the BB Tranche token contract (ERC20).

[`depositAA`](depositaa.md): transfers underlying from the user to the contract and mint AA tranche tokens for the user.

[`depositBB`](depositbb.md): transfers underlying from the user to the contract and mint BB tranche tokens for the user.

[`fee`](fee.md): returns the Performance Fee.

[`getAPR`](getapr.md): returns the current APR for a tranche based on `trancheAPRSplitRatio` and the current AA ratio.

[`getContractValue`](getcontractvalue.md): calculates the current total value locked (in underlyings).

[`getCurrentAARatio`](getcurrentaaratio.md): returns the AA tranches ratio (in underlying value) considering all interest.

[`getIncentiveTokens`](getincentivetokens.md): returns an array of tokens used to incentive tranches via `StakingRewards`.

[`lastNAVAA`](lastnavaa.md): returns the last saved net asset value (TVL) for AA tranches only.

[`lastNAVBB`](lastnavbb.md): returns the last saved net asset value (TVL) for BB tranches only.

[`strategy`](strategy.md): returns the address of the lending strategy used for deploying capital.

[`strategyToken`](strategytoken.md): returns the interest bearing asset of the lending provider used in this IdleCDO (e.g. idleDAI).

[`token`](token.md): returns the underlying asset address deposited by the user (eg DAI).

[`trancheAPRSplitRatio`](trancheaprsplitratio.md): returns the set interest split ratio between senior and junior holders.

[`tranchePrice`](trancheprice.md): returns the last tranche price saved on the last smart contract interaction (it may not include interest earned since the last update, for an up to date price check the [virtualPrice](virtualprice.md) method).

[`virtualPrice`](virtualprice.md):  calculates the current tranches price considering the interest that is yet to be split (i.e. the interest generated since the last interaction done on depositXX/withdrawXX/harvest).

[`withdrawAA`](withdrawaa.md): allows a user to burn a AA tranche token and get the principal + interest back (if no emergency shutdown is in progress).

[`withdrawBB`](withdrawbb.md): allows a user to burn a BB tranche token and get the principal + interest back (if no emergency shutdown is in progress).
