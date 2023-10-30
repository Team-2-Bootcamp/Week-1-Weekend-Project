# Week-1 Weekend Project

This document forms part of the week 1 weekend project for the Solidity Bootcamp. 

Members from Team 2 who worked on this project: Ignas Apšega, Lyle Davids and Wendwossen Dufera

For week 1, we deployed the contract below to Sepolia testnet and interacted with it to see what results we get
The contract address on Sepolia testnet is 0xf649c3704655D524Eec75ee3C3b9B4Fe1C1a5a4a
### Deployment
Deployed Smart Contract through Remix on Sepolia Network. Also, the contract was verified through Sepolia Etherscan

```
// SPDX-License-Identifier: GPL-3.0
pragma solidity >=0.7.0 <0.9.0;

contract HelloWorld {

    string private text;
    address public owner;
    constructor() {
        text = "Hello World";
        owner = msg.sender;
    }
    function helloWorld() public view returns (string memory) {
        return text;
    }
    function setText(string calldata newText) public onlyOwner {
        text = newText;
    }
    function transferOwnership(address newOwner) public onlyOwner {
        owner = newOwner;
    }
    modifier onlyOwner()
    {
        require (msg.sender == owner, "Caller is not the owner");
        _;
    }
}


```

### Contract Functions

#### helloWorld

**Wendwossen Dufera**: I’ve successfully interacted with this function(helloWorld) using the smart contract address given above and got “gg” as an output.

**Lyle Davids**: I interacted with this function and got “gg” as output

**Ignas Apšega**: I was the first to interact with the Smart Contract. I got - “Hello World”

#### setText

**Wendwossen Dufera**: Tried to interact with this function(setText) using the smart contract address given above and got reverted. The reason for the reversion was “Caller is not the owner”. And I understood that this reversion occurred because the owner of the smart contract was not me. But, after lyle transferred the ownership of the smart contract to me, I am able to successfully change the state of the text from “testing it out” to “wende”. Here is the transaction hash of the transaction 

[Transaction](https://sepolia.etherscan.io/tx/0xda1d83f05ee66bc933d7686bc2298c07b38fb6b60dabe60dd9c9663710cd0dc4)


**Lyle Davids**: Interacted with this function 3 times, I successfully changed the text from “gg” to “12345” and again from “12345” to “testing it out”. Tried to interact again with the contract but it got reverted because I transferred ownership to Wendwossen
Transaction hashes - 
“gg” to “12345” - 
[Transaction](https://sepolia.etherscan.io/tx/0x862cde9914f5c9b7385db96ff9fd87f39137f1993dff0e5047e757a0628336da)

“12345” to “testing it out” - 
[Transaction](https://sepolia.etherscan.io/tx/0x34fa8b28379be2311fe35e5cc8726e7fe4a5e049e812c7f243fe77faac2ef3ab)

**Ignas Apšega**: Because I was the first to interact and deploy the contract I did change the text only once from - “Hello World” to “gg”
Transaction hashes - 
“Hello World” to “gg” - 
[Transaction](https://sepolia.etherscan.io/tx/0x69ac609b170bdfcddb1f04210c58d30ab22a942a992b02d2cebcca7b71b47893)


#### transferOwnership

**Wendwossen Dufera**: Tried to interact with this function(transferOwnership) too and got the same reversion like I got above which is “Caller is not the owner”. The reason for reversion here is the same as above(in the setText function), that’s I am not the owner of the smart contract. Then i got the ownership transferred from lyle, then was able to transfer the ownership back to lyle to the below address
“0xEd921BA5cc5EEB8971cD8929254627a4FDAF84C1”
The link of the transaction is down below

[Transaction](https://sepolia.etherscan.io/tx/0xe50968c8600426fe7db29ea062bb0f52030aed9ce9040900e426ebd4fad6b3ad)



**Lyle Davids**: Successfully interacted with this function of the smart contract, was able to transfer ownership to Wendwossen, at this address 0x889B0fA4E64C7b4a8e2E2EF48Fd013bab33f3699
[Transaction](https://sepolia.etherscan.io/tx/0xc9889e1c2751ce0a47aa2c6108fa20419ca9e7584130841621f4efb3bb5c44c5)

**Ignas Apšega**: This was the last function I used and successfully transferred ownership to Lyle.
[Transaction](https://sepolia.etherscan.io/tx/0x7b56adfae34febaf30394cb61b5a9330550499d1caaa6bc09a59cbfb1b2eb0c3)
