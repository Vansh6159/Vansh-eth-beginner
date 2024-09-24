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
   
## Function Usage
**mint
The mint function allows the creation of new tokens and adds them to a specified address.

**burn
The burn function destroys tokens from a specified address, reducing the total supply.

**Parameters:
_address: The address to which the newly minted tokens will be added or burned.
_value: The amount of tokens to mint or burn.

## Help
For common issues or problems, you can refer to the Remix IDE documentation or check the console for error messages.

**Authors
Contributors:
