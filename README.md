# ZenithTrace

Built for Base

ZenithTrace is a compact, Base-first repository focused on validating Base network connectivity, wallet onboarding, and read-only RPC interactions using official Coinbase tooling.

The repository is intentionally lightweight and serves as a repeatable diagnostic surface for Base infrastructure rather than a feature-complete decentralized application.

## Project Intent

ZenithTrace exists to:
- Confirm Base Mainnet and Base Sepolia availability
- Exercise OnchainKit wallet connection flows
- Validate chainId consistency and RPC responses
- Provide clear Basescan explorer references

## Networks

Base Sepolia  
chainId (decimal): 84532  
Explorer: https://sepolia.basescan.org  
RPC: https://sepolia.base.org  

Base Mainnet  
chainId (decimal): 8453  
Explorer: https://basescan.org  
RPC: https://mainnet.base.org  

## Runtime Behavior

Primary file: app/zenithTrace.ts

When executed, the application:
- Initializes an OnchainKitProvider bound to the selected Base network
- Presents wallet connection UI
- Uses Viem to query Base RPC endpoints
- Retrieves:
  - RPC-reported chainId
  - latest block height
  - native ETH balance for a supplied address
- Exposes Basescan URLs for direct inspection

## Repository Layout

- app/
  - zenithTrace.ts  
    React entry point combining wallet UX with Base RPC reads.

Common companion files:
- package.json
- tsconfig.json
- index.html / main.tsx
- .env (optional)

## Libraries

OnchainKit  
https://github.com/coinbase/onchainkit  

Viem  
EVM client for Base onchain reads  

## Installation & Usage

Requirements:
- Node.js 18+
- Browser environment with wallet support

Install dependencies using your preferred package manager and run the project with a standard React/Vite or Next.js development setup.

Optional environment variables:
- VITE_BASE_RPC_URL
- VITE_BASE_SEPOLIA_RPC_URL

## Author

GitHub: https://github.com/flytrapturtle

Public contact (email): your-name@proton.me  

Public contact (X): https://x.com/nazarovavaria 

## License

MIT License

## Testnet Deployment (Base Sepolia)

As part of pre-production validation, one or more contracts may be deployed to the Base Sepolia test network to confirm correct behavior and tooling compatibility.

Network: Base Sepolia  
chainId (decimal): 84532  
Explorer: https://sepolia.basescan.org  

Contract #1 address:  
0x5444a48a7576c9e15ec65d59426021471443a4b5

Deployment and verification:
- https://sepolia.basescan.org/address/0x5444a48a7576c9e15ec65d59426021471443a4b5
- https://sepolia.basescan.org/0x5444a48a7576c9e15ec65d59426021471443a4b5/0#code  

Contract #2 address (optional):  
0xe74b41c9bda0a9e8c5dc3d4ade8f01a2b2a3e15b

Deployment and verification:
- https://sepolia.basescan.org/address/0xe74b41c9bda0a9e8c5dc3d4ade8f01a2b2a3e15b
- https://sepolia.basescan.org/0xe74b41c9bda0a9e8c5dc3d4ade8f01a2b2a3e15b/0#code  

These testnet deployments provide a controlled environment for validating Base tooling, account abstraction flows, and read-only onchain interactions prior to Base Mainnet usage.
