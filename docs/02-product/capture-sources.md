# Capture Sources

> **Purpose:** Describe how transactions enter Buckets per platform, and what coverage to expect.
> **Status:** Draft · **Last updated:** 2026-11-02
> **Related:** [ADR-003](../04-delivery/decisions/ADR-003-server-side-capture-parsing.md) · [Glossary: Capture Event](../00-foundation/glossary.md#capture-event) · [Releases](../04-delivery/releases.md)

The first version must capture transactions automatically from wallet and banking-app signals. Processing rules (server-side parsing, idempotency, dedup, raw-text retention) live in [ADR-003](../04-delivery/decisions/ADR-003-server-side-capture-parsing.md).

## Sources

### Android — notification listener
- Uses `NotificationListenerService` (native Kotlin module).
- Sensitive permission: requires Google Play review and a clear user explanation.
- Client filters on device and only sends notifications from an **allowlist** of apps (wallets, banks).
- Risk: OEMs that kill background processes; must be tested on real devices.

### iOS — Shortcuts automation
- iOS gives no API to read other apps' notifications.
- Route: Shortcuts automation with the Wallet **"Transaction"** trigger calling the API.
- FinanceKit has very limited regional availability; verify for Colombia and do **not** rely on it.

### File import
- Bank statements / exports (CSV etc.) as a fallback on every platform. Formats to be defined per bank.

### Manual entry
- Always available; the baseline for tracker-only use.

## Coverage

Wallet signals cover only tap / Apple Pay / Google Pay payments. Income, transfers and PSE need bank-app notifications, SMS or email. Partial coverage is communicated through [Data Confidence](../00-foundation/glossary.md#data-confidence).

## Open items

- Banks/wallets to cover first (e.g. Bancolombia, Nequi, Daviplata).
- SMS and email as additional sources.
- Spike: log raw notification text for ~1 week to learn real formats ([releases](../04-delivery/releases.md)).
