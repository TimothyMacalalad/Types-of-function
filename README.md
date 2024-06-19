# Types-of-function
# Description 
create your own ERC20 token and deploy it using HardHat or Remix the contract owner should be able to mint tokens to a provided address and any user should be able to burn and transfer tokens.

# Executing the program
// SPDX-License-Identifier: Apache-2.0
pragma solidity ^0.8.0;

import "@openzeppelin/contracts/token/ERC20/ERC20.sol";

contract MyToken is ERC20 {
    address public tokenOwner; // changed variable name from "owner" to "tokenOwner"

    constructor(string memory _name, string memory _symbol,uint256 initialSupply) ERC20(_name, _symbol) {
     _mint (msg.sender, initialSupply);
     tokenOwner = msg.sender; // changed variable name here
    }

    modifier onlyTokenOwner() {
        require(msg.sender == tokenOwner, "Only the token owner can call this function"); // changed variable name here
        _;
    }

The Solidity code above defines MyToken to be an ERC20 token which makes use of the OpenZeppelin library for standardized and secure implementations of ERC20 token functionalities. This contract sets the deploying address as the owner. It sets that new minting of tokens can only be done by calling the mint function by the owner. Burn: By calling the burn function, every token holder can burn his or her own tokens. It inherits the standard ERC20 functionality for transfer and transferFrom, and then it is supplemented with conditions for disallowing transfers to the zero address. This smart contract uses an implementation of OpenZeppelin's ERC20, underpinning its safety and compliance with the ERC20 standard while letting users define functionalities concerning minting, burning, and ownership restrictions.
# Author
Timothy Macalalad MetaCrafters

# License 
This project is licensed under the MIT License
