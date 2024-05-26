# Create-and-Mint-Token-My-Token
This contract, named MyToken, is an ERC20-compatible token developed on the Ethereum blockchain. It facilitates the creation and management of a custom token with the functionality of standard ERC20 tokens.

### Description
Contract successfully implements ERC20 interface
Contract includes functionalities for minting and burning tokens
Contract provides access control for minting tokens restricted to the contract owner
Component and Functionality
constructor: The constructor initializes the token with a name, symbol, and initial supply. It also assigns the contract deployer as the initial owner of all tokens.

### Requirements
-Only contract owner should be able to mint tokens

-Any user can transfer tokens

-Any user can burn tokens

### Component and Functionality
`mint:` This function allows the contract owner to mint new tokens and assign them to a specified address.

`burn:` This function allows any token holder to burn a specific amount of their own tokens.

`balanceOf:` A function that retrieves the balance of a specified address.

`totalSupply:` A function that retrieves the total supply of tokens.

`transfer:` This function allows token holders to transfer tokens to another address.

`transferFrom:` This function allows approved spenders to transfer tokens from one address to another on behalf of the token owner.

`allowance:` A function that retrieves the amount of tokens approved for transfer by a spender.

`name:` A public variable that stores the name of the token.

`symbol:` A public variable that stores the symbol of the token.

`decimals:` A public variable that stores the number of decimal places for token representation.

`owner:` An address variable representing the owner of the token contract.

### Getting Started
To interact with this contract, you can deploy it on Remix Ethereum IDE or any Ethereum-compatible blockchain.

Open Remix Ethereum IDE.
Create a new file and paste the provided Solidity code.
Compile the code.
Deploy the contract.
Interact with the deployed contract by calling its functions.

Solidity
```Solidity
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
        return allowance(msg.sender, spender);
    }
    
}

```

This is the whole functionality within the code itself and the generalization of how the code will run.


### Authors


Baquiran, Kristine Mae P. 


8215029@ntc.edu.ph
