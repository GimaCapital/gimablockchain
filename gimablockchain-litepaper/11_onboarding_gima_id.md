# Onboarding & Identity (Gima ID)

### Description
Gima ID is a human-readable identifier (e.g., `gima:0xabc...`) enabling seamless onboarding on Ethereum Layer-2 solutions, abstracting wallet and gas complexity.

### MVP – Relayer-Managed Subwallets
- **Mechanism**:
  - Each Gima ID maps to a subwallet created by the Gima Relayer (`apps/relayer-api/main.py`) and managed via Zenrock’s dMPC (`zenrock/client.py`).
  - Private keys are sharded across Zenrock’s distributed network, eliminating centralized custody risks.
  - Users onboard via the frontend (`apps/frontend`) without managing seed phrases or paying gas fees.
  - The Relayer validates requests, Zenrock signs transactions per policy, and transactions are broadcast to Layer-2.
- **Features**:
  - **User Experience**: Web2-like simplicity; users deposit to vaults, create tokens, or claim yields without Web3 complexity.
  - **Security**: Zenrock’s dMPC ensures no single point of failure; on-chain logs (txHash, Gima ID) enable auditability.
  - **Layer-2 Integration**: Leverages low-cost transactions for scalable onboarding.

### Example
A retail user signs up, receives `gima:0x123...`, and deposits 10 ETH into a yield-generating vault. The Relayer and Zenrock handle signing and gas abstraction transparently.

### Future
By Q3 2026, evolve Gima ID into a hybrid decentralized identifier (DID) model, extending to Solana and BNB Smart Chain via cross-chain messaging, native deployments, or oracles.
