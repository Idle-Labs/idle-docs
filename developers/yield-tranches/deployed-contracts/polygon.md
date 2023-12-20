---
description: Developers > Yield Tranches > Deployed contracts > Polygon zkEVM
---

# Polygon zkEVM

You can find the currently deployed instances and ABIs of the Yield Tranches contracts at the following addresses. The tables list all the YTs addresses currently available and the specific token addresses following this scheme:&#x20;

* CDO = Main YTs contract address
* Senior = Senior tranche LP token (AA)
* Junior = Junior tranche LP token (BB)

The ABI of the Yield Tranches contract can be found here: [JSON](https://github.com/Idle-Labs/idle-tranches/blob/master/abi/IdleCDO.json).

<table><thead><tr><th width="299.50164149548493">Contract</th><th>Address</th></tr></thead><tbody><tr><td>Idle CDO registry</td><td><a href="https://etherscan.io/address/0x84FDeE80F18957A041354E99C7eB407467D94d8E">0x84FDeE80F18957A041354E99C7eB407467D94d8E</a></td></tr></tbody></table>

### Clearpool

**USDT (Portofino)**

<table><thead><tr><th width="98.33333333333331">Side</th><th width="197">Ticker</th><th>Address</th></tr></thead><tbody><tr><td>CDO</td><td>cp_POR_USDT</td><td><a href="https://zkevm.polygonscan.com/address/0x6b8A1e78Ac707F9b0b5eB4f34B02D9af84D2b689">0x6b8A1e78Ac707F9b0b5eB4f34B02D9af84D2b689</a></td></tr><tr><td>Senior</td><td>AA_cp_POR_USDT</td><td><a href="https://zkevm.polygonscan.com/address/0x6aab2db845b23729af1f5b0902ff4bdc32bbf948">0x6AaB2db845b23729aF1F5B0902Ff4BDc32BBf948</a></td></tr><tr><td>Junior</td><td>BB_cp_POR_USDT</td><td><a href="https://zkevm.polygonscan.com/address/0x1fdaf221ff3929e86266d6a5930fa7263c1bd4df">0x1FdAF221fF3929e86266D6A5930fa7263c1bD4DF</a></td></tr></tbody></table>

### ERC-4626 wrappers for Tranche tokens

where AA = Senior Tranche, BB = Junior Tranche.

Integrators that need other ERC-4626 wrappers can get in contact with the [Development League ](https://discord.gg/fJaBYmS)on Discord.&#x20;

<table><thead><tr><th width="96.33333333333331">Side</th><th width="206">Ticker</th><th>Address</th></tr></thead><tbody><tr><td>Senior</td><td>AA_cp_POR_USDT_w</td><td><a href="https://zkevm.polygonscan.com/address/0x0ac74Fe6f3C9123254418EEfcE37E4f7271a2b72">0x0ac74Fe6f3C9123254418EEfcE37E4f7271a2b72</a></td></tr><tr><td>Senior</td><td>AA_cp_FAS_USDC_w</td><td><a href="https://zkevm.polygonscan.com/address/0xFbc63d309F915AA62517A6b4e845502CEcf946cf">0xFbc63d309F915AA62517A6b4e845502CEcf946cf</a></td></tr></tbody></table>

### Deprecated strategies

The expandable lists all the YTs addresses deprecated and the specific token addresses following this order:&#x20;

1. Main YTs contract address (CDO)
2. Senior tranche LP token (AA)
3. Junior tranche LP token (BB)

{% tabs %}
{% tab title="QuickSwap" %}
#### WETH

<table><thead><tr><th width="250">Contract</th><th>Address</th></tr></thead><tbody><tr><td>Quickswap idleCSUNI-V2</td><td><a href="https://polygonscan.com/address/0xb144ee58679e15f1b25a5f6efcebdd0ab8c8bef5">0xB144eE58679e15f1b25A5F6EfcEBDd0AB8c8BEF5</a></td></tr></tbody></table>
{% endtab %}

{% tab title="Clearpool" %}
**USDC (Fasanara)**

<table><thead><tr><th width="192">Ticker</th><th>Address</th></tr></thead><tbody><tr><td>cp_FAS_USDC</td><td><a href="https://zkevm.polygonscan.com/address/0x8890957f80d7d771337f4ce42e15ec40388514f1">0x8890957F80d7D771337f4ce42e15Ec40388514f1</a></td></tr><tr><td>AA_cp_FAS_USDC</td><td><a href="https://zkevm.polygonscan.com/address/0x3ed123e94c95a5777149aeec50f4c956b29eccec">0x3Ed123E94C95A5777149AeEc50F4C956b29EcceC</a></td></tr><tr><td>BB_cp_FAS_USDC</td><td><a href="https://zkevm.polygonscan.com/address/0xbf78b393d14a90b52cdc2325e11c92f24f2f54f3">0xBF78b393d14A90B52cdc2325e11c92F24f2F54F3</a></td></tr></tbody></table>
{% endtab %}
{% endtabs %}
