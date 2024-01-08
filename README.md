# Smart Contract Winner

## Overview

- Interacting with a smart contract deployed on the Ethereum Goerli testnet.

## Contract details

Here there is a contract deployed on the blockchain:

[0x37De8591056b60Cc2e3a620C30305FA91Fb71e1C](https://goerli.etherscan.io/address/0x37De8591056b60Cc2e3a620C30305FA91Fb71e1C)

## Contract code

```solidity
// SPDX-License-Identifier: Unlicense
pragma solidity ^0.8.0;

contract Contract {
    event Winner(address);

    function attempt() external {
        require(msg.sender != tx.origin, "msg.sender is equal to tx.origin");
        emit Winner(msg.sender);
    }
}
```

## Contract logic

The contract includes a function attempt() that emits a Winner event. The criteria for winning are as follows:

- msg.sender must not be equal to tx.origin.
- This implies that the transaction's origin address must be different from the address calling the attempt() function.

## Solution approach

- To meet the winning criteria, I deployed my own contract using my Externally Owned Account (EOA). This contract contains a function designed to call the attempt() function of the deployed contract on the blockchain.

## Demo

<div>
    <a href="https://www.loom.com/share/d06c7496613644209d577d35b286c34e">
      <p></p>
    </a>
    <a href="https://www.loom.com/share/d06c7496613644209d577d35b286c34e">
      <img style="max-width:300px;" src="https://cdn.loom.com/sessions/thumbnails/d06c7496613644209d577d35b286c34e-with-play.gif">
    </a>
  </div>

## Contributor

Erik Williams
