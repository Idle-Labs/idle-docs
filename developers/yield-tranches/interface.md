---
description: Developers > Yield Tranches > Interface
---

# Interface

### **IdleCDO**

The interface for the `IdleCDO` contract is the following:

```solidity
interface IdleCDO {
  function AATranche() external view returns(address);
  function BBTranche() external view returns(address);
  function AAStaking() external view returns(address);
  function BBStaking() external view returns(address);
  function strategy() external view returns(address);
  function strategyToken() external view returns(address);
  function token() external view returns(address);

  function allowAAWithdraw() external view returns(bool);
  function allowBBWithdraw() external view returns(bool);
  function fee() external view returns(uint256);
  function getApr(address _tranche) external view returns(uint256);
  function getContractValue() external view returns(uint256);
  function trancheAPRSplitRatio() external view returns(uint256);
  function getCurrentAARatio() external view returns(uint256);
  function tranchePrice(address _tranche) external view returns(uint256);
  function virtualPrice(address _tranche) external view returns(uint256);
  function getIncentiveTokens() external view returns(address[] memory);

  function depositAA(uint256) external returns(uint256);
  function depositBB(uint256) external returns(uint256);
  function withdrawAA(uint256) external returns(uint256);
  function withdrawBB(uint256) external returns(uint256);
}
```
