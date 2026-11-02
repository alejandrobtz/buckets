# Product Principles

> **Purpose:** Single home for the rules that guide product decisions.
> **Status:** Draft · **Last updated:** 2026-11-02
> **Related:** [Vision](product-vision.md) · [Glossary](glossary.md) · [Architecture principles](../03-architecture/architecture-principles.md)

1. **Tracker-first, layers optional.** Recording income/expenses and viewing balances must deliver value alone. Buckets, goals, strategies and commitments never gate core features.
2. **Deterministic and auditable numbers.** Balances and calculations are reproducible from stored data. Every figure can be traced to its transactions.
3. **Trust is visible.** Uncertain data is never presented as confirmed fact. Completeness and reliability are surfaced through [Data Confidence](glossary.md#data-confidence).
4. **User corrections are respected.** Provenance and manual corrections are kept; automation must not silently overwrite them.
5. **A Bucket is not an account.** It is a logical allocation with a purpose ([glossary](glossary.md#bucket), [ADR-002](../04-delivery/decisions/ADR-002-optional-funding-container.md)). Balances are never double counted.
6. **Money is exact.** Integer minor units plus currency; never floating point. Transfers are not income or expense.
7. **AI explains, it does not decide.** AI may explain results that are backed by data; it is never the source of financial truth.
8. **Low-friction capture.** Prefer automatic capture where platforms allow; always provide manual entry and file import ([capture sources](../02-product/capture-sources.md)).
9. **Privacy by minimisation.** Collect and retain only what is needed; raw captured text is short-lived ([ADR-003](../04-delivery/decisions/ADR-003-server-side-capture-parsing.md)).
