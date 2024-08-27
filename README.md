# MyToken Smart Contract

A simple smart contract for managing a custom token with basic minting and burning functionalities.

## Description

The MyToken smart contract is a basic implementation of an ERC-20 like token on the Ethereum blockchain. It allows users to mint new tokens to specific addresses and burn tokens from an address. The contract keeps track of each address's balance using a mapping.

## Getting Started

### Installing
Clone the Repository:
Download the project to your local machine using the following command:
bash
Copy code
git clone https://github.com/yourusername/your-repository.git
cd your-repository
Setup Solidity Development Environment:

You can use Remix IDE or any local development environment like Truffle, Hardhat, etc.
### Executing program

Open the Contract:

Load the MyToken.sol file in your Solidity development environment.
Compile the Contract:

Use the Solidity compiler to compile the MyToken contract.
Deploy the Contract:

Deploy the contract to a local blockchain (like Ganache) or a test Ethereum network (like Rinkeby or Goerli).
Interact with the Contract:

Mint Tokens:
solidity
MyToken.mint(0xYourAddress, 100);
Burn Tokens:
solidity
MyToken.burn(0xYourAddress, 50);

## Help

For common issues:

Ensure your Solidity environment is correctly set up.
Verify the network connection when deploying the contract.
Make sure the address you interact with is valid and has sufficient balance for burning.
For additional help, you can run:

bash
Copy code
solidity --help

## Authors

Contributors' names and contact info:

Your Name - @sarth9

## License

This project is licensed under the MIT License - see the LICENSE.md file for details.

Solidity code

contract MyToken {

    // Public variables to store the details about the token
    string public tokenName = "MyToken";
    string public tokenAbbrv = "MTK";
    uint256 public totalSupply = 0;

    // Mapping to store the balances of addresses
    mapping(address => uint256) public balances;

    // Mint function to increase the total supply and the balance of the sender
    function mint(address _address, uint256 _value) public {
        totalSupply += _value;
        balances[_address] += _value;
    }

    // Burn function to decrease the total supply and the balance of the sender
    function burn(address _address, uint _value) public {
        if(balances[_address]>=_value){
             totalSupply -= _value;
             balances[_address] -= _value;
        }
       
    }
}










