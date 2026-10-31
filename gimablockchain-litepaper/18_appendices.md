# Appendices

### Technical References
- **Smart Contracts**:
  - `contracts/RPV20.sol`: Rug-Proof Vaults token standard.
  - `contracts/GimaBadge.sol`: NFT-based trust certifications.
  - `contracts/TokenFactory.sol`: Token and badge deployment.
  - `contracts/StakingRewards.sol`: GIMA token staking rewards.
  - `contracts/strategies/AaveStrategy.sol`, `YearnStrategy.sol`: Yield optimization.
  - `contracts/Governance.sol`: DAO governance.
- **Relayer**: `apps/relayer-api/main.py`, `zenrock/client.py`.
- **Deployment**: `infrastructure/deploy.yaml`, `config/networks.json`.
- **Testing**: `tests/contracts/test_rpv20.js`, `test_gimabadge.js`, `test_tokenfactory.js`, `test_strategies.js`.

### Glossary
- **RPV-20**: Rug-Proof Vaults token standard with time-locks and multi-sig.
- **Gima ID**: Human-readable identifier for onboarding.
- **Trust Energy (TE)**: Unit for abstracting transaction costs.
- **dMPC**: Distributed Multi-Party Computation for secure signing.

### Code Example (TokenFactory.sol)
```solidity
// Simplified excerpt from contracts/TokenFactory.sol
contract TokenFactory {
    event TokenCreated(address indexed creator, address tokenAddress, uint256 supply);

    function createRPV20Token(
        string memory name,
        string memory symbol,
        uint256 initialSupply,
        uint256 lockDuration,
        address strategyAddress
    ) public returns (address) {
        RPV20 newToken = new RPV20(name, symbol, initialSupply, lockDuration, strategyAddress);
        emit TokenCreated(msg.sender, address(newToken), initialSupply);
        return address(newToken);
    }

    function mintTrustBadge(address projectOwner, uint8 tier) public returns (uint256) {
        require(zenrockVerify(projectOwner, tier), "Invalid verification");
        uint256 badgeId = gimaBadges.mint(projectOwner, tier);
        return badgeId;
    }
}
