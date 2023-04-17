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

| Parameter  | Description     |
| ---------- | --------------- |
| `_tranche` | Tranche address |

### Return values

| Value           | Description                                                                                                                                                                    |
| --------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `_tranchePrice` | <p>Last saved tranche price. </p><p>This price gets updated right before each deposit and redeems call in order to split the interest accrued since the last interaction. </p> |
