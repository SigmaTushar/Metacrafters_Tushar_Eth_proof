HelloToken Solidity Contract

 Overview

The `HelloToken` contract is a basic ERC20-like token that allows minting and burning of tokens. It includes functionalities to manage token balances and track the total token supply.

 Public Variables

- TokenName: "Tushar Ranjan Jha"
- TokenAbr: "TRJ"
- TotalSupply: Total number of tokens minted.

 Functions

1. mintToken(address addr, uint256 val)
   - Increases the total supply by `val`.
   - Increases the balance of `addr` by `val`.
   - function mintToken(address addr, uint256 val) public{
    TotalSupply = TotalSupply + val;
     Balances[addr] += val;
       
    }

2. burnToken(address addr, uint256 val)
   - Decreases the total supply by `val`.
   - Decreases the balance of `addr` by `val`, if the balance is sufficient.
   - function burnToken(address addr, uint256 val) public{
       if(Balances[addr] >= val){
        TotalSupply = TotalSupply - val;
        Balances[addr] -= val;
    } 
    else{
        revert("The balance is insufficient in the mapping address account");
       }
  }
}

Requirements

1. Public variables store token name, abbreviation, and total supply.
2. Mapping tracks token balances for addresses.
3. `mintToken` function increases total supply and address balance.
4. `burnToken` function decreases total supply and address balance, with validation for sufficient balance.

Deployment

To deploy this contract:
- Compile the Solidity code using a compiler compatible with version ^0.8.7.
- Use functions `mintToken` and `burnToken` to manage token minting and burning operations.

- Using Remix:
  1.Open Remix.
  2.In the Contracts folder, create a new file and paste the contract code into the editor.
  3.Compile the contract.
  4.Deploy the contract to the desired Ethereum network, in this case I have used the test token address given in the Remix IDE only.

 License

This contract is licensed under the MIT License. See [LICENSE](./LICENSE) for more details.



 Developer

- Author: Tushar Ranjan Jha

 Contributing: Contributions are welcome! Feel free for any changes or improvements.


