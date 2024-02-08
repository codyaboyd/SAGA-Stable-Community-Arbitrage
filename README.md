# SAGA-Stable-Community-Arbitrage
A stable-coin vault for public arbitrage.

# SAGA Token Smart Contract Documentation

## Overview

The SAGA Token Smart Contract is a comprehensive ERC20 token with added functionalities, including minting tokens in exchange for other stablecoins (DAI, USDC, fUSDT, MIM) and burning mechanisms to convert SAGA tokens back into these stablecoins. Developed using Solidity ^0.8.9, it adheres to the MIT license.

## Core Components

### Context Contract

- Provides `_msgSender()` and `_msgData()` to access transaction context.

### Ownable Contract

- Implements ownership management with `onlyOwner` modifier.
- Functions include `owner()`, `renounceOwnership()`, and `transferOwnership(address newOwner)`.

### ERC20 Standard

- Implements standard ERC20 functionalities including `transfer()`, `approve()`, `transferFrom()`, `increaseAllowance()`, and `decreaseAllowance()`.

### ERC20 Metadata

- Provides token information such as `name()`, `symbol()`, and `decimals()`.

### ERC20Burnable

- Extends ERC20 with `burn()` and `burnFrom()` functions for token burning.

## SAGA Token Specific Functions

### Minting Functions

- `mintFromDAI(uint256 amount)`: Mint SAGA tokens by depositing DAI.
- `mintFromUSDC(uint256 amount)`: Mint SAGA tokens by depositing USDC.
- `mintFromFUSDT(uint256 amount)`: Mint SAGA tokens by depositing fUSDT.
- `mintFromMIM(uint256 amount)`: Mint SAGA tokens by depositing MIM.

### Burning Functions

- `sagaToDai(uint256 amount)`: Convert SAGA tokens back to DAI.
- `sagaToFusdt(uint256 amount)`: Convert SAGA tokens back to fUSDT.
- `sagaToUsdc(uint256 amount)`: Convert SAGA tokens back to USDC.
- `sagaToMim(uint256 amount)`: Convert SAGA tokens back to MIM.

### Gate Controls

- `setMimGate(uint256 mimStatus)`: Enable/disable minting with MIM.
- `setDaiGate(uint256 daiStatus)`: Enable/disable minting with DAI.
- `setFusdtGate(uint256 fusdtStatus)`: Enable/disable minting with fUSDT.
- `setUsdcGate(uint256 usdcStatus)`: Enable/disable minting with USDC.

### Balance Queries

- `getUSDCBalance()`: Query the contract's USDC balance.
- `getFUSDTBalance()`: Query the contract's fUSDT balance.
- `getDAIBalance()`: Query the contract's DAI balance.
- `getMIMBalance()`: Query the contract's MIM balance.

## Security and Ownership

Ownership functions are secured with the `onlyOwner` modifier, ensuring that only the owner can toggle minting gates and perform sensitive operations.

## Usage

The SAGA token can be minted by depositing specific stablecoins into the contract. It allows users to exchange stablecoins for SAGA tokens, which can then be converted back to any of the accepted stablecoins, enabling a versatile mechanism for token liquidity and utility.

## Conclusion

The SAGA Token Smart Contract offers a robust solution for creating a convertible token system on the Ethereum blockchain. By leveraging ERC20 standards and extending functionality to include minting and burning through stablecoin deposits, it provides a flexible platform for token issuance and management.
