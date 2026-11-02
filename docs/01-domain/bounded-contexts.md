# Bounded Contexts (Provisional)

> **Purpose:** Propose module boundaries for the modular monolith.
> **Status:** Draft — provisional, expected to change · **Last updated:** 2026-11-02
> **Related:** [Architecture principles](../03-architecture/architecture-principles.md) · [Glossary](../00-foundation/glossary.md) · [Releases](../04-delivery/releases.md)

| Context | Responsibility | Key terms | Likely release |
|---|---|---|---|
| **Financial Operations** | Accounts, Transactions, Transfers, Balances, capture ingestion, dedup, review queue, Data Confidence | Account, Transaction, Transfer, Balance, Capture Event | R1 |
| **Financial Planning** | Financial Periods, Buckets, goals, commitments | Financial Period, Bucket, Funding Container | R3 |
| **Financial Guidance** | Strategies, options and trade-offs for decisions | — | R4 |
| **Household** | Membership, roles, sharing | Household | R1+ |
| **Integrations** | Bank/wallet/file connectors and source-specific parsers | Capture Event | R1 |
| **AI Advisor** | Natural-language explanations of data-backed results | — | R5 |

## Notes

- Contexts communicate through explicit interfaces; no reaching into another context's data ([architecture principles](../03-architecture/architecture-principles.md)).
- Boundaries are candidates. Revisit after R1 with real usage.
