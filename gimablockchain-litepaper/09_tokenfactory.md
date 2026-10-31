# TokenFactory

### Description
TokenFactory (`contracts/TokenFactory.sol`) is a smart contract for deploying secure RPV-20 tokens and GimaTrust Badges, ensuring rug-proof protections from creation.

### Features
- Deploys tokens with embedded time-locks and multi-sig (e.g., `createRPV20Token(name, symbol, supply, lockDuration, strategyAddress)`).
- Mints badges with Zenrock dMPC verification (e.g., `mintTrustBadge(projectOwner, tier)`).
- Integrates with yield strategies for reward-generating tokens.

### Implementation
- Deployed via `scripts/deploy_contracts.py`.
- Tested in `tests/contracts/test_tokenfactory.js`.

### Example
A developer uses TokenFactory to launch a token tied to a yield strategy (e.g., `YearnStrategy.sol`), certified with a Gold badge, attracting LPs to a secure vault.
