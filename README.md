# MyToken Smart Contract

A simple Ethereum smart contract for creating and managing a custom token (HELIX). This project demonstrates basic token minting and burning functionalities.

## Description

The `MyToken` contract is designed to allow users to mint new tokens and burn existing tokens. It features basic functionalities typical of a cryptocurrency token, including adjusting total supply and tracking individual wallet balances. This contract is part of the ETH-PROOF assessment for the course offered by Metacrafters, aiming to provide hands-on experience with smart contract development.

## Getting Started

### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., HelloWorld.sol). Copy and paste the following code into the file:

```javascript
pragma solidity 0.8.18;
contract MyToken {

    // public variables here
   string public token_Name="HELIX";
   string public token_Abbrv="HLX";
   uint public total_Supply=0;

    // mapping variable here
   mapping(address => uint) public balance;

    // mint function
   function mint (address _address, uint _value) public{
      total_Supply+=_value;
      balance[_address]+=_value;
   }
    // burn function
   function burn (address _address, uint _value) public{
      if(balance[_address] >= _value){
         total_Supply-=_value;
         balance[_address]-=_value;
      }
   }
}


```

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.18" (or another compatible version), and then click on the "Compile MyToken.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "MyToken" contract from the dropdown menu, and then click on the "Deploy" button.

After deployment, the deployed contract instance will appear below in the "Deployed Contracts" section.
To mint tokens, expand the deployed contract, enter the desired address and value in the respective fields next to the mint function, and click "transact".
To burn tokens, use the burn function in a similar way, ensuring that the specified address has enough tokens to burn.

## Authors

Contributors names and contact info

* Krish Jaiswal
* email-krish.jaiswal2182003@gmail.com

## License

This project is licensed under the MIT License - see the LICENSE.md file for details
