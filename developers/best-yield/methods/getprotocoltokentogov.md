---
description: Developers > Best Yield > getProtocolTokenToGov
---

# getProtocolTokenToGov

This method gives the governance token associated to a protocol token, e.g. `protocolTokenToGov[cDAI]` == COMP address.

```solidity
function getProtocolTokenToGov(
    address _protocolToken
) external view returns (address);
```

### Parameters

| Parameter        | Description                                                  |
| ---------------- | ------------------------------------------------------------ |
| `_protocolToken` | Address of one of the interest-bearing tokens currently used |

### Return values

| Value     | Description                                     |
| --------- | ----------------------------------------------- |
| `address` | An array of the address of the governance token |
