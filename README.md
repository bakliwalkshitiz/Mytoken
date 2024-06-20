Simple Contract

Description

This project implements a basic token system using a smart contract written in Solidity. The contract includes public variables to store details about the token (Token Name, Token Abbreviation, Total Supply), a mint function to increase the total supply and the balance of a specified address, and a burn function to decrease the total supply and the balance of a specified address.

Getting Started

To run this program, you can use Remix, an online Solidity IDE. Follow these steps to get started:

Go to the Remix website.
Create a new file by clicking on the "+" icon in the left-hand sidebar.
Save the file with a .sol extension (e.g., MyToken.sol).
Copy and paste the following code into the file:

executing program

// SPDX-License-Identifier: MIT
pragma solidity ^0.8.26;

contract MyToken {
    // Public variables
    string public name = "KB Token"; 
    string public symbol = "KBT";
    uint256 public totalSupply;

    // Mapping of addresses to balances
    mapping(address => uint256) public balances;

    // Mint function to create new tokens
    // This function is responsible for creating new tokens and assigning them to the specified recipient.
    function mint(address _recipient, uint256 _amount) public {
        totalSupply += _amount;
        balances[_recipient] += _amount;
    }

    // Burn function to destroy tokens
    function burn(address _account, uint256 _amount) public {
        require(balances[_account] >= _amount, "Insufficient balance");
        totalSupply -= _amount;
        balances[_account] -= _amount;
    }
}

Executing Program

To compile and deploy the contract in Remix, first, click on the "Solidity Compiler" tab, ensure the compiler is set to "0.8.26" (or another compatible version), and click "Compile MyToken.sol". Next, go to the "Deploy & Run Transactions" tab, select the "MyToken" contract, and click "Deploy". Once deployed, you can interact with the contract by using the mint function to add tokens to an address, the burn function to remove tokens from an address (if the balance is sufficient), check balances using the balances mapping, and view the total supply through the totalSupply variable.

Authors
Kshitiz Bakliwal


