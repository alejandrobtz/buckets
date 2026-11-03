# ADR-004: Modular monolith behind a single API

> **Status:** Proposed (Draft) · **Last updated:** 2026-11-03
> **Related:** [ADR-001](ADR-001-central-backend.md) · [Architecture principles](../../03-architecture/architecture-principles.md) · [Bounded contexts](../../01-domain/bounded-contexts.md) · [Brief §12](../../../product-brief.md)

## Context
[ADR-001](ADR-001-central-backend.md) separates clients from a central backend. This ADR covers a different question: how that backend is structured internally. Bounded contexts are still provisional, balances must be consistent, and the team is small.

## Decision
- The backend is a **modular monolith**: one deployable application and one database, organised into modules that follow the [bounded contexts](../../01-domain/bounded-contexts.md).
- Clients depend only on the public API ([ADR-001](ADR-001-central-backend.md)); the internal structure is invisible to them.
- Modules interact only through explicit interfaces or domain events. No module reads or writes another module's data directly.
- Dependency rules are enforced by automated tests.
- Not microservices at this stage.

## Consequences
- (+) Simple to build and operate; atomic transactions help keep balances consistent.
- (+) Boundaries can be changed by refactoring while contexts are still being validated.
- (+) A module can later be extracted into its own service (e.g. capture parsing) if the boundaries were respected.
- (−) Requires discipline; without enforcement it degrades into a tangled monolith.
- (−) All modules scale and deploy together.

## Revisit when
There is a measurable reason to split a module: scale, team structure or isolation of a component.
