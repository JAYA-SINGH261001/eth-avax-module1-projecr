# eth-avax-module1-project
# Smart Contract - Simple Deposit and Withdraw
This is a simple Solidity smart contract that allows users to deposit and withdraw Ether. The contract implements input validation using require() and handles overflows and underflows using assert(). Additionally, it uses revert() to return excess amounts to the sender during withdrawals.
# Contract Details
* contractBalance: A public variable representing the total balance held by the contract. Users can deposit Ether into the contract, increasing this balance, and withdraw Ether, decreasing this balance.

* owner: A public variable representing the address of the contract owner. The owner is set during contract deployment and is typically the address of the account that deployed the contract.
# Functions
1. constructor()

The constructor is executed only once during the contract deployment. It sets the contract owner to the address of the account that deployed the contract.
2. deposit()

The deposit() function allows users to deposit Ether into the contract. To deposit Ether, users need to call this function with an attached amount of Ether. The function performs the following steps:
*   It uses require() to validate that the deposited amount is greater than zero. If the amount is not greater than zero, the function reverts the transaction with an error message.

*   It uses assert() to ensure that the addition of the deposited amount to contractBalance does not cause an overflow. If an overflow is detected, the transaction will revert.

*   The contract balance is updated by adding the deposited amount to contractBalance.
3. withdraw(uint256 amount)
The withdraw() function allows users to withdraw a specific amount of Ether from the contract. The function takes one parameter amount, which represents the amount of Ether the user wants to withdraw. The function performs the following steps:

*    It uses require() to check that the contract has enough balance to cover the withdrawal. If the contract balance is less than the requested withdrawal amount, the function reverts with an error message.

*    If there is any excess amount (when amount < contractBalance), the function calculates the excess and transfers it back to the sender using payable(msg.sender).transfer(excessAmount).

*    The contract balance is updated by subtracting the withdrawal amount from contractBalance.

*    It uses assert() to ensure that the subtraction of the withdrawal amount from contractBalance does not cause an underflow. If an underflow is detected, the transaction will revert.
# Usage
To interact with the contract, you can deploy it on the Ethereum blockchain using a development environment like Remix or Truffle. After deploying the contract, you can call the deposit() function to deposit Ether and use the withdraw(uint256 amount) function to withdraw specific amounts of Ether.

Please note that this is a simplified example for educational purposes, and in real-world scenarios, you would need to consider additional security measures and further error handling to make the contract robust and secure. Always exercise caution when working with smart contracts, especially when handling user funds.
# Author 
Jaya Singh
# License 
MIT Licence 
