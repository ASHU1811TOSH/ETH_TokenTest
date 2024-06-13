# ETH_Token Smart Contract
This Solidity smart contract is a basic ERC20-like token. The contract allows for minting and burning of tokens, and keeps track of balances associated with addresses.

# Prerequisites
Solidity compiler version: 0.8.26

# Description
The MyToken contract is written in Solidity, a programming language specifically designed for developing smart contracts on the Ethereum blockchain. This contract includes public variables to store details about the token, a mapping to keep track of balances, and functions to mint and burn tokens. This program serves as an introductory example to help you understand how to create and manage a custom token.

# Getting Started
Executing program
To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., ETHProof.sol). Copy and paste the following code into the file:


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

     contract StandardToken {

    // public variables here
    string public Name = "ASHUTOSH";
    string public NameAbbrv = "ASH";
    uint public Total = 0;

    // mapping variable here
    mapping(address => uint) public balances;

    // mint function
    function mint(address _address, uint _value)public{
        Total += _value;
        balances[_address] += _value;
    }

    // burn function
    function burn(address _address, uint _value)public{
        if (balances[_address] >= _value){
            Total -= _value;
            balances[_address] -= _value;
        }
      }
    }
   
# Explaination-

**Mint Function:**

1.It takes two parameters: an address (_address) and a value (_value).

2.It increases the Total by the amount specified in val.

3.It also increases the balance of the address _address by the same amount.

**Burn Function:**

1.It takes two parameters: an address (_address) and a value (_value).

2.It first checks if the balance of the address _address is greater than or equal to the amount specified in _value.

3.If the condition is met, it decreases the Total by the amount specified in _value.

4.It also decreases the balance of the address _address by the same amount.
