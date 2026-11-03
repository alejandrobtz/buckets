# Capture Sources

> **Purpose:** Describe how transactions enter Buckets per platform, and what coverage to expect.
> **Status:** Draft · **Last updated:** 2026-11-03
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

## Immediate categorization of PSE and Bre-B payments

PSE and Bre-B payments are hard to understand after the fact: the bank notification gives an amount and a recipient, rarely a purpose. Buckets asks the user right after the confirmation arrives.

**Scope:** Buckets prompts when the bank's confirmation notification is captured. It does **not** intercept or observe the payment flow inside the bank app (no accessibility service or overlay: restricted by Google Play, exposes sensitive banking screens, impossible on iOS).

**Flow**
1. The bank notification is captured and processed ([ADR-003](../04-delivery/decisions/ADR-003-server-side-capture-parsing.md)).
2. Within seconds Buckets shows its own actionable notification: "You paid $X to Y. What was it?" with a few likely categories, "other", and an optional concept/comment.
3. The amount and recipient are recorded as facts; the category stays *pending* until answered. Unanswered items go to the review queue with a reminder; prompts are batched to avoid nagging.

**Suggestions** are deterministic (e.g. the category chosen last time for the same recipient, recurring payments after one confirmation). No AI is needed.

**Platforms**
- Android: full support, since capture reads the bank notification.
- iOS: the Wallet trigger does not cover PSE or Bre-B. Until a source exists, use manual entry via a Shortcut, widget or share sheet. This gap is communicated through [Data Confidence](../00-foundation/glossary.md#data-confidence).

**To verify in the spike:** what each bank's notification contains (name, Bre-B key or amount only) and end-to-end prompt latency; if slow, show a generic prompt first and complete it after parsing.

## Open items

- Banks/wallets to cover first (e.g. Bancolombia, Nequi, Daviplata).
- SMS and email: deferred to R1.x; R1 captures from notifications only ([releases](../04-delivery/releases.md)).
- Spike: log raw notification text for ~1 week to learn real formats ([releases](../04-delivery/releases.md)).
