// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract MyToken {
    // Public variables
    string public tokenName = "MyToken";
    string public tokenAbb = "MTK";
    uint256 public totalSupply = 0;

    // Mapping from address to balance
    mapping(address => uint256) public balances;

    // Mint function to create new tokens
    function mint(address _address, uint256 value) public {
        totalSupply += value;
        balances[_address] += value;
    }

    // Burn function to destroy tokens
    function burn(address _address, uint256 value) public {
        require(balances[_address] >= value, "Insufficient balance to burn");
        totalSupply -= value;
        balances[_address] -= value;
    }
}
