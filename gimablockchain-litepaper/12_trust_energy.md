# Trust Energy (TE)

### Description
Trust Energy (TE) is a user-friendly unit to abstract transaction costs (gas), managed by the Relayer to enhance accessibility.

### Models
- **Relayer-Sponsored**: Covers costs for small actions (e.g., low-value deposits), free for users.
- **TE-Billed**: Charges TE for large operations (e.g., token creation), discounted via GIMA token staking.

### Implementation
TE ledger maintained in the Relayer (`apps/relayer-api`); displayed in the frontend (`apps/frontend/src`).

### Future
Extends TE to Solana and BNB Smart Chain, abstracting chain-specific costs (e.g., SOL or BNB gas).

### Example
A user deposits to a vault without paying gas; the Relayer sponsors the transaction using TE.
