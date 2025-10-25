# GimaTrust Badges

### Description
GimaTrust Badges are NFT-based certifications (`contracts/GimaBadge.sol`) issued via DAO governance and Zenrock-verified audits to enhance project trust and credibility.

### Tiers
- **Bronze**: KYC verification for basic trust.
- **Silver**: Code audit for technical reliability.
- **Gold**: Full compliance and security audit for maximum credibility.

### Purpose
Certified vaults attract LPs, boosting APY by 2–5% through increased trust and participation.

### Implementation
- Minted via TokenFactory (`contracts/TokenFactory.sol`).
- Tested in `tests/contracts/test_gimabadge.js` for minting and verification logic.

### Example
A project earns a Silver badge after a code audit, increasing its vault’s APY and attracting more LPs.
