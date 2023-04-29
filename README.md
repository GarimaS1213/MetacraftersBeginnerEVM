# Token Creation

In the code provided below, I've created a simple solidity smart contract that mints and burns the number of tokens we provide those functions in the value parameter.

## Description

The code bascally contains three variables, tokenname, tokenAbbrv, totalSupply. And two functions, mint and burn that generate and deletes the tokens respectively. We just have to copy the address from the address bar in remixIDE and paste it in mint or burn, and pass number of tokens as value parameter and just transact it.

### Executing program

The following code can be run in remix editor which is an online editor for running and deploying smart contracts. just compile and deploy.

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
    string public tokenname = "GARIMA"; 
    string public tokenAbbrv = "GAR"; 
    uint public totalSupply = 0;

    // mapping variable here
    mapping(address => uint) public balances;

    // mint function
    function mint (address _address, uint _value) public {
        totalSupply += _value; 
        balances[_address] += _value;
    }
    // burn function
    function burn (address _address, uint _value) public { 
        if (balances[_address] >= _value) {
            totalSupply -= _value; 
            balances[_address] -= _value;
        }
    }
}
```

## License

We have used the license MIT which is specifed in the first line.

Thanks for checking this out!!
