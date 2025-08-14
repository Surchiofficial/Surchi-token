
🌏 Project Origin — Singapore
Name: Surchi Token (SURCHI)
Blockchain: Binance Smart Chain (BSC)
Category: Utility Token for the Surchi App

Project Overview
Surchi Token is a Singapore-originated blockchain project built on the Binance Smart Chain (BSC), designed to power the Surchi App ecosystem. It serves as the exclusive utility token for premium features, in-app purchases, and secure digital transactions.

Singapore’s position as a global fintech hub gives Surchi Token a strategic advantage — combining strong investor trust, a transparent regulatory environment, and access to Asia’s fastest-growing tech markets.

Core Vision
To build a stable, investor-focused token with strong liquidity and a solid utility base, driving real adoption through the Surchi App while ensuring long-term value growth.

Key Features

Fixed Total Supply: 1 Billion SURCHI

Liquidity Lock: 80–85% for price stability and investor safety

No Minting After Launch: Immutable supply ensures scarcity value

Presale Structure: Fair and attractive for both small and large investors

Utility-Driven Adoption: Direct integration with the Surchi App’s premium services and marketplace


Why Singapore?

Global Trust: One of the world’s leading blockchain and fintech innovation hubs

Investor-Friendly Environment: Clear compliance and pro-investment policies

Strategic Market Access: Gateway to Southeast Asia and global blockchain markets


surchi-token/
│
├── contracts/               # Smart contract files
│   └── SurchiToken.sol       # Main BEP-20 token contract
│
├── scripts/                  # Deployment scripts
│   └── deploy.js
│
├── README.md                 # Project overview & instructions
├── LICENSE                   # Open-source license
├── .gitignore                # Ignore node_modules & build files
├── package.json              # Node.js package info
└── hardhat.config.js         # Hardhat config for deployment

# Surchi Token (SURCHI)

## Overview
Surchi Token is a Singapore-originated blockchain project built on the Binance Smart Chain (BSC). It powers the Surchi App ecosystem, enabling premium in-app purchases, digital transactions, and utility-driven adoption.

## Key Features
- Total Supply: **1,000,000,000 SURCHI**
- Blockchain: **Binance Smart Chain**
- Liquidity Lock: **80–85%**
- No Minting After Launch
- Fair Presale Structure

## Contract Address
_To be updated after deployment_

## Tech Stack
- Solidity
- Hardhat
- OpenZeppelin

## License
MIT License


--- contracts/SurchiToken.sol --- // SPDX-License-Identifier: MIT pragma solidity ^0.8.20;

import "@openzeppelin/contracts/token/ERC20/ERC20.sol"; import "@openzeppelin/contracts/token/ERC20/extensions/ERC20Burnable.sol"; import "@openzeppelin/contracts/token/ERC20/extensions/ERC20Permit.sol";

/**

SURCHI Token — Fixed-supply BEP-20 (BNB Chain)

Total Supply: 1,000,000,000 (18 decimals)

No minting, no owner, no admin keys */ contract SURCHI is ERC20, ERC20Burnable, ERC20Permit { uint256 public constant INITIAL_SUPPLY = 1_000_000_000 * 10 ** 18;

constructor() ERC20("Surchi", "SURCHI") ERC20Permit("Surchi") { _mint(msg.sender, INITIAL_SUPPLY); }

// Block accidental BNB transfers receive() external payable { revert("SURCHI: Cannot receive BNB"); }

fallback() external payable { revert("SURCHI: Invalid function"); } }


--- .gitignore --- node_modules/ .env artifacts/ cache/ .DS_Store Thumbs.db

--- .env.example --- DEPLOYER_PRIVATE_KEY= BSC_TESTNET_RPC=https://data-seed-prebsc-1-s1.binance.org:8545/ BSC_MAINNET_RPC=https://bsc-dataseed.binance.org/

--- Repository structure --- your-repo/ │ ├── contracts/ │   ├── SurchiToken.sol │   └── TeamVesting.sol │ ├── scripts/ │   └── deploy.js │ ├── .gitignore ├── .env.example ├── hardhat.config.js ├── README.md

--- Deployment ---

1. Install dependencies:



npm install --save-dev hardhat @nomiclabs/hardhat-ethers ethers @openzeppelin/contracts dotenv

2. Compile:



npx hardhat compile

3. Deploy:



npx hardhat run --network bscTestnet scripts/deploy.js

4. Verify on BscScan:



npx hardhat verify --network bscTestnet <DEPLOYED_CONTRACT_ADDRESS>

