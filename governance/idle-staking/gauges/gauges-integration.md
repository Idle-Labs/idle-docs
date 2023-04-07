---
description: Governance > $IDLE staking > Gauges > Gauges integration
---

# Gauges integration

{% hint style="success" %}
Any smart contract is eligible for Idle Gauges, including AMM pools, on-top PYT products, and tools that empower Idle DAO to expand its ecosystem with new use cases.
{% endhint %}

The **gauges integration** process is **composed of 3 steps:**

### **1. Forum proposal**

Write a post labelled as follows: “**\[Gauges] - Proposal to add YOUR POOL NAME**”, publish it in the "[_Gauges whitelisting_](https://gov.idle.finance/c/governance/gauges/25)" governance forum subcategory and include these paragraphs as follows:

> _<mark style="color:blue;">**Abstract**</mark>_\
> Short description of why you are writing this proposal and the expected outcomes. This shouldn't be deeply technical but should be accessible to a casual community member.

> _<mark style="color:blue;">**Background**</mark>_\
> Link to website, documentation, Github page, (eventual) previous forum discussions, and other useful links to support the understanding of the proposal.

> _<mark style="color:blue;">**Motivation**</mark>_\
> Describe the proposed pool(s) and the corresponding protocol(s) that manages it. Clearly explain why this pool should be incentivized via $IDLE Gauges and what are the benefits for the Idle DAO. Providing tangible elements, like data from previous discussions and forum posts, would be beneficial. If the pool is not directly managed by Idle DAO, please provide information on the protocol’s Governance structure, audits, and pool’s metrics (TVL, longevity).

> _<mark style="color:blue;">**Specifications**</mark>_\
> Share the address of the pool and, if available, the address of the `LiquidityGaugeV3` contract.

> _<mark style="color:blue;">**Next steps**</mark>_\
> Inform the community when you plan to launch the Temperature check. The forum proposal can be moved to the temperature check phase at least after 3 days of discussion.

### **2. Temperature check**

{% hint style="info" %}
**Duration**: 3+ days of voting\
**Quorum**: 100,000 IDLE, as a weighted sum of $IDLE and stkIDLE votes\
**Majority**: the most voted option wins
{% endhint %}

Follow up your forum proposal with a reply that includes a [temperature check](../../idle-dao/governance-process/#2.-temperature-check).\
The aim is to taste the sentiment of the community about this potential whitelisting.

{% hint style="warning" %}
You need to have a **minimum of 100 tokens** in order to submit a temperature check.
{% endhint %}

You can launch a temperature check using the official Snapshot pages for [IDLE holders](https://snapshot.org/#/idlefinance.eth) and [stkIDLE holders](https://snapshot.org/#/staking.idlefinance.eth).

{% hint style="warning" %}
The 2 snapshots ($IDLE, stkIDLE) must have the same opening/closing date, equal description and voting options.
{% endhint %}

Idle Leagues will calculate the final $IDLE voting weights using the [approved calculator](https://docs.google.com/spreadsheets/d/1BnH9boRmBADuyquvDMh0AmQfF97Zj76sIENKtySLU8o/edit?usp=sharing), with the weighted votes of IDLE + stkIDLE.

The structure of the Temperature Check **is similar to the forum proposal one**, replacing the _Next Steps_ section with the following one:

> _<mark style="color:blue;">**Voting Options**</mark>_\
> Please cast your vote on one of the following options:\
> \
> **FOR**: Approve the whitelisting of YOUR POOL NAME in the Gauge Controller \
> **AGAINST**: Vote against the whitelisting of YOUR POOL NAME in the Gauge Controller **DISCUSS MORE**: Discuss more the proposal

The voting weight of stkIDLE is calculated in the form of weighted IDLE tokens as _(tot. IDLE stakes/tot. stkIDLE minted)tot. stkIDLE voting in the pool% of each option_.

### 3. On-chain Gauges whitelisting

Being the Treasury League multisig the owner of the `Gauge Controller` there is currently no need to open an IIP to deploy the new Gauges.&#x20;
