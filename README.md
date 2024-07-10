# ETH-Proof-Begineer
// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;

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
