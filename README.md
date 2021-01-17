# truffle-token-test-utils
![npm](https://img.shields.io/npm/v/truffle-token-test-utils)
![npm bundle size](https://img.shields.io/bundlephobia/min/truffle-token-test-utils)

Visualize ERC20 token transfers in Truffle Tests

## Install

```
$ npm install truffle-token-test-utils
```

## Usage
### With Truffle:

```js
const tokenTransfers = require("truffle-token-test-utils");
contract("ContractName", (accounts) => {
  tokenTransfers.setWeb3(web3);  // web3 auto injected by truffle in tests
  ...
  const tx = await someContract.someFunction();
  await tokenTransfers.print(tx);
}
```
### With OpenZeppelin:

```js
const { web3 } = require("@openzeppelin/test-environment");
const tokenTransfers = require("truffle-token-test-utils");
tokenTransfers.setWeb3(web3);
...
const tx = await someContract.someFunction();
await tokenTransfers.print(tx);
```

## Sample Output
![Console Output](https://i.imgur.com/e11x6ti.jpg)

## Additional Options:
**1. Substitute address with custom names**

An object for custom `addressToName` mapping can be passed along with `print()` to display names instead of ETH addresses.
Without it the default `'SENDER'` and `'RECEIVER'` are displayed for the transaction sender and receiver contract address repectively. They both can also be overwritten with the passed object.

Eg:
```js
await tokenTransfers.print(tx, {
  "0xAb5801a7D398351b8bE11C439e05C5B3259aeC9B": "Vitalik"
});
```

Output:

![Custom Address Mapping output](https://i.imgur.com/St58RfP.png)

**2. Get overall accounts balance change**

Pass boolean `true` as third argument for `print()` to display overall token balance change as shown

```js
await tokenTransfers.print(tx, {}, true);
```

Output:

![overall accounts balance output](https://i.imgur.com/UIZDGce.png)

---
## Developed by:
### **Apoorv Lathey**
[![Twitter Follow](https://img.shields.io/twitter/follow/apoorvlathey?label=%40apoorvlathey&style=social)](https://twitter.com/apoorvlathey)
