---
description: Developers > Perpetual Yield Tranches > Methods > virtualPrice
---

# virtualPrice

This method calculates the current tranches price considering the interest that is yet to be split (i.e. the interest generated since the last interaction done on depositXX/withdrawXX/harvest).

This should always be >= of `tranchePrice`

### Function

```solidity
function virtualPrice(
    address _tranche
) public view returns (uint256 _virtualPrice)
```

### Parameters

| Parameter  | Description                      |
| ---------- | -------------------------------- |
| `_tranche` | Address of the requested tranche |

### Return values

| Value           | Description                                                   |
| --------------- | ------------------------------------------------------------- |
| `_virtualPrice` | Tranche price considering all interest since last interaction |
