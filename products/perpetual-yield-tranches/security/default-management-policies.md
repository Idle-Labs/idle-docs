---
description: Products > Perpetual Yield Tranches > Security > Default management policies
---

# Default management policies

Yield Tranche strategies rely on various sources of yield. These sources can come from different markets that may have established default policies. Below we summarize the Idle processes that follow the given terms and conditions set by each protocol.

### Clearpool default policy

Yield Tranches interact with the Clearpool uncollateralized markets and due to this link are subject to the [default policy](https://docs.clearpool.finance/clearpool/how-it-works/protocol/default) of Clearpool.

> Clearpool’s smart contracts have been developed to incorporate a number of safety measures which protect both borrowers and lenders during black swan events.

Clearpool’s pools have a default mechanism based on each pool **utilization rate** which forces borrowers to repay loans if the pool’s utilization rate is too high.

| Utilization rate | Pool status      | Time limit                       |
| ---------------- | ---------------- | -------------------------------- |
| < 95%            | Active           | No time limit                    |
| > 95%            | High utilization | Until utilization = 99% or < 95% |
| > 99%            | Warning          | 120 hours                        |

Yield Tranches users can enter and exit the market anytime when the utilization rate of the underlying pool is lower than 99%. When the pool reaches 99% utilization, it enters automatically the _Warning_ mode and withdrawals for both borrowers and lenders will be halted.

The pool borrower has five days to deposit more capital and return the utilization rate below 95%, if not both the borrower and the pool will enter the _Default_ state.

#### Default state

When a Clearpool's pool is in _Default_, an **auction** will be triggered allowing participants to bid for the pool's cpTokens (the total debt of the pool).

Following the auction, a voting process will ensue, providing all cpToken holders with the opportunity to accept or reject the winning bid.

* If the majority vote to reject the bid, then each cpToken holder will be able to redeem their cpTokens for their proportionate share of the pool's insurance account and maintain their rights to legally pursue the defaulted borrower individually.
* If the majority vote to accept the bid, then each cpToken holder will be able to redeem their cpTokens for their proportionate share of the winning bid amount but will relinquish their rights to legally pursue the defaulted borrower to the winning bidder.

Please refer to Clearpool's [documentation](https://docs.clearpool.finance/clearpool/how-it-works/protocol/default) and its [terms and conditions](https://docs.clearpool.finance/clearpool/terms-and-conditions) for more information.

### Clearpool's Yield Tranches

In the case of a default scenario on a Clearpool's tranche, Idle will open a sub-space on [Snapshot](https://snapshot.org/#/idlefinance.eth) to gather Yield Tranches depositors' votes and will uniquely cast their preference on Clearpool.

Only depositors in the affected Clearpool pool will be able to vote in the dedicated sub-space.

* Senior depositors will be always able to share their sentiments on the bid
* Junior depositors will share their preferences depending on their weight in the tranches.\
  An automatic 30% slashing of Junior voting power will be applied in this scenario.&#x20;

| Senior weight | Junior weight | Senior voting | Junior voting |
| ------------- | ------------- | ------------- | ------------- |
| > 60%         | < 40%         | ✅             | ❌             |
| < 40%         | > 60%         | ✅             | ✅             |
