# ADR-003: Server-side capture parsing

> **Status:** Proposed (Draft) · **Last updated:** 2026-11-02
> **Related:** [Capture sources](../../02-product/capture-sources.md) · [Architecture principles](../../03-architecture/architecture-principles.md) · [ADR-001](ADR-001-central-backend.md)

## Context
Notification formats change per bank and platform. Parsing on each client would duplicate logic and make fixes depend on app releases.

## Decision
- The client filters on device and sends only notifications from an app **allowlist**.
- The server parses deterministically per source; an LLM is only a fallback.
- Raw text is kept for a short period, then deleted; only the structured transaction and its origin remain.
- Endpoint `POST /capture-events` is idempotent. Input: source, raw text or structured fields, date, idempotency key. Output: confirmed transaction or pending-review item.
- Uncertain results are never treated as confirmed.
- Cross-source dedup (e.g. Wallet + bank) by amount, time and merchant.

## Consequences
- (+) Parser fixes ship without client releases; one implementation for all clients.
- (−) Raw text leaves the device; needs retention policy, consent and security review.
- (−) Retention period and LLM-fallback privacy rules still to define.
