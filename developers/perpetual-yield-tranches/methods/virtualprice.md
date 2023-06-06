---
description: Developers > Yield Tranches > Methods > virtualPrice
---

# virtualPrice

This method calculates the current tranches price considering the interest that is yet to be split (i.e. the interest generated since the last interaction done on depositXX/withdrawXX/harvest).

This should always be $$\geq$$ of `tranchePrice`

### Function

```solidity
function virtualPrice(
    address _tranche
) public view returns (uint256 _virtualPrice)
```

### Parameters

<table><thead><tr><th width="293">Parameter</th><th>Description</th></tr></thead><tbody><tr><td><code>_tranche</code></td><td>Address of the requested tranche</td></tr></tbody></table>

### Return values

<table><thead><tr><th width="297">Value</th><th>Description</th></tr></thead><tbody><tr><td><code>_virtualPrice</code></td><td>Tranche price considering all interest since last interaction</td></tr></tbody></table>
