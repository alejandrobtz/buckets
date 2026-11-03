# Buckets

> **Status:** Draft · **Last updated:** 2026-11-03

Buckets is a financial operating system for individuals and households: it moves people from *recording transactions* to *understanding, planning and deciding*.

Tracker-only use (log income and expenses, see balances) is a valid, permanent mode. Goals, Buckets, strategies and commitments are optional layers.

## Document map

| Area | Document | Purpose |
|---|---|---|
| Overview | [product-brief.md](product-brief.md) | Original product brief (Draft v0.1). |
| Foundation | [docs/00-foundation/product-vision.md](docs/00-foundation/product-vision.md) | Why Buckets exists and where it is going. |
| Foundation | [docs/00-foundation/product-principles.md](docs/00-foundation/product-principles.md) | Rules that guide product decisions. |
| Foundation | [docs/00-foundation/glossary.md](docs/00-foundation/glossary.md) | Canonical definitions of domain terms. |
| Domain | [docs/01-domain/bounded-contexts.md](docs/01-domain/bounded-contexts.md) | Provisional module boundaries. |
| Product | [docs/02-product/capture-sources.md](docs/02-product/capture-sources.md) | How transactions enter the system, per platform. |
| Architecture | [docs/03-architecture/architecture-principles.md](docs/03-architecture/architecture-principles.md) | Architectural constraints (stack-agnostic). |
| Delivery | [docs/04-delivery/releases.md](docs/04-delivery/releases.md) | Proposed release roadmap R0–R5. |
| Delivery | [docs/04-delivery/decisions/](docs/04-delivery/decisions/) | Architecture Decision Records (ADR-001…004). |

## Conventions

- Documentation is written in **English** and lives in this repository.
- Every document starts with a purpose, a **Status** (`Draft` · `In Review` · `Accepted` · `Superseded`) and a **Last updated** date.
- Each rule has one home. Other documents link to it instead of repeating it (definitions → glossary, principles → product-principles, architecture constraints → architecture-principles).
- The technology stack is **not decided**; see [Open questions](#open-questions).

## Open questions

1. **Market:** Colombia / COP is the probable first market (to confirm).
2. **Platform:** Android-first for automatic capture; iOS via Wallet Shortcut + manual entry + file import (to confirm).
3. **Banks / wallets to cover first:** e.g. Bancolombia, Nequi, Daviplata (to define). First target audience also to define.
4. **Stack:** backend TypeScript/Postgres vs .NET; mobile React Native/Expo + Kotlin module vs native vs Flutter (undecided).
