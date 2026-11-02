# Architecture Principles

> **Purpose:** Stack-agnostic architectural constraints.
> **Status:** Draft · **Last updated:** 2026-11-02
> **Related:** [Bounded contexts](../01-domain/bounded-contexts.md) · [ADR-001](../04-delivery/decisions/ADR-001-central-backend.md) · [ADR-003](../04-delivery/decisions/ADR-003-server-side-capture-parsing.md) · [Product principles](../00-foundation/product-principles.md)

1. **Modular monolith** with explicit module boundaries; not microservices.
2. **Central backend, API-first.** All core logic lives server-side behind an OpenAPI contract; clients are generated and thin ([ADR-001](../04-delivery/decisions/ADR-001-central-backend.md)).
3. **Money as integers** in minor units plus currency; no floats.
4. **Deterministic core.** Balances, periods and dedup are reproducible and auditable; AI sits outside the financial source of truth.
5. **Idempotent ingestion.** Capture endpoints accept an idempotency key and are safe to retry ([ADR-003](../04-delivery/decisions/ADR-003-server-side-capture-parsing.md)).
6. **Provenance retained.** Every transaction records its origin and any user correction.
7. **Uncertainty is explicit.** Uncertain data goes to a review queue, never silently confirmed.
8. **Data minimisation.** Short retention for raw captured text.

## Not decided

The technology stack (backend language/database, mobile framework) is an open question; see [README](../../README.md#open-questions). A future ADR will record it.
