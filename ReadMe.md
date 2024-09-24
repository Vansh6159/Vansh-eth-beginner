# MyToken Smart Contract

*A simple smart contract for creating and managing a token named "Elon" with the abbreviation "MUSK".*

## Description

The `MyToken` contract allows users to mint new tokens, burn existing tokens, and keep track of token balances associated with different addresses. The contract demonstrates basic token management on the Ethereum blockchain.

## Getting Started

### Executing Program

Follow these steps to set up and deploy the contract using Remix IDE:

1. **Open Remix IDE:**
   Go to [Remix IDE](https://remix.ethereum.org).

2. **Create a New File:**
   - In the left sidebar, click on the "+" icon to create a new file.
   - Name your file `MyToken.sol`.

3. **Paste the Solidity Code:**
   ```solidity
   // SPDX-License-Identifier: MIT
   pragma solidity 0.8.18;

   contract MyToken {
       // Public variables
       string public tokenName = "Elon";
       string public tokenAbbrv = "MUSK";
       uint public totalSupply = 0;

       // Mapping of addresses to balances
       mapping(address => uint) public balances;

       // Mint function
       function mint(address _address, uint _value) public {
           totalSupply += _value;
           balances[_address] += _value;
       }

       // Burn function
       function burn(address _address, uint _value) public {
           require(balances[_address] >= _value, "Insufficient balance to burn");
           totalSupply -= _value;
           balances[_address] -= _value;
       }
   }
