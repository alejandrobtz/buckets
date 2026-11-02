# Releases

> **Purpose:** Proposed release roadmap.
> **Status:** Draft — proposal · **Last updated:** 2026-11-02
> **Related:** [Vision](../00-foundation/product-vision.md) · [Bounded contexts](../01-domain/bounded-contexts.md) · [Capture sources](../02-product/capture-sources.md)

| Release | Theme | Outcome |
|---|---|---|
| **R0** | Foundations | Repo, docs, decisions, stack ADR, capture-format spike. |
| **R1** | Reliable Financial Operations | Accounts, transactions, transfers, balances, capture + review queue, Data Confidence. **Must be useful for tracker-only users.** |
| **R2** | Reviews & discovery | Financial Reviews, insights from recorded data. |
| **R3** | Planning | Financial Periods, Buckets, goals, commitments. |
| **R4** | Guidance | Strategies and decision support. |
| **R5** | AI Advisor | Data-backed explanations. |

## Spike (R0)

2–3 days: minimal Android app that only logs raw text of real notifications for about a week, to learn the formats the backend must parse ([ADR-003](decisions/ADR-003-server-side-capture-parsing.md)).
