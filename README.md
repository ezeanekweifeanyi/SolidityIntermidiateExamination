# Error Handling Solidity Contract

This Solidity contract illustrates various error handling mechanisms, including the usage of `require`, `assert`, and `revert`. It provides examples of how these constructs are used to prevent undesirable behavior and maintain contract integrity. Below is a guide on how to compile and deploy the contract using Remix, an online Solidity IDE.

## Description

The "Error" contract demonstrates the use of error handling mechanisms to ensure the proper functioning of a smart contract. It includes two functions: `set` and `increase`, each showcasing different error handling approaches. The contract highlights the importance of error handling in maintaining the reliability and security of Ethereum smart contracts.

## Getting Started

### Prerequisites

- Access to an Ethereum wallet and Remix Solidity IDE (https://remix.ethereum.org/).

### Deployment

1. Open Remix in your web browser.

2. Create a new file named `Error.sol`.

3. Copy and paste the following Solidity code into the file:

solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract Error {
    uint256 public num;

    function set(uint256 _newNum) public {
        require(_newNum > num, "New number must be greater than the existing num");
        
        num = _newNum;
    }
    
    function increase(uint256 _amount) public {
        uint256 oldNum = num;
        
        assert(num + _amount >= num);
        
        num += _amount;
        
        if (num < oldNum) {
            revert("Number won't reduce");
        }
    }
}


4. Compile the contract by clicking on the "Solidity Compiler" tab, ensuring the compiler version is set to `0.8.0`, and then clicking on the "Compile Error.sol" button.

5. Deploy the contract by clicking on the "Deploy & Run Transactions" tab. Select the `Error` contract from the dropdown menu, and then click on the "Deploy" button.

6. Once the contract is deployed, you can interact with it:
   - To set a new number, click on the `set` function under the deployed contract, provide the new number (`_newNum`), and then click "transact."
   - To increase the number, click on the `increase` function, provide the amount (`_amount`), and then click "transact."

Note that the error handling mechanisms used in this contract are for demonstration purposes and may need further enhancements for more complex scenarios.

## Authors

Ifeanyi Febian Ezeanekwe

## License

This project is licensed under the MIT License - see the LICENSE.md file for details.
