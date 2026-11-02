# ADR-002: Bucket is a logical allocation; Funding Container is optional

> **Status:** Proposed (Draft) · **Last updated:** 2026-11-02
> **Related:** [Glossary: Bucket](../../00-foundation/glossary.md#bucket) · [Product principles](../../00-foundation/product-principles.md)

## Context
Users keep money in real accounts and sub-accounts (e.g. Nequi/Bancolombia pockets) but think in purposes.

## Decision
A Bucket is a logical allocation with a purpose, not an account. Linking it to a Funding Container is optional. Sub-accounts/pockets are never summed into their parent.

## Consequences
- (+) Buckets work without mapping every peso to an account; tracker-only unaffected.
- (+) No double counting.
- (−) Unlinked Buckets cannot be verified against a real balance; Data Confidence should reflect that.
