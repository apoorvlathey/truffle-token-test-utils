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
const { setWeb3, printTokenTransfers } = require("truffle-token-test-utils");
setWeb3(web3);  // web3 auto injected by truffle in tests
...
const tx = await someContract.someFunction();
printTokenTransfers(tx)
```
### With OpenZeppelin:

```js
const { web3 } = require("@openzeppelin/test-environment");
const { setWeb3, printTokenTransfers } = require("truffle-token-test-utils");
setWeb3(web3);
...
const tx = await someContract.someFunction();
printTokenTransfers(tx)
```

## Sample Output
![Console Output](https://i.imgur.com/FTPduIH.png)

---
## Developed by:
### **Apoorv Lathey**
[![Twitter Follow](https://img.shields.io/twitter/follow/apoorvlathey?label=%40apoorvlathey&style=social)](https://twitter.com/apoorvlathey)
