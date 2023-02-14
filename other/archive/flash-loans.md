# Flash Loans (deprecated)

The latest implementation of the `IdleToken` for the Best Yield strategy. has support for flash loans, which are uncollateralized loans that allow users to borrow the underlying token (e.g `DAI`) of an `IdleToken` (e.g `IdleDAI`).

### Overview

All `IdleToken` contracts can lend their undelrying tokens to a borrower smart contract as long as the principal amount + a fee are returned within the same transaction.

The `IdleToken` flash loans implementation follows the [EIP-3156](https://eips.ethereum.org/EIPS/eip-3156) which defines a standard interface that the lender and borrower smart contracts must implement.

### Fee

The current fee is set to `0.02%`, available in the `uint256 public flashLoanFee;` variable. You can also call the `flashFee` method to ask for the final fee based on the `_amount` to be borrowed:

`function flashFee(address _token, uint256 _amount) public view returns (uint256);`

### How it works

**Step 1**

An EOA (external owned account) or a smart contract calls the `flashLoan` method of an `IdleToken`.

```javascript
  function flashLoan(
    IERC3156FlashBorrower _receiver,
    address _token,
    uint256 _amount,
    bytes calldata _params
  ) external returns (bool);
```

* **\_receiver**: the smart contract that will receive the loan.
* **\_token**: it must be the underlying token (e.g. DAI) of the IdleToken.
* **\_amount**: the amount to borrow.
* **\_params**: parameters to forward to the borrower smart contract.

**Step 2**

The `IdleToken` contract transfers **\_amount** token to the borrower contract and calls its `onFlashLoan` method:

```javascript
  function onFlashLoan(
    address _initiator,
    address _token,
    uint256 _amount,
    uint256 _fee,
    bytes calldata _params
  ) external returns (bytes32);
```

* **\_initiator**: the EOA or contracts that initiated the flash loan.
* **\_token**: the token borrowed.
* **\_amount**: the amount borrowed.
* **\_fee**: the fee to be paid back on top of the principal.
* **\_params**: the params forwarded by the `IdleToken`.

At this point the borrower contracts can use the borrowed tokens in any way.

**Step 3**

After using the borrowed tokens, the borrower contracts must:

1. approve the IdleToken contract to get back`principal + fee` of the borrowed token&#x20;
2. return `keccak256("ERC3156FlashBorrower.onFlashLoan")`

**Step 4**

The `IdleToken` checks that the returned value is the one expected (`keccak256("ERC3156FlashBorrower.onFlashLoan")`) and transfers `amount + fee` tokens from the borrower to itself.

If the returned value is wrong, or if the transfers fails (i.e. the borrower didn't approve or approved less than `amount + fee`), the transaction is reverted.

### Example

Flash loan borrower contract:

```javascript
interface IERC3156FlashBorrower {
  function onFlashLoan(
    address initiator,
    address token,
    uint256 amount,
    uint256 fee,
    bytes calldata data
  ) external returns (bytes32);
}

contract FlashLoanBorrower is IERC3156FlashBorrower {
  using SafeMath for uint256;
  using SafeERC20 for IERC20;

  function onFlashLoan(
    address _initiator,
    address _token,
    uint256 _amount,
    uint256 _fee,
    bytes calldata _params
  ) external returns (bytes32) {
    // custom logic where the contract uses the borrowed tokens
    // NOTE: Remember to verify that _initiator address

    // approve principal + fee to be received back by the sender
    IERC20(_token).safeApprove(msg.sender, _amount.add(_fee));

    // return value specified in the ERC3156
    return keccak256("ERC3156FlashBorrower.onFlashLoan");
  }
}
```

Executing the flash loan:

```javascript
const idleToken = await IdleTokenGovernance.at(addresses.idleDAIV4);
const underlying = await IERC20.at(await idleToken.token);

await deployer.deploy(FlashLoanBorrower);
const borrower = await FlashLoanBorrower.deployed();

await idleToken.flashLoan(
  borrower.address,
  underlying.address,
  "1000000000000000000", // 1 DAI
  web3.eth.abi.encodeParameters(["uint256"], [123]),
  { from: accounts[0] }
);
```
