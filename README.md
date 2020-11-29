# Mooniswap
## credits to 1inch team.
[![Build Status](https://github.com/CryptoManiacsZone/mooniswap/workflows/CI/badge.svg)](https://github.com/CryptoManiacsZone/mooniswap/actions)
[![Coverage Status](https://coveralls.io/repos/github/CryptoManiacsZone/mooniswap/badge.svg?branch=master)](https://coveralls.io/github/CryptoManiacsZone/mooniswap?branch=master)

AMM with a beautiful mind and further developed by the team of ethereumgeeks in order to be used with the [gasprod]() project . 

## Factory Address
[https://etherscan.io/address/0x71CD6666064C3A1354a3B4dca5fA1E2D3ee7D303](https://etherscan.io/address/0x71CD6666064C3A1354a3B4dca5fA1E2D3ee7D303)

## Context for the project 
1. in order to first interact with the vault with the bot  for [gasprod]() project , the integration of mooniswap to buy the chitokens is the first step , which will be done via the 

2. also i forked the project to see its functionality and how it can be suitably integrated to other project / or dissecting the security vulnerablities . 



## Swap
```solidity
/**
* @param src address of the source token to exchange
* @param dst token address that will received
* @param amount amount to exchange
* @param minReturn minimal amount of the dst token that will receive (if result < minReturn then transaction fails)
* @param referral 1/20 from LP fees will be minted to referral wallet address (in liquidity token) (in case of address(0) no mints) 
* @return result received amount
*/
function swap(address src, address dst, uint256 amount, uint256 minReturn, address referral) external payable returns(uint256 result);
```

## TODO : you will have to fetch the address of the destination address ( being the vault address ) in order to  transfer the swapped tokens  and the chi tokens ( we will limit the destination  token in the modified version of the website to support only one contract implementation )




## Deposit
```solidity
/**
* @dev provide liquidity to the pool and earn on trading fees
* @param amounts [amount0, amount1] for liquidity provision (each amount sorted by token0 and token1) 
* @param minAmounts minimal amounts that will be charged from sender address to liquidity pool (each amount sorted by token0 and token1) 
* @return fairSupply received liquidity token amount
*/
function deposit(uint256[] calldata amounts, uint256[] calldata minAmounts) external payable returns(uint256 fairSupply);
```

## here we will be getting the better liquidity pool in order to get the corresponding chitokens at better margin and without  larger slipage. 





## Withdraw
```solidity
/**
* @dev withdraw liquidity from the pool
* @param amount amount to burn in exchange for underlying tokens
* @param minReturns minimal amounts that will be transferred to sender address in underlying tokens  (each amount sorted by token0 and token1) 
*/
function withdraw(uint256 amount, uint256[] memory minReturns) external;
```

## Create new pool
```solidity
/**
* @dev tokens will be sorted and stored according to token0 < token1
* @param tokenA 
* @param tokenB 
* @return pool created pool address
*/
function deploy(address tokenA, address tokenB) public returns(address pool);
```
