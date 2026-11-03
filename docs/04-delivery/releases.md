# Releases

> **Purpose:** Proposed release roadmap.
> **Status:** Draft — proposal · **Last updated:** 2026-11-03
> **Related:** [Vision](../00-foundation/product-vision.md) · [Bounded contexts](../01-domain/bounded-contexts.md) · [Capture sources](../02-product/capture-sources.md) · [Brief §14](../../product-brief.md)

| Release | Theme | Outcome |
|---|---|---|
| **R0** | Foundations | Repo, docs, decisions, stack ADR, capture-format spike. |
| **R1** | Reliable Financial Operations + notification capture | Core ledger plus assisted capture from notifications. **Must be useful for tracker-only users.** |
| **R1.x** | Additional capture sources | Email and SMS capture, after R1 proves the pipeline. |
| **R2** | Reviews & discovery | Financial Reviews, insights from recorded data. |
| **R3** | Planning | Financial Periods, Buckets, goals, commitments. |
| **R4** | Guidance | Strategies and decision support. |
| **R5** | AI Advisor | Data-backed explanations. |

## R1 scope

- **Core:** accounts, transactions (income, expense), transfers, categories, editing, balances, basic cash-flow and category summaries, inspectable transactions behind every total.
- **Manual entry:** always available; the baseline for tracker-only use.
- **Capture from notifications only** (see [capture sources](../02-product/capture-sources.md)):
  - Android: notification listener for wallets and bank apps.
  - iOS: Shortcuts automation with the Wallet "Transaction" trigger.
- **Backend:** idempotent `POST /capture-events`, server-side parsing, review queue for uncertain items, cross-source dedup ([ADR-003](decisions/ADR-003-server-side-capture-parsing.md)).
- **Immediate categorization prompt** for PSE and Bre-B payments, shown when the notification is captured (Android full, iOS partial); see [capture sources](../02-product/capture-sources.md#immediate-categorization-of-pse-and-bre-b-payments).
- **Trust:** source indicators and [Data Confidence](../00-foundation/glossary.md#data-confidence), including visible partial coverage.
- **Optional:** CSV import, only if it can be made reliable (per brief).

### Out of R1

Email and SMS capture (R1.x), planning, guidance, AI.

### Exit criteria

- A manual-only user gets correct balances and can inspect the transactions behind each total.
- Uncertain captures are never confirmed automatically.
- Coverage gaps (e.g. PSE transfers not covered by wallet notifications) are visible to the user.

## Spike (R0)

2–3 days: minimal Android app that only logs raw text of real notifications for about a week, to learn the formats the backend must parse. It gates the start of R1 capture work ([ADR-003](decisions/ADR-003-server-side-capture-parsing.md)).
