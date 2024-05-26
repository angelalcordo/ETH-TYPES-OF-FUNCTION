# Types of Functions - ETH + AVAX

### Create, Mint and Transfer Token
ETH Avax Intermediate Module 3: MyToken is a Solidity smart contract that implements an ERC20 token. It extends the functionality of the ERC20 standard token by providing additional features such as minting, burning, and ownership control.

### Description

The Types of Function named CyberxCoin, is an implementation of an ERC20 token on the Ethereum blockchain. It allows for the creation, transfer, and burning of tokens. The contract owner has the exclusive ability to mint new tokens, while any user can transfer tokens to other addresses or burn their own tokens. The contract is built upon OpenZeppelin's ERC20 implementation for standard token functionality and employs a modifier onlyOwner to restrict certain actions to the contract owner.

### Executing the program

To run this program, begin by accessing the Remix Ethereum IDE at https://remix.ethereum.org/. Create a new file in the IDE, ensuring it has a .sol extension, and paste the provided Solidity smart contract code into it. Next, compile the contract by selecting the appropriate Solidity compiler version, which is 0.8.0 in this case, from the Remix compiler tab. Following compilation, deploy the contract by selecting the MyToken contract from the Remix deploy & run tab, then initiate deployment by clicking the deploy button. Once the contract is deployed, you can interact with it through the user-friendly interface provided by Remix. As the contract owner, you hold the privilege to mint new tokens to designated addresses using the mint function. Moreover, any user can facilitate token transfers to other addresses leveraging the transfer function. Additionally, users possess the capability to burn their own tokens utilizing the burn function.

### Contract Functions

The "CyberXCoin" contract exposes the following functions:

mint(address to, uint256 amount): Allows me to mint new tokens and assign them to the specified address.

burn(uint256 amount): Allows users to destroy a specific amount of their tokens.

transfer(address to, uint256 amount): Allows users to transfer tokens to another address.

```
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

import "@openzeppelin/contracts/token/ERC20/ERC20.sol";

contract MyToken is ERC20 {
    address public owner;

    constructor() ERC20("CyberCoin", "CYR") {
        owner = msg.sender;
        _mint(msg.sender, 100000); // Given value amount for the Token
    }

    modifier onlyOwner() {
        require(msg.sender == owner, "You must be the contract owner to do this");
        _;
    }

    function mint(address to, uint256 amount) public onlyOwner {
        _mint(to, amount);
    }

    function transfer(address to, uint256 amount) public override returns (bool) {
        _transfer(msg.sender, to, amount);
        return true;
    }

    function burn(uint256 amount) public {
        _burn(msg.sender, amount);
    }
}
```

### Additional Information

Student Info and Email address

Alcordo, Angel Adellene A. 

422003173@ntc.edu.ph

### License

This project is licensed under the MIT License - see the LICENSE.md file for details

