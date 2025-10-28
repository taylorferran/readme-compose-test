# Compose Network Demo

<div align="center">
  <img src="public/images/logo/light.svg" alt="Compose Network Logo" width="400" />
</div>

A demo web app showcasing Compose Network's synchronous composability across Ethereum rollups. This demo enables atomic transactions between different blockchain networks through Compose's Shared Publisher coordination layer.

## What is Compose Network?

Compose Network unites Ethereum rollups to enable instant and composable transactions, where actions across rollups can happen together in a single atomic flow. It's powered by a Shared Publisher, a coordination layer that allows rollups to execute operations synchronously while each maintains its own sequencing and independence.

## Features

### Bridge Functionality
- **Cross-chain ETH bridging** from Hoodi testnet to Rollup A or Rollup B

### Swap Functionality  
- **Token swaps** between SSV, ETH, and USDC
- **Cross-rollup swaps** (Rollup A ↔ Rollup B)
- **Same-rollup swaps** within Rollup A or Rollup B

### Key Capabilities
- **Synchronous composability** - transactions either succeed together or revert together
- **Smart account integration** using Kernel accounts and ECDSA validators

## How It Works

This demo implements the core Compose Network transaction flow:

### End-to-End Transaction Flow
1. **Account Setup**: Creates Kernel accounts and ECDSA validators on source and destination chains
2. **Allowance Management**: Verifies and sets ERC-20 allowances to bridge contracts
3. **UserOperation Preparation**: Builds and signs UserOperations for both chains using `compose_buildSignedUserOpsTx`
4. **Cross-chain Settlement**: Submits all of the transactions together using `eth_sendXTransaction` and returns the transaction hashes

### Technical Architecture
- **Frontend**: React + TypeScript + Vite
- **Blockchain Integration**: Wagmi + Viem for Ethereum interactions
- **Smart Accounts**: ZeroDev Kernel accounts with ECDSA validation
- **UI Components**: Radix UI + Tailwind CSS

## Quick Start

### Prerequisites
- Node.js >= 18.0.0
- pnpm >= 8.0.0

### Installation & Development

```bash
# Install dependencies
pnpm install

# Start development server
pnpm run dev
```

## Supported Networks

- **Hoodi Testnet**: Ethereum Layer 1 testnet for initial ETH deposits
- **Rollup A**: Compose demo rollup showcasing synchronous composability
- **Rollup B**: Second Compose demo rollup for cross-chain operations

## Supported Tokens

- **ETH**: Native Ethereum token
- **SSV**: Secret Shared Validators token
- **USDC**: USD Coin stablecoin

## Learn More

- **[Compose Network Documentation](https://docs.compose.network)**
- **[Composable dApps Overview + code walkthrough](https://docs.compose.network/developers/getting-started/composable-dapps)** - Understanding the transaction flow
- **[ZeroDev Documentation](https://docs.zerodev.app)** - Smart account infrastructure

## Contributing

This is a demonstration application showcasing Compose Network capabilities. For questions about Compose Network or to contribute to the protocol, please visit the [official documentation](https://docs.compose.network).
