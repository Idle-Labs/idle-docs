# Deployed contracts

### Risk adjusted strategy

| **Contract**                    | **ABI**                                                              | **Address**                                                                                                           |
| ------------------------------- | -------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------- |
| IdleDAI Risk Adjusted (IIP-14)  | [JSON](https://github.com/Idle-Labs/idle-contracts/tree/develop/abi) | [0xa14eA0E11121e6E951E87c66AFe460A00BCD6A16](http://etherscan.io/address/0xa14eA0E11121e6E951E87c66AFe460A00BCD6A16)  |
| IdleUSDC Risk Adjusted (IIP-14) | [JSON](https://github.com/Idle-Labs/idle-contracts/tree/develop/abi) | [0x562C4fd96F0652F5Fcfa96b0a33088B5a6eAeE9B](https://etherscan.io/address/0x562c4fd96f0652f5fcfa96b0a33088b5a6eaee9b) |
| IdleUSDT Risk Adjusted (IIP-14) | [JSON](https://github.com/Idle-Labs/idle-contracts/tree/develop/abi) | [0x28fAc5334C9f7262b3A3Fe707e250E01053e07b5](http://etherscan.io/address/0x28fAc5334C9f7262b3A3Fe707e250E01053e07b5)  |

### Best Yield V3

| **CONTRACT** | **STRATEGY**  | **ABI**                                                                             | **ADDRESS**                                                                                                           |
| ------------ | ------------- | ----------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------- |
| IdleDAI      | Best Yield    | [JSON](https://github.com/bugduino/idle-contracts/blob/master/abi/IdleTokenV3.json) | [0x78751B12Da02728F467A44eAc40F5cbc16Bd7934](https://etherscan.io/address/0x78751b12da02728f467a44eac40f5cbc16bd7934) |
| IdleUSDC     | Best Yield    | [JSON](https://github.com/bugduino/idle-contracts/blob/master/abi/IdleTokenV3.json) | [0x12B98C621E8754Ae70d0fDbBC73D6208bC3e3cA6](https://etherscan.io/address/0x12b98c621e8754ae70d0fdbbc73d6208bc3e3ca6) |
| IdleUSDT     | Best Yield    | [JSON](https://github.com/bugduino/idle-contracts/blob/master/abi/IdleTokenV3.json) | [0x63D27B3DA94A9E871222CB0A32232674B02D2f2D](https://etherscan.io/address/0x63d27b3da94a9e871222cb0a32232674b02d2f2d) |
| IdleSUSD     | Best Yield    | [JSON](https://github.com/bugduino/idle-contracts/blob/master/abi/IdleTokenV3.json) | [0xe79e177d2a5c7085027d7c64c8f271c81430fc9b](https://etherscan.io/address/0xe79e177d2a5c7085027d7c64c8f271c81430fc9b) |
| IdleTUSD     | Best Yield    | [JSON](https://github.com/bugduino/idle-contracts/blob/master/abi/IdleTokenV3.json) | [0x51C77689A9c2e8cCBEcD4eC9770a1fA5fA83EeF1](http://etherscan.io/address/0x51C77689A9c2e8cCBEcD4eC9770a1fA5fA83EeF1)  |
| IdleWBTC     | Best Yield    | [JSON](https://github.com/bugduino/idle-contracts/blob/master/abi/IdleTokenV3.json) | [0xD6f279B7ccBCD70F8be439d25B9Df93AEb60eC55](http://etherscan.io/address/0xD6f279B7ccBCD70F8be439d25B9Df93AEb60eC55)  |
| IdleDAI      | Risk Adjusted | [JSON](https://github.com/bugduino/idle-contracts/blob/master/abi/IdleTokenV3.json) | [0x1846bdfDB6A0f5c473dEc610144513bd071999fB](https://etherscan.io/address/0x1846bdfdb6a0f5c473dec610144513bd071999fb) |
| IdleUSDC     | Risk Adjusted | [JSON](https://github.com/bugduino/idle-contracts/blob/master/abi/IdleTokenV3.json) | [0xcDdB1Bceb7a1979C6caa0229820707429dd3Ec6C](https://etherscan.io/address/0xcDdB1Bceb7a1979C6caa0229820707429dd3Ec6C) |
| IdleUSDT     | Risk Adjusted | [JSON](https://github.com/bugduino/idle-contracts/blob/master/abi/IdleTokenV3.json) | [0x42740698959761BAF1B06baa51EfBD88CB1D862B](https://etherscan.io/address/0x42740698959761baf1b06baa51efbd88cb1d862b) |

**Kovan V3:**

\*(rebalance not triggered, allocations are fixed on Compound)

| **CONTRACT** | Strategy   | **ABI**                                                                           | **ADDRESS**                                                                                                                 |
| ------------ | ---------- | --------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| IdleDAI      | Best Yield | [JSON](https://github.com/bugduino/idle-contracts/blob/master/abi/IdleToken.json) | [0x50d6350d2167bad558c2ee195c664030505ffce0](https://kovan.etherscan.io/address/0x50d6350d2167bad558c2ee195c664030505ffce0) |

**IdleTokenV3 Interface**

The following one is the interface for the `IdleTokenV3` contract. Note that IdleTokens are ERC20 so they will also support methods from the ERC20 standard like `approve` , `transfer`, `balanceOf`

```javascript
interface IIdleToken {
  function token() external returns (address underlying);
  function userAvgPrices(address) external returns (uint256 avgPrice);
  function mintIdleToken(uint256 _amount, bool _skipWholeRebalance) external returns (uint256 mintedTokens);
  function redeemIdleToken(uint256 _amount, bool _skipRebalance, uint256[] calldata _clientProtocolAmounts) external returns (uint256 redeemedTokens);
  function redeemInterestBearingTokens(uint256 _amount) external;
  function rebalance() external returns (bool);
  function rebalanceWithGST() external returns (bool);
  function openRebalance(uint256[] calldata _newAllocations) external returns (bool, uint256 avgApr);
  function tokenPrice() external view returns (uint256 price);
  function getAPRs() external view returns (address[] memory addresses, uint256[] memory aprs);
  function getAvgAPR() external view returns (uint256 avgApr);
  function getCurrentAllocations() external view returns (address[] memory tokenAddresses, uint256[] memory amounts, uint256 total);

  // Old V2 methods  
  function mintIdleToken(uint256 _amount, uint256[] calldata _clientProtocolAmounts) external returns (uint256 mintedTokens);
  function rebalance(uint256 _newAmount, uint256[] calldata _clientProtocolAmounts) external returns (bool);
}
```

****

### **V2**

**Mainnet V2:**

| **CONTRACT** | **ABI**                                                                           | **ADDRESS**                                                                                                           |
| ------------ | --------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------- |
| IdleDAI      | [JSON](https://github.com/bugduino/idle-contracts/blob/master/abi/IdleToken.json) | [0x10eC0D497824e342bCB0EDcE00959142aAa766dD](https://etherscan.io/address/0x10eC0D497824e342bCB0EDcE00959142aAa766dD) |
| IdleUSDC     | [JSON](https://github.com/bugduino/idle-contracts/blob/master/abi/IdleToken.json) | [0xeB66ACc3d011056B00ea521F8203580C2E5d3991](https://etherscan.io/address/0xeB66ACc3d011056B00ea521F8203580C2E5d3991) |



### **V1**

**Mainnet V1:**

| **CONTRACT** | **ABI**                                                                           | **ADDRESS**                                                                                                          |
| ------------ | --------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- |
| IdleSAI      | [JSON](https://github.com/bugduino/idle-contracts/blob/master/abi/IdleToken.json) | [0xAcf651Aad1CBB0fd2c7973E2510d6F63b7e440c9](http://etherscan.io/address/0xAcf651Aad1CBB0fd2c7973E2510d6F63b7e440c9) |
