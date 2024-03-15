---
description: Governance > Idle DAO > Governance process
---

# Governance process

{% hint style="info" %}
Any address with at least 130,000 IDLE (1% of the total supply) delegated to is able to propose IIPs (on-chain proposals), which are _executable codes._ The Timelock contract would then modify system parameters, logic, and contracts in a "time-delayed", "opt-out" upgrade pattern (as described in the [On-Chain Proposal section](./#4.-on-chain-proposal)).
{% endhint %}

Any proposal, idea, or initiative for the Idle protocol coming from a community member or Leagues' contributor follows a governance process composed of several steps:

<figure><img src="../../../.gitbook/assets/Governance process.png" alt=""><figcaption></figcaption></figure>

{% hint style="success" %}
Users can visit this [Syncvote page](https://app.syncvote.com/public/idle-governance-process-229/idle-dao-governance-process-300/320) to get an overview of the governance process
{% endhint %}

<figure><img src="../../../.gitbook/assets/image (90).png" alt=""><figcaption><p>Syncvote's preview of Idle DAO governance process</p></figcaption></figure>

### 1. Idea Discussion

Community members can propose early-stage ideas in the [Ideas and Improvements](https://gov.idle.finance/c/proposals/new-features-improvements/5) category to receive initial feedback. If community members have an already structured proposal, they can use the [Formal Proposals](https://gov.idle.finance/c/proposals/formal-proposal/21) category.

DAO contributors can use the templates available in the Governance Forum. Some categories provide a suggested template that can be found by clicking the "New Topic" button.&#x20;

**Timeline:** 2+ days of discussion

**Website:** [Idle Governance Forum](https://gov.idle.finance/)

<figure><img src="../../../.gitbook/assets/image (11).png" alt=""><figcaption></figcaption></figure>

### 2. Temperature Check

After a successful idea discussion, community members can create the associated Snapshot poll (off-chain action) to measure the sentiment of the community about the potential change.&#x20;

For the time being, contributors need to open two polls: one for IDLE votes and one for stkIDLE ones.

Users need to hold at least 100 IDLE to open a Snapshot poll.

**Timeline:** 3+ days of voting

**Website:** [Snapshot page](https://snapshot.org/#/idlefinance.eth) for IDLE holders and [Snapshot page](https://snapshot.org/#/staking.idlefinance.eth) for stkIDLE holders

{% hint style="warning" %}
In 2021, Idle DAO [approved](https://gov.idle.finance/t/voting-framework-for-stkidle-holders/567) a voting process update affecting stkIDLE holders only:

* A new [stkIDLE holders voting space ](https://snapshot.org/#/staking.idlefinance.eth)has been created on Snapshot.
* No quorum is required to validate the vot_e **off-chain**_
* The voting weight of stkIDLE is calculated in the form of weighted IDLE tokens as\
  \
  $$\large{\frac{\text{tot. IDLE staked}}{\text{tot. stkIDLE minted}}}\times \text{tot. stkIDLE voting} \times \text{\% on each option}$$

\
The sum of the voting weights cast by IDLE and stkIDLE holders represents the final snapshot results (votes results are reported in the official [calculator](https://docs.google.com/spreadsheets/d/1BnH9boRmBADuyquvDMh0AmQfF97Zj76sIENKtySLU8o/edit?usp=sharing)).
{% endhint %}

<figure><img src="../../../.gitbook/assets/image (78).png" alt=""><figcaption></figcaption></figure>

### 3. Proposal Formalization

After having reached a consensus in the Temperature Check, the initial proposer or another community member can submit the idea as an IIP in the [Proposals category](https://gov.idle.finance/c/proposals/6) in the Governance forum.&#x20;

DAO contributors can use the templates available in the Governance Forum. Some categories provide a suggested template that can be found by clicking the "New Topic" button.

**Timeline:** 2+ days of discussion

**Website:** [Idle DAO Governance](https://gov.idle.finance/)&#x20;

### 4. On-chain Proposal

The proposer or other DAO members can deploy on-chain the official proposal, which is broadcasted as _executable code_. It starts its journey in a pending state. Once the on-chain proposal is active, IDLE token holders cast their votes.&#x20;

DAO contributors can follow these [guides](../governance-guides/) to create a formal IIP.

{% hint style="info" %}
In case of an _**on-chain**_ poll, _stkIDLE_ votes should meet two minimum thresholds to make the poll valid to be cast on-chain:&#x20;

1. _20% of circulating stkIDLE voting the poll_
2. _at least 70% on the same option_&#x20;

If the poll quorum is reached, the Treasury multisign, which holds delegated votes, will broadcast the result on-chain with the entire voting balance.
{% endhint %}

**Quorum:** 4% of the total IDLE supply (\~520,000 IDLE) voting the pool

**Timeline:** 3 days of voting

**Website:** [Idle DAO Governance voting page on Tally](https://www.tally.xyz/gov/idle)

{% hint style="info" %}
If a proposal is successful, it can be queued for execution and, after 2 days, can be executed on-chain.&#x20;
{% endhint %}

<figure><img src="../../../.gitbook/assets/image (71).png" alt=""><figcaption></figcaption></figure>
