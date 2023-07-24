# eth-avax-module1-project
# Smart Contract - Simple Deposit and Withdraw
This is a simple Solidity smart contract that allows users to deposit and withdraw Ether. The contract implements input validation using require() and handles overflows and underflows using assert(). Additionally, it uses revert() to return excess amounts to the sender during withdrawals.
# Contract Details
* contractBalance: A public variable representing the total balance held by the contract. Users can deposit Ether into the contract, increasing this balance, and withdraw Ether, decreasing this balance.

* owner: A public variable representing the address of the contract owner. The owner is set during contract deployment and is typically the address of the account that deployed the contract.
# Functions
1. constructor()

The constructor is executed only once during the contract deployment. It sets the contract owner to the address of the account that deployed the contract.
  
