# Security & Governance

### Security Mechanisms
- **Zenrock dMPC**: Shards private keys across a distributed network, enforcing n-of-m policies for vault, badge, and strategy actions (`zenrock/client.py`).
- **RPV-20 Protections**: Time-locks and multi-sig prevent unauthorized withdrawals.
- **Relayer Policies**: Enforce transaction limits (e.g., daily $10K cap) and validation rules.
- **Auditability**: On-chain logs (via `scripts/verify_contracts.js`) ensure transparency, verifiable via block explorers.

### Governance
A decentralized autonomous organization (DAO) implemented via `Governance.sol` enables GIMA token holders to vote on:
- GimaTrust Badge issuance.
- Yield strategy parameters.
- Protocol upgrades and TE rules.

### Cross-Chain Security
Future Zenrock dMPC signatures for Solana/BNB Smart Chain operations, maintaining consistent security.
