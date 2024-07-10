# ETH-Proof-Begineer
MyToken Smart Contract
Overview
MyToken is a simple ERC-20 like token implemented in Solidity. This contract allows for the creation (minting) and destruction (burning) of tokens. The total supply of tokens and the balance of each address are tracked.

Features
Token Details: The contract stores the name, symbol, and total supply of the token.
Minting: Allows increasing the total supply and the balance of a specified address.
Burning: Allows decreasing the total supply and the balance of a specified address.

Contract Details
SPDX License Identifier
solidity
code:
// SPDX-License-Identifier: MIT

Solidity Version
solidity
code:
pragma solidity 0.8.18;

Contract Definition
solidity
code:
contract MyToken {

    // Public variables to store details about the token
    string public name = "MyToken";
    string public symbol = "MTK";
    uint256 public totalSupply = 0;

     // Mapping to store balances of addresses
      mapping(address => uint256) public balanceOf;

    // Mint function to increase total supply and the balance of a given address
        function mint(address _to, uint256 _amount) public {
        totalSupply += _amount;
        balanceOf[_to] += _amount;
    }

     // Burn function to decrease total supply and the balance of a given address
        function burn(address _from, uint256 _amount) public {
        require(balanceOf[_from] >= _amount, "Insufficient balance to burn");
        totalSupply -= _amount;
        balanceOf[_from] -= _amount;
    }
}

Functions
Public Variables
name: The name of the token. Set to "MyToken".
symbol: The symbol of the token. Set to "MTK".
totalSupply: The total supply of the token. Initialized to 0.
balanceOf: A mapping that stores the balance of each address.

Mint
solidity
code:
"function mint(address _to, uint256 _amount) public"
Increases the total supply and the balance of the specified address.

Parameters:
_to: The address to receive the newly minted tokens.
_amount: The number of tokens to mint.
Example:
solidity
code:
"mint(0xAbC123..., 1000);"

Burn
solidity
code:
"function burn(address _from, uint256 _amount) public"
Decreases the total supply and the balance of the specified address. Requires that the address has a sufficient balance to burn.

Parameters:
_from: The address whose tokens will be burned.
_amount: The number of tokens to burn.
Example:
solidity
code:
"burn(0xAbC123..., 500);"

Usage
To deploy and interact with this contract, use a Solidity development environment such as Remix, Truffle, or Hardhat. Ensure you are using Solidity version 0.8.18 or later.

Deployment
Deploy the contract to your preferred Ethereum network.
Use the mint function to create tokens and assign them to addresses.
Use the burn function to destroy tokens from addresses as needed.

