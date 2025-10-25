# Yield Strategies

### Description
Yield strategies are smart contracts (`contracts/strategies/`, e.g., `AaveStrategy.sol`, `YearnStrategy.sol`) that optimize returns (10–20% APY) for RPV-20 vaults by integrating with external DeFi protocols.

### Features
- Allocates vault funds to high-yield pools while enforcing RPV-20’s time-locks and multi-sig protections.
- Zenrock dMPC signs reallocations to ensure security.
- DAO governs strategy parameters (e.g., allocation ratios).
- Certified by GimaTrust Badges for enhanced trust.

### Implementation
- Deployed via `scripts/deploy_contracts.py`.
- Tested in `tests/contracts/test_strategies.js`.

### Example
A vault uses `YearnStrategy.sol` to allocate 70% to a lending protocol, earning 15% APY, with time-locks preventing unauthorized withdrawals.
