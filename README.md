# SolidityTokenAssesment

This is a simple solidity program which is used for developing smart contracts on ethereum blockchain.

## Description
This is a simple solidity program which is used to store tokens in your account(balance) and using a mint function to add new tokens or burn function to remove the tokens form the balance.Also we print the total supply at the end after minting and burning the tokens to see how much tokens are left.

## Getting Started

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

### Executing program
1. Now after opening the link you will click on the "File Explorer" option on the extreme left of the screen,then click on "create new file".
2. Save the file with .sol extension (For Eg. myTokens.sol).
3. Copy paste the following code on your remix platform.

```
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
    string public tokenName = "CRAFTERS";
    string public tokenAbr = "CFT";
    uint public totalSupply = 0;
    // mapping variable here
    mapping(address=>uint) public balance;

    // mint function
    function mint (address add,uint value) public {
       totalSupply += value;
       balance[add]+=value;

    }
    // burn function
    function burn (address add,uint value) public {
     if(balance[add] >= value){
       totalSupply -= value;
       balance[add]-=value;
     }

    }
}

```
4. To compile the code click on the "Solidity Compiler" option on the left hand side. Before compiling check the compiler option is 0.8.18,then click on the "compile" button.
5. Once the code is compiled click on the "Deploy and run Transaction" button on the left side of the screen. And click on "Deploy" button.
6. Once the contract is deployed, you can copy the address from the from "account" and paste the values in your "mint" function button and add any value, check the total supply (it will print the amount value which you added on the mint function button).
7. you can also burn the values by copying the address from the "account" and pasting it into the "burn" function button and write a value to be burnt, check the total supply again(Now you will be able to see the total supply will be deducted by the particular amount which you have written on the burn function.
8. keep in mind that if you add more value to burn than your total value than the function will simply compiled but the output will not changed.

## Authors
Metacrafter Chris
@metacraftersio
academy@metacrafters.io


## License

This project is licensed under the MIT License - see the LICENSE.md file for details
