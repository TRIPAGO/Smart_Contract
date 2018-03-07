# ICO TRIPAGO

# README

*TRIPAGO.sol* is a fixed supply contract with a fixed supply of 1000000000 that are initially assigned to the owner of the contract.
The Contract is based on ERC20 Token Standard.

## What is this repository for?
TRIPAGO ICO contract.

## How Does A TRIPAGO Contract Work?

Deploy the above *TRIPAGO.sol* smart contract and obtain its address.
The address which deployed the Smart Contract becomes the Owner of the Smart Contract.

### Token Balance
To check the token balance of token holder, **balanceOf()** function needs to be used.
For example, assume the TRIPAGO contract has two token holders:
* 0x111 with a balance of 50 TPG
* 0x222 with a balance of 100 TPG

The **balanceOf()** will return following values:
* balanceOf(0x111) will return 50
* balanceOf(0x111) will return 100


### Transfer Token Balance
To transfer TPG tokens to different address, **transfer()** function needs to be used.

For example,If 0x111 wants to transfer 10 TPG to 0x222,
0x111 will execute the function:
* transfer(0x222, 10)

The **balanceOf()** will now return following values:
* balanceOf(0x111) will return 40
* balanceOf(0x222) will return 110

### Approve and TransferFrom Token Balance
If 0x222 wants to authorise 0x111 to transfer some tokens on his behalf, then 0x222 will  execute the **approve()** function

For example,If 0x222 wants to approve 30 TPG to 0x111,
0x222 will execute the function:
* approve(0x111, 30)

The approve data structure will now contain the following information:
* allowed[0x222][0x111] = 30
	
Now, if 0x111 wants to later transfer some tokens from 0x222 to itself, then 0x111 will execute **transferFrom()** function

For example, if 0x111 wants to transfer 20 TPG to itself,
0x111 will execute function:
* transferFrom(0x222, 0x111, 20)
 
The **balances** data structure will contain the following information:
* balances[0x111] = 60
* balances[0x222] = 90

And, approve data structure will now contain the following information:
* allowed[0x222][0x111] = 10

Thus, 0x111 can still spend 10 TPG from 0x222,

The **balanceOf()** will now return following values:
* balanceOf(0x111) will return 60
* balanceOf(0x222) will return 90

## NOTE : 
The above two addresses(0X111, 0X222) taken in Example are not Valid Ethereum Addresses, to make transaction you need to have a valid Ethereum Address.