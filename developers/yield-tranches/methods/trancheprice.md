---
description: Developers > Yield Tranches > Methods > tranchePrice
---

# tranchePrice

This method returns the last tranche price saved on the last smart contract interaction (it may not include interest earned since the last update. For an up-to-date price, check the [virtualPrice](virtualprice.md) method).

### Function

```solidity
function tranchePrice(
    address _tranche
) external view returns (uint256)
```

### Parameters

<table><thead><tr><th width="264">Parameter</th><th>Description</th></tr></thead><tbody><tr><td><code>_tranche</code></td><td>Tranche address</td></tr></tbody></table>

### Return values

<table><thead><tr><th width="266">Value</th><th>Description</th></tr></thead><tbody><tr><td><code>_tranchePrice</code></td><td><p>Last saved tranche price. </p><p>This price gets updated right before each deposit and redeems call in order to split the interest accrued since the last interaction. </p></td></tr></tbody></table>
