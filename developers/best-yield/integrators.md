---
description: Developers > Best Yield > Get integrated as yield source
---

# Get integrated as yield source

Currently, the Best Yield is integrated with Compound, and Aave as yield sources.&#x20;

If you want to promote a new integration, you can create an `IdleWrapper` that adhere to the following interface:

```javascript
interface ILendingProtocol {
  function mint() external returns (uint256);
  function redeem(address account) external returns (uint256);
  function nextSupplyRate(uint256 amount) external view returns (uint256);
  function getAPR() external view returns (uint256);
  function getPriceInToken() external view returns (uint256);
  function token() external view returns (address);
  function underlying() external view returns (address);
  function availableLiquidity() external view returns (uint256);
}
```

You can find the current wrappers for Compound as a reference on GitHub [here](https://github.com/Idle-Labs/idle-contracts/tree/develop/contracts/wrappers) (`IdleCompoundV2` is used for DAI only).

The `nextSupplyRate(uint256 amount)` is the rate that the protocol would have after a new deposit of underlying `amount` (e.g. if the current APR for DAI in Compound is 10% and then we deposit 100.000 DAI what would the next rate be?)

The Idle DAO implemented the [Integration Standard Requirements](../security/integration-standard-requirements.md), guidelines to help the Idle community, builders, protocol founders, and Idle liquidity providers to perform adequate due diligence on the current and future yield generating integrations and infrastructures.
