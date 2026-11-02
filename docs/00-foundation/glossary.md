# Glossary

> **Purpose:** Canonical definitions of domain terms. Other documents link here rather than redefine.
> **Status:** Draft · **Last updated:** 2026-11-02
> **Related:** [Bounded contexts](../01-domain/bounded-contexts.md) · [Principles](product-principles.md)

### Household
A group of people who share a financial view. Owns Accounts, Buckets and plans; the unit of sharing and permissions.

### Account
A real-world place that holds or owes money (bank account, cash, card, loan, e-wallet). Has a currency and a Balance. Sub-accounts or pockets (e.g. Nequi "bolsillos") belong to a parent and are **not** added to its balance again.

### Transaction
A recorded movement of money affecting one Account: income or expense. Amount is an integer in minor units with a currency. Keeps provenance and user corrections.

### Transfer
Movement between two of the user's own Accounts. It is neither income nor expense and is excluded from spending/earning totals.

### Balance
The amount in an Account (or aggregate) derived deterministically from its Transactions and Transfers. Never double counts sub-accounts.

### Financial Period
A time window (e.g. a month or a pay cycle) used for summaries, plans and reviews.

### Bucket
A logical allocation of money with a purpose (e.g. "Rent", "Trip"). **Not a bank account.** See [ADR-002](../04-delivery/decisions/ADR-002-optional-funding-container.md).

### Funding Container
The Account (or sub-account) that physically holds money backing a Bucket. Linking a Bucket to one is **optional**.

### Capture Event
A raw signal that may represent a Transaction (a notification, structured shortcut payload, imported row). Processed idempotently into a confirmed Transaction or a pending-review item. See [capture sources](../02-product/capture-sources.md) and [ADR-003](../04-delivery/decisions/ADR-003-server-side-capture-parsing.md).

### Data Confidence
An indicator of how complete and reliable the data for a period or Account is (e.g. partial source coverage, unreviewed items). Communicates uncertainty instead of hiding it.

### Financial Review
A periodic look-back comparing what happened with what was expected, producing learnings and adjustments. Part of "Review & learn" ([vision](product-vision.md)).
