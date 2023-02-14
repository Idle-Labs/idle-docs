---
description: Developers > Security > Integration Standard Requirements
---

# Integration Standard Requirements

The [Security](integration-standard-requirements.md#security) and [Resiliency](integration-standard-requirements.md#resiliency) tables show the requirements to onboard a new yield source or an asset in the [Best Yield](../best-yield/) strategies.

{% hint style="info" %}
The Integration Standard Requirements made part of a due diligence process to evaluate new possible yield improvements.
{% endhint %}

### **Security**&#x20;

| Metrics                                                                                                                    | Minimum requirement                                     |
| -------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------- |
| Has a reputable company audited contracts, or are they fork of audited projects?                                           | 1 custom audit                                          |
| Months of activities since last contract update                                                                            | 3 months                                                |
| Are contracts immutable or upgradeable by admins? If upgradable, how many admins control the keys, and are they anonymous? | Immutable preferred, but answers evaluated case by case |
| Is there an emergency exit plan?                                                                                           | Evaluated case by case                                  |
| Are there protocol dependences?                                                                                            | Evaluated case by case                                  |
| Has the protocol/asset suffered losses in the past?                                                                        | Evaluated case by case                                  |

### **Resiliency**

| Metrics                                             | Minimum requirement                    |
| --------------------------------------------------- | -------------------------------------- |
| Current protocol TVL or asset market capitalization | $ 50M+                                 |
| Expected TVL or market capitalization in 3 months   | $ 100M+                                |
| Current protocol's or supported service' APYs       | +30% than Idle 30-day strategy average |
| Expected impact on APY when deploying Idle TVL      | Less than 10% change                   |
