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

<table><thead><tr><th width="301">Parameter</th><th>Description</th></tr></thead><tbody><tr><td><code>_protocolToken</code></td><td>Address of one of the interest-bearing tokens currently used</td></tr></tbody></table>

### Return values

<table><thead><tr><th width="305">Value</th><th>Description</th></tr></thead><tbody><tr><td><code>address</code></td><td>An array of the address of the governance token</td></tr></tbody></table>
