# Architecture

GimaBlockchain’s architecture leverages Ethereum Layer-2’s scalability and security, with modular components for seamless integration and user experience:

- **Frontend (`apps/frontend`)**: A React + Vite interface for vault deposits, badge minting, token creation, and Trust Energy display, accessible via Gima ID.
- **Gima Relayer (`apps/relayer-api/main.py`)**: A Python-based service that validates user requests, interfaces with Zenrock for signing, and broadcasts transactions to Layer-2 networks.
- **Zenrock dMPC (`zenrock/client.py`)**: A distributed signing mechanism that shards private keys across a secure network, enforcing n-of-m policies (e.g., 3-of-5 for high-value actions) to eliminate single points of failure (`config/zenrock.json`).
- **Smart Contracts (`contracts/`)**:
  - `RPV20.sol`: Implements time-locked, multi-sig vaults for rug-proof liquidity.
  - `GimaBadge.sol`: Mints NFT-based trust certifications.
  - `TokenFactory.sol`: Deploys RPV-20 tokens and badges, integrated with yield strategies.
  - `StakingRewards.sol`: Distributes GIMA token rewards for staking.
  - `strategies/*`: Yield optimization contracts (e.g., `AaveStrategy.sol`, `YearnStrategy.sol`) for vault returns.
  - `Governance.sol`: Enables DAO-based voting on protocol parameters and badge issuance.
- **Infrastructure**: Deployed on Ethereum Layer-2 (`infrastructure/deploy.yaml`, `config/networks.json`), optimized for low-cost, high-throughput transactions.
- **Cross-Chain Plans**: Future support for Solana (Rust-based programs) and BNB Smart Chain (Solidity, EVM-compatible) via cross-chain messaging, native deployments, or oracles.

**Transaction Flow**:

1. A user with Gima ID (e.g., `gima:0xabc...`) initiates an action (e.g., vault deposit, token creation) via the frontend (POST `/api/action`).
2. The Relayer validates the request and forwards it to Zenrock’s dMPC for signing, adhering to predefined policies (e.g., daily transaction limits, multi-sig for withdrawals).
3. The signed transaction is broadcast to Layer-2, logged on-chain for auditability (txHash, Gima ID).
