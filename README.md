# MyToken Solidity Smart Contract

## Overview

This project implements a basic ERC20-like token contract in Solidity. The contract allows minting and burning of tokens and tracks the total supply and balances of each address.

## Requirements

1. **Public Variables**:
    - `tokenName`: The name of the token.
    - `tokenAbb`: The abbreviation of the token.
    - `totalSupply`: The total supply of the tokens.

2. **Mapping**:
    - `balances`: A mapping of addresses to their respective balances.

3. **Functions**:
    - `mint(address _address, uint256 value)`: Mints new tokens and assigns them to the specified address. Increases the total supply by the specified value.
    - `burn(address _address, uint256 value)`: Burns tokens from the specified address. Decreases the total supply by the specified value. Ensures that the address has enough balance to burn the specified amount.

## Usage

### Deploy the Contract

Deploy the contract to an Ethereum network using your preferred method (e.g., Remix,etc. ).

### Minting Tokens

To mint tokens, call the `mint` function with the desired address and amount of tokens. This will increase the total supply and the balance of the specified address.

```solidity
function mint(address _address, uint256 value) public {
    totalSupply += value;
    balances[_address] += value;
}
function burn(address _address, uint256 value) public {
    require(balances[_address] >= value, "Insufficient balance to burn");
    totalSupply -= value;
    balances[_address] -= value;
}
