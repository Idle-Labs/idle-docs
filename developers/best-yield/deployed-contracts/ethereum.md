---
description: Developers > Best Yield > Deployed contracts > Ethereum
---

# Ethereum

You can find the currently deployed instances and ABIs of the Best Yield and LP staking contracts at the following addresses. The ABI of the Best Yield contract can be found here: [JSON](https://github.com/Idle-Labs/idle-contracts/tree/develop/abi).

### **Best Yield**

Aave, Compound, and whitelisted [Senior Yield Tranches](../../yield-tranches/deployed-contracts/ethereum.md) as underlying markets

<table><thead><tr><th width="205">Ticker</th><th>Address</th></tr></thead><tbody><tr><td>idleDAI_Yield</td><td><a href="https://etherscan.io/address/0x3fe7940616e5bc47b0775a0dccf6237893353bb4">0x3fe7940616e5bc47b0775a0dccf6237893353bb4</a></td></tr><tr><td>idleUSDC_Yield</td><td><a href="http://etherscan.io/address/0x5274891bEC421B39D23760c04A6755eCB444797C">0x5274891bEC421B39D23760c04A6755eCB444797C</a></td></tr><tr><td>idleUSDT_Yield</td><td><a href="http://etherscan.io/address/0xF34842d05A1c888Ca02769A633DF37177415C2f8">0xF34842d05A1c888Ca02769A633DF37177415C2f8</a></td></tr></tbody></table>

### ERC-4626 wrappers for Best Yield tokens

<table><thead><tr><th width="120">Type</th><th width="184">Ticker</th><th>Address</th></tr></thead><tbody><tr><td>Junior</td><td>idleDAI_Junior_w</td><td><a href="https://etherscan.io/address/0x0c80F31B840C6564e6c5E18f386FaD96b63514cA">0x0c80F31B840C6564e6c5E18f386FaD96b63514cA</a></td></tr><tr><td>Junior</td><td>idleUSDC_Junior_w</td><td><a href="https://etherscan.io/address/0xc3dA79e0De523eEf7AC1e4ca9aBFE3aAc9973133">0xc3dA79e0De523eEf7AC1e4ca9aBFE3aAc9973133</a></td></tr><tr><td>Junior</td><td>idleUSDT_Junior_w</td><td><a href="https://etherscan.io/address/0x544897a3b944fdeb1f94a0ed973ea31a80ae18e1">0x544897a3b944fdeb1f94a0ed973ea31a80ae18e1</a></td></tr></tbody></table>

### **Deprecated strategies**

Multiple versions of the BY vaults were released over time. Please refer to the list below to understand the BY type

* OG BY = vaults using only Aave and Compound as underlying markets
* Senior BY = vaults using Aave, Compound, and [Senior tranches](../../yield-tranches/deployed-contracts/ethereum.md) as underlying markets
* Junior BY = vaults using [Junior tranches](../../yield-tranches/deployed-contracts/ethereum.md) as underlying markets

<table><thead><tr><th width="137">Type</th><th width="163">Ticker</th><th>Address</th></tr></thead><tbody><tr><td>OG</td><td>idleWBTC_Yield</td><td><a href="http://etherscan.io/address/0x8C81121B15197fA0eEaEE1DC75533419DcfD3151">0x8C81121B15197fA0eEaEE1DC75533419DcfD3151</a></td></tr><tr><td>OG</td><td>idleSUSD_Yield</td><td><a href="https://etherscan.io/address/0xf52cdcd458bf455aed77751743180ec4a595fd3f">0xf52cdcd458bf455aed77751743180ec4a595fd3f</a></td></tr><tr><td>OG</td><td>idleTUSD_Yield</td><td><a href="https://etherscan.io/address/0xc278041fdd8249fe4c1aad1193876857eea3d68c">0xc278041fdd8249fe4c1aad1193876857eea3d68c</a></td></tr><tr><td>OG</td><td>idleRAI_Yield</td><td><a href="https://etherscan.io/address/0x5c960a3dcc01be8a0f49c02a8cebcacf5d07fabe">0x5c960a3dcc01be8a0f49c02a8cebcacf5d07fabe</a></td></tr><tr><td>OG</td><td>idleFEI_Yield</td><td><a href="https://etherscan.io/address/0xb2d5CB72A621493fe83C6885E4A776279be595bC">0xb2d5CB72A621493fe83C6885E4A776279be595bC</a></td></tr><tr><td>Senior</td><td>idleWETH_Senior</td><td><a href="https://etherscan.io/address/0xc8e6ca6e96a326dc448307a5fde90a0b21fd7f80">0xC8E6CA6E96a326dC448307A5fDE90a0b21fd7f80</a></td></tr><tr><td>Junior</td><td>idleWETH_Junior</td><td><a href="https://etherscan.io/address/0x62a0369c6bb00054e589d12aad7ad81ed789514b">0x62a0369c6bb00054e589d12aad7ad81ed789514b</a></td></tr><tr><td>Junior</td><td>idleDAI_Junior</td><td><a href="https://etherscan.io/address/0xec9482040e6483b7459cc0db05d51dfa3d3068e1">0xec9482040e6483b7459cc0db05d51dfa3d3068e1</a></td></tr><tr><td>Junior</td><td>idleUSDC_Junior</td><td><a href="https://etherscan.io/address/0xdc7777c771a6e4b3a82830781bdde4dbc78f320e">0xdc7777c771a6e4b3a82830781bdde4dbc78f320e</a></td></tr><tr><td>Junior</td><td>idleUSDT_Junior</td><td><a href="https://etherscan.io/address/0xfa3afc9a194babd56e743fa3b7aa2ccbed3eaaad">0xfa3afc9a194babd56e743fa3b7aa2ccbed3eaaad</a></td></tr></tbody></table>

#### Deprecated strategies Polygon

<table><thead><tr><th width="137.33333333333331">Type</th><th width="159">Ticker</th><th>Address</th></tr></thead><tbody><tr><td>OG</td><td>idleDAI_Yield</td><td><a href="https://polygonscan.com/address/0x8a999F5A3546F8243205b2c0eCb0627cC10003ab">0x8a999F5A3546F8243205b2c0eCb0627cC10003ab</a></td></tr><tr><td>OG</td><td>idleUSDC_Yield</td><td><a href="https://polygonscan.com/address/0x1ee6470CD75D5686d0b2b90C0305Fa46fb0C89A1">0x1ee6470CD75D5686d0b2b90C0305Fa46fb0C89A1</a></td></tr><tr><td>OG</td><td>idleWETH_Yield</td><td><a href="https://polygonscan.com/address/0xfdA25D931258Df948ffecb66b5518299Df6527C4">0xfdA25D931258Df948ffecb66b5518299Df6527C4</a></td></tr></tbody></table>
