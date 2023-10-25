---
description: Developers > Network and codebase > ERC-4626
---

# ERC-4626 standard

### What is the ERC-4626 standard?

The [ERC-4626](https://eips.ethereum.org/EIPS/eip-4626) is a standard interface for yield-bearing tokens.&#x20;

> _The ERC-4626 is a standard to optimize and unify the technical parameters of yield-bearing vaults. It provides a standard API for tokenized yield-bearing vaults that represent shares of a single underlying ERC-20 token. ERC-4626 also outlines an optional extension for tokenized vaults utilizing ERC-20, offering basic functionality for depositing, withdrawing tokens and reading balances_ - [Ethereum.org](https://ethereum.org/en/developers/docs/standards/tokens/erc-4626/)

### Why is the ERC-4626 compatibility needed?

Tokenized vaults have a lack of standardization leading to diverse implementation details. Some examples include lending markets, aggregators, and intrinsically interest-bearing tokens. This makes integration difficult at the aggregator or plugin layer for protocols conforming to multiple standards, forcing each protocol to implement its error-prone adapters.

A standard for tokenized vaults will lower the integration effort for yield-bearing vaults while creating more consistent and robust implementation patterns enhancing the DeFi composability capacity. This standard will also reduce the cost of audits to secure their adapters from vulnerabilities.

#### Specs

All ERC-4626 tokenized vaults must implement ERC-20 to represent shares. If a vault is to be non-transferrable, it may revert on calls to `transfer` or `transferFrom`. The ERC-20 operations `balanceOf`, `transfer`, `totalSupply`, etc. operate on the Vault “shares” which represent a claim to ownership on a fraction of the Vault’s underlying holdings.

All ERC-4626 tokenized Vaults must implement ERC-20’s optional metadata extensions. The `name` and `symbol` functions should reflect the underlying token’s `name` and `symbol` in some way.

#### Backward Compatibility <a href="#backwards-compatibility" id="backwards-compatibility"></a>

[EIP-4626](https://github.com/ethereum/EIPs/pull/4626) is fully backward compatible with the ERC-20 standard and has no known compatibility issues with other standards. For production implementations of vaults that do not use ERC-4626, wrapper adapters can be developed and used.

### ERC-4626 compliant contracts

All deployed Best Yield strategies ERC-4626 wrappers can be found [here](../best-yield/deployed-contracts.md#erc-4626-wrappers-for-best-yield-tokens).

All deployed Yield Tranches ERC-4626 wrappers can be found [here.](../yield-tranches/deployed-contracts/#erc-4626-wrappers-for-tranche-tokens)
