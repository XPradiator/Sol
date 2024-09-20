# Create a Token in Solidity

This Solidity program is a program that demonstrates the basic syntax and functionality of the Solidity programming language. The purpose of this program is to introduce data types, functions and mapping in Solidity.

## Description

This program is a simple contract written in Solidity, a programming language used for developing smart contracts on the Ethereum blockchain. The contract has multiple functions namely "mint" and "burn" to add or remove token amount from chain respectively. This program serves as a simple and straightforward use to Solidity programming with addition of mapping, conditional statements,functions and can be used to test out creating a token on block chain.

## Getting Started

### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., mytoken.sol). Copy and paste the following code into the file:

```javascript
// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;

/*
       REQUIREMENTS
    1. Your contract will have public variables that store the details about your coin (Token Name, Token Abbrv., Total Supply)
    2. Your contract will have a mapping of addresses to balances (address => uint)
    3. You will have a mint function that takes two parameters: an address and a value. 
       The function then increases the total supply by that number and increases the balance 
       of the “sender” address by that amount
    4. Your contract will have a burn function, which works the opposite of the mint function, as it will destroy tokens. 
       It will take an address and value just like the mint functions. It will then deduct the value from the total supply 
       and from the balance of the “sender”.
    5. Lastly, your burn function should have conditionals to make sure the balance of "sender" is greater than or equal 
       to the amount that is supposed to be burned.
*/

contract MyToken {

     // public variables here
    string public tokenName = "META";
    string public tokenAbbrv = "MTA";
    uint public totalSupply = 0;

     // mapping variable here
     mapping(address => uint) public balances;

     // mint function
function mint (address _address, uint _value) public {
        totalSupply += _value;
        balances[_address] += _value;
         }

// burn function
function burn (address _address, uint _value) public{
    if (balances[_address] >= _value) { 
         totalSupply -= _value;
        balances[_address] -= _value;
    }
}
}

```

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.18" (or another compatible version), and then click on the "Compile mytoken.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "mytoken" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you can interact with it by calling the mint and burn function. Click on the "mytoken" contract in the left-hand sidebar, and add addressed to a wallet given at Remix then click on the "mint" function to add token or "burn" function. Finally, click on the "total supply" button to execute the function and retrieve the amount of token in wallet.

## Authors

Mayank Singh  
[Gmail](ironmanrock18@gmail.com)
