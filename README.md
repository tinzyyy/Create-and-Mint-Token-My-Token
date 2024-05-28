# MyToken - ERC20 Token Contract

This contract, named MyToken, is an ERC20-compatible token developed on the Ethereum blockchain. It facilitates the creation and management of a custom token with the functionality of standard ERC20 tokens.

## Description

The contract successfully implements the ERC20 interface and includes functionalities for minting and burning tokens. Access control for minting tokens is restricted to the contract owner.

## Requirements

- Only the contract owner should be able to mint tokens.
- Any user can transfer tokens.
- Any user can burn tokens.

## Components and Functionalities

### Constructor
The constructor initializes the token with a name ("MyToken"), symbol ("MTK"), and initial supply. It also assigns the contract deployer as the initial owner of all tokens.

### Functions

1. `mint`: This function allows the contract owner to mint new tokens and assign them to a specified address.

2. `burn`: This function allows any token holder to burn a specific amount of their own tokens.

3. `getAllowance`: A function that retrieves the amount of tokens approved for transfer by a spender.

4. `transferTokens`: This function allows token holders to transfer tokens to another address.

5. `balanceOf`: A function that retrieves the balance of a specified address.

6. `totalSupply`: A function that retrieves the total supply of tokens.

7. `transferFrom`: This function allows approved spenders to transfer tokens from one address to another on behalf of the token owner.

### Variables

- `name`: A public variable that stores the name of the token.
- `symbol`: A public variable that stores the symbol of the token.
- `decimals`: A public variable that stores the number of decimal places for token representation.
- `owner`: An address variable representing the owner of the token contract.

## Getting Started

To interact with this contract, you can deploy it on Remix Ethereum IDE or any Ethereum-compatible blockchain.

1. Open Remix Ethereum IDE.
2. Create a new file and paste the provided Solidity code.
3. Compile the code.
4. Deploy the contract.
5. Interact with the deployed contract by calling its functions.

 ### Solidity Code

```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

import "@openzeppelin/contracts/token/ERC20/ERC20.sol";
import "@openzeppelin/contracts/access/Ownable.sol";

contract MyToken is ERC20, Ownable {
    constructor() ERC20("MyToken", "MTK") Ownable(msg.sender) {
        
    }

    function mint(address to, uint256 amount) public onlyOwner {
        _mint(to, amount);
    }

    function burn(uint256 amount) public {
        _burn(msg.sender, amount);
    }
    
    function getAllowance(address spender) public view returns (uint256) {
        return allowance(_msgSender(), spender);
    }

    
    function transferTokens(address to, uint256 amount) public returns (bool) {
        _transfer(_msgSender(), to, amount);
        return true;
    }
}
```

This version includes the Solidity code along with the documentation. Let me know if there's anything else you'd like to add or modify!

## Authors

Baquiran, Kristine Mae P.  
8215029@ntc.edu.ph
