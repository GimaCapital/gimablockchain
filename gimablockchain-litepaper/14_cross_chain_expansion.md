# Cross-Chain Expansion

### Current State
GimaBlockchain operates exclusively on Ethereum Layer-2, leveraging EVM compatibility and low-cost transactions.

### Future (2026)
Extend the protocol to Solana and BNB Smart Chain:

- **Cross-Chain Messaging Protocols**: Use interoperability layers (e.g., Chainlink CCIP, LayerZero) to send vault, badge, or strategy instructions.
- **Native Deployments**: Deploy Rust programs on Solana and Solidity contracts on BNB Smart Chain.
- **Oracle-Based Synchronization**: Sync vault states, yields, and badge verifications across chains.
- **Unified Identity Layer**: Extend Gima ID to map to subwallets on Solana and BNB Smart Chain.

### Example
A Solana user deposits to a native RPV-20 vault using Gima ID; an oracle syncs audit data with Layer-2, and Zenrock signs multi-sig actions.

### Benefits
Access Solana’s high-performance DeFi and BNB Smart Chain’s cost-efficient ecosystem while maintaining rug-proof guarantees.
