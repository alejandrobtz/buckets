# ADR-001: Central backend, API-first

> **Status:** Proposed (Draft) · **Last updated:** 2026-11-02
> **Related:** [Architecture principles](../../03-architecture/architecture-principles.md) · [ADR-003](ADR-003-server-side-capture-parsing.md)

## Context
Buckets must serve multiple clients (Android, iOS, web, iOS Shortcuts) with identical financial results.

## Decision
A single central backend holds all core logic (domain, balances, periods, dedup, ingestion, review queue). It exposes an OpenAPI contract; clients are generated from it and limited to capture and presentation. Internally a modular monolith.

## Consequences
- (+) One source of truth; consistent behaviour across clients.
- (+) Shortcuts and future clients integrate via the same API.
- (−) Connectivity needed for core logic; offline behaviour must be designed.
- Stack is not decided here.
