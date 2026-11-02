# Buckets — Product, Domain, and Delivery Brief

**Document status:** Draft v0.1  
**Purpose:** Consolidate the product vision, problem definition, solution approach, domain discoveries, decisions, open questions, and initial implementation plan discussed so far.  
**Language:** English, consistent with the project's documentation convention.  
**Note:** This is a working baseline. It distinguishes accepted direction from proposals that still need validation.

## 1. Executive Summary

Buckets is envisioned as a financial operating system for individuals and households. It helps people move from simply recording transactions to understanding their financial behavior, making informed decisions, planning for what matters, and gradually building financial resilience and wealth.

The product must serve users at different levels of financial readiness. Some people only want to record income and expenses and see account balances. They should receive immediate value without being forced to create goals, budgets, Buckets, strategies, or commitments. As their data becomes more complete and they interact with the product, Buckets can offer increasingly useful reviews and guidance. Users may choose to act on those insights—or continue using Buckets only as a financial tracking tool.

The product is organized around user questions:

- **Know:** What is my financial reality?
- **Plan:** What do I want my money to accomplish?
- **Decide:** What action makes sense given my situation and priorities?
- **Review and learn:** What happened, what changed, and what can I improve?

Guidance must be grounded in trustworthy financial data, make its assumptions visible, and explain the impact of an action in terms the user cares about. AI may explain and communicate results, but deterministic domain logic and traceable calculations should underpin financial facts and recommendations.

## 2. Problem Definition

### The user problem

Many personal-finance tools help users record transactions, categorize spending, and view reports. These are useful capabilities, but they often leave the user to interpret the information and decide what to do next.

Users may struggle to answer:

- Where did my money go?
- How much money do I actually have available after accounting for bills, debt, and money already reserved for a purpose?
- Why do I repeatedly run short before the next payday?
- Which spending patterns are reducing my ability to save?
- What is the consequence of a spending change for a goal or family priority?
- Can I afford a purchase without putting other priorities at risk?
- What is the next practical step to improve my finances?

A further barrier is that many users are not ready to plan. They may be curious, want a simple transaction register, or need time to understand their behavior before defining goals. Requiring a full budgeting methodology at signup creates friction and can prevent these users from receiving value.

### Problem statement

> People need a reliable, low-friction way to understand their financial reality and the consequences of their everyday financial behavior, with optional guidance that helps them improve their finances and work toward the outcomes that matter to them.

### Product opportunity

Buckets can bridge the gap between **financial tracking** and **financial guidance**. It should make everyday financial information understandable and actionable without requiring every user to become a financial planner.

## 3. Product Vision and Positioning

### Working product vision

> **Buckets is a financial operating system that helps households understand, plan, and improve their financial future through trusted financial data, purposeful planning, and intelligent guidance.**

This is a working statement and should be reconciled with the previously accepted `PRODUCT_VISION.md` before replacing it.

### Product philosophy

1. **Money is a tool, not the goal.** It should help people build the life they want.
2. **Understanding comes before planning.** Users should be able to learn from their real behavior before being asked to create goals.
3. **Trusted data comes first.** Recommendations must be based on adequate, relevant, and sufficiently reliable information.
4. **Never make users calculate.** Explain balances, reserved amounts, available funds, and consequences clearly.
5. **Financial decisions matter more than reports.** Reports describe the past; decisions shape the future.
6. **Guidance adapts to the user.** Meet people where they are rather than forcing a single methodology.
7. **Recommendations explain impact.** Users should understand what could change if they follow a recommendation.
8. **Progress is measured over time.** Consistency and improvement matter more than perfection.
9. **Transparency earns trust.** Data sources, assumptions, calculation methods, and uncertainty should be visible.
10. **Technology should reduce friction.** Users want better financial outcomes, not more administration.
11. **Planning is optional.** A user can continue using transaction tracking and reviews without creating goals, Buckets, strategies, or commitments.
12. **The user retains agency.** Guidance supports decisions; it should not shame, coerce, or silently make consequential financial decisions.

### Candidate slogans

Two slogan directions were liked in the discussion:
- “From recording money to understanding money.”
- “Transform income into wealth.”

These are candidates, not final approved brand copy. The product helps users do the work; it should not imply that the software itself guarantees wealth creation.

## 4. Target Users and Entry Points

Buckets should support a continuum of needs rather than rigid user classes.

- **Transaction tracker:** wants to record income and expenses, categorize transactions, see balances, and review activity. Does not want goals or planning features. This is a valid long-term usage mode, not merely an incomplete onboarding state.
- **Financial explorer:** is curious about spending patterns and wants to understand where money goes, but may not know what goals to set.
- **Household planner:** wants to coordinate household finances, assign money to priorities, manage goals, and plan for life events.
- **Decision-focused user:** wants to evaluate purchases, debt repayment, savings choices, investments, or trade-offs based on current financial data and personal priorities.
- **Advanced user:** may want consolidated accounts, net worth, cash flow, forecasts, scenario comparisons, investment tracking, and richer analysis.

The interface and guidance should grow in depth as the user's needs and data permit. Do not require users to declare a fixed financial-maturity level as a prerequisite.

## 5. Proposed Solution: Capabilities by User Question

### Financial Operations — “Where does my money stand?”

Represents financial facts and activity:
- Financial institutions and providers.
- Accounts and account types.
- Transactions, income, expenses, transfers, and adjustments.
- Credit cards, loans, liabilities, and investments.
- Balances and balance history.
- Cash flow and net worth.
- Transaction import, categorization, reconciliation, and eventually financial data integrations.

Distinguish observed facts from estimates and user-entered data. A transaction register and reliable balance view are valuable on their own.

### Financial Planning — “What do I want my money to accomplish?”

- Buckets: logical reserves for a purpose.
- Goals and target amounts/dates.
- Priorities and life events.
- Funding plans and allocation strategies.
- Funding containers that physically or virtually hold money.
- Progress tracking and goal timelines.

Planning is optional. Users can operate without Buckets or goals.

### Financial Guidance — “What should I consider doing?”

- Spending and behavior analysis.
- Financial signals and patterns.
- Impact analysis.
- Recommendations.
- Financial strategies and commitments.
- Financial reviews.
- Scenario analysis and forecasts.
- An AI Advisor that explains grounded results in natural language.

“Financial Intelligence” was discussed as an internal capability name, but **Financial Guidance** better describes the user benefit. Final context boundaries and naming remain open.

### Household — “With whom do I manage money?”

Supports household membership, invitations, roles, permissions, and visibility. Household members may share goals without necessarily sharing every account or transaction.

### Integrations — “How does Buckets connect to external data?”

Encapsulates imports and external providers such as banks, open-finance services, files, and future third-party APIs. External systems should not dictate the core domain language.

### AI Advisor — “Can you explain this to me?”

Provides conversational explanations, summaries, education, and assistance. It should rely on structured facts and calculation results produced by the domain, not invent balances, calculations, or unsupported financial claims. Whether it is a separate bounded context or a capability within Financial Guidance remains to be decided.

## 6. Core User Journey

A flexible journey has emerged:

**Observe → Understand → Improve → Plan → Commit → Act → Review → Learn → Repeat**

Users may enter or remain at different points. This is not a mandatory funnel.

- **Observe:** record or import transactions and check balances.
- **Understand:** identify patterns and explain what the available data suggests, including limitations and confidence.
- **Improve:** offer practical opportunities to improve cash flow or reduce avoidable spending. Users may act without creating a formal goal.
- **Plan:** optionally create Buckets, goals, priorities, and funding plans.
- **Commit:** optionally adopt a strategy or measurable commitment, such as limiting restaurant spending or making an additional debt payment.
- **Act:** real transactions and behavior provide evidence of what happened.
- **Review:** summarize activity, progress, deviations, and possible next steps for the selected period.
- **Learn:** compare outcomes over time and adapt guidance based on explicit preferences and observed responses without overconfident assumptions about personality or intent.

## 7. Financial Discovery and Data Confidence

### Discovery without forced planning

A new user may begin by recording or importing transactions only. Buckets can invite them to use a review feature and explain that more complete data can produce more useful insights. The user must not be forced to create goals, Buckets, or commitments.

The first review should depend on evidence quality, not just elapsed time.

### Data Confidence

The product needs a way to communicate how complete and reliable its analysis is. Factors may include:
- Number and distribution of transactions.
- Coverage of the selected period.
- Whether income sources are known.
- Whether accounts and balances are up to date.
- Whether transactions have been categorized or verified.
- Whether recurring expenses and transfers are recognized.
- Whether the user has connected/imported relevant accounts.
- Whether data is user-entered, imported, or synced and when it was last updated.

Do not treat raw transaction count or app interaction frequency alone as proof of data quality. A large number of transactions from one card may still omit cash, another account, or income.

Distinguish:
- **Data coverage:** how much financial activity is represented.
- **Data quality:** how accurate and correctly classified the available records appear to be.
- **Analytical confidence:** how strongly the evidence supports a specific insight.

Exact scoring and thresholds remain open. Initial versions can use transparent rules and explanatory labels rather than an opaque universal score.

### Example Discovery Review

A review could state:
- Restaurant spending was 20% higher than in the previous comparable period.
- The comparison includes transactions recorded for the selected periods.
- If the increase continues, estimated savings capacity may be reduced by COP X.
- Under the user's current priorities and funding plan, a university goal may be delayed by approximately one month.
- Options include reviewing restaurant spending, adjusting another discretionary category, revising the goal timeline, or taking no action.

Calculations must be derived from user data and explicit assumptions. Label estimates, account for incomplete data, and avoid implying that correlation proves causation.

## 8. Financial Periods and Reviews

### User-defined financial cycle

Users should be able to define the period used for tracking and reviews. Potential options include calendar month, biweekly, weekly, quarterly, or a custom date range. The model must distinguish transaction date and period assignment, review period, recurring income/pay schedules, partial periods, and comparisons between equivalent periods.

A monthly or quarterly review should use transactions within the selected cycle, not blindly use calendar-month totals.

### Review types

- **Discovery Review:** early analysis when sufficient evidence becomes available.
- **Financial Cycle Review:** recurring review for the user's selected period.
- **Goal Review:** progress against specific goals, if configured.
- **Strategy Review:** results of an adopted strategy or commitment.
- **Annual Review / Financial Year in Review:** longer-term progress and milestones.

Automatic generation is a proposal. Users should be able to preview, inspect, correct, and understand the data behind a review.

### Review insights

Potential insights include spending by category and change versus a comparable period, income and expense trends, cash flow, unusual or recurring expenses, goal progress where configured, strategy/commitment progress where adopted, opportunities and trade-offs, missing data, and a small number of prioritized next steps.

## 9. Buckets, Accounts, and Funding Containers

### Bucket definition

A **Bucket** is a logical allocation of money to a purpose. It represents financial intent; it is not itself a bank account. Examples include an emergency fund, a child's university, a car repair reserve, or a family holiday.

### Funding Container

A **Funding Container** represents a place or instrument in which money is held or tracked. Examples may include a savings/checking account, bank sub-account or savings box, cash, an investment account, or a digital wallet. The abstraction should not assume that every provider's “pocket” or “box” is technically a separate bank account.

### Relationship decision

**Accepted direction:** linking a Bucket to a Funding Container is optional. A Bucket may be unfunded/planned, virtually allocated within a larger account, backed by one dedicated container, or backed by multiple containers.

The model must avoid double-counting money. If a savings box is a subdivision of a parent account, its balance must not be added to the parent balance as if both were independent assets.

### Balance and availability concepts

Buckets must support balances and consolidated account information. Candidate concepts to define precisely:
- Account balance.
- Available balance, when supported by the data source.
- Ledger/recorded balance.
- Reserved/allocated amount.
- Unallocated amount.
- Cash position.
- Net worth.
- Cash flow.

A possible calculation is **Unallocated funds = eligible available funds − allocations/reservations**, subject to defined treatment of pending transactions, credit limits, overdrafts, and account restrictions. Do not equate “unallocated” with a recommendation to spend. Do not present a figure as reliable when data is incomplete or stale.

## 10. Financial Guidance: From Insight to Action

### The “So what?” principle

A raw transaction or chart is often insufficient. Buckets should explain potential consequences.

Example:

> Restaurant spending increased by 20% compared with the previous period. Based on the transactions currently recorded, this represents approximately COP X in additional spending. If your current savings allocation remains unchanged, the university goal could be delayed by about one month. You could reduce restaurant spending, adjust another discretionary category, change the savings contribution, or keep the current plan and accept the delay.

This is illustrative; actual calculations must come from user data and stated assumptions.

### Financial Signals

Potential signals include spending trend, savings momentum, cash-flow stability, debt pressure, goal momentum, recurring-expense growth, and data gaps. Each signal must have a defined rule, period, evidence, and explanation. Avoid arbitrary scores that appear authoritative without a defensible methodology.

### Recommendation lifecycle

A potential lifecycle is:
1. **Observation/Insight:** describes a pattern.
2. **Recommendation:** proposes an action.
3. **Adopted Strategy:** the user accepts a broader approach.
4. **Financial Commitment:** a concrete, measurable action within a strategy.
5. **Habit (optional concept):** a recurring behavior the user wants to sustain.
6. **Review:** measures what happened and what impact can reasonably be attributed.

The distinctions between Strategy, Commitment, Habit, Goal, and automatic Rule need formal domain definitions before implementation.

### Measuring a commitment

For a commitment such as “keep restaurant spending at or below COP 600,000 per financial cycle,” track:
- **Outcome:** was the target met?
- **Trend:** is spending moving in the intended direction?
- **Impact:** what changed in cash flow or goal timelines?
- **Evidence/confidence:** are relevant transactions likely represented?
- **Context:** were there exceptional events or corrections the user wants considered?

Do not treat every missed target as personal failure. Reviews should explain results neutrally and let users revise or discontinue a strategy.

### Strategy example

**Accelerate Sofia's University Fund** could include reducing restaurant spending by a specified amount, contributing an additional amount each cycle, and allocating part of an annual bonus. The system measures individual actions and the overall strategy. Users can choose a simpler approach or no strategy.

## 11. AI Advisor: Role and Guardrails

AI is a communication and assistance layer, not the source of financial truth.

It may explain calculations, summarize reviews, help explore options, ask clarifying questions, explain financial concepts, and turn an approved recommendation into an understandable action plan.

It must not invent or silently modify transactions, balances, or goals; present estimates as facts; hide missing/stale data; claim causation without sufficient evidence; execute consequential transactions or change strategies without explicit authorization; or present uncertain personalized investment, tax, or credit conclusions as certain.

Recommended flow:

**Financial records → validated calculations and domain rules → evidence-backed insights/recommendations → AI explanation → user decision**

Retain enough structured evidence to explain why an insight was generated, including period, inputs, rule/model version, assumptions, and confidence.

## 12. Domain Landscape and Candidate Bounded Contexts

These are candidate boundaries for discovery, not a final technical architecture.

| Context / Capability | Main question | Candidate responsibilities |
|---|---|---|
| Financial Operations | Where does my money stand? | Accounts, transactions, balances, liabilities, cash flow |
| Financial Planning | What should my money accomplish? | Buckets, goals, priorities, funding plans, life events |
| Financial Guidance | What should I consider doing? | Insights, impact analysis, recommendations, strategies, reviews |
| Household | With whom do I manage money? | Members, roles, invitations, permissions, visibility |
| Integrations | How does external data enter or leave? | Imports, bank/open-finance adapters, provider mappings |
| AI Advisor | Can you explain this to me? | Conversation, explanations, summaries, guided exploration |

“Financial Behavior” emerged as a possible module for behavior analysis, but it may be a capability within Financial Guidance. Reviews and Scenarios may also be capabilities rather than independent contexts. Validate boundaries before splitting into services.

### Architecture direction

Prefer starting with a **modular monolith** with explicit domain boundaries and contracts. Do not begin with microservices merely because the conceptual model has multiple contexts. Use domain events where they add clear value, keeping deployment and operations simple until scale and team needs justify more complexity.

Candidate flow:

`Financial Operations → Financial Planning (where relevant) → Financial Guidance → AI explanation`

Events and derived views must not make the source of truth ambiguous. Define ownership, consistency expectations, idempotency, and recalculation behavior before implementing event-driven workflows.

## 13. Technical Direction and Delivery Principles

### Platform

The product should be accessible on mobile as well as web. Mobile is strategically important because capturing transactions should involve as little friction as possible.

Angular and .NET were discussed as likely technologies, with web and mobile experiences in mind. The final architecture decision is open. Evaluate whether the first mobile release should be responsive/PWA, cross-platform, or staged. Avoid maintaining separate implementations unnecessarily.

### Automation and transaction capture

Reducing transaction-entry friction is a major goal. Potential inputs include manual entry with fast defaults, CSV/statement imports, recurring transaction suggestions, rules-based categorization, bank/open-finance synchronization where legally and technically available, and review/correction flows for uncertain classifications.

Automated ingestion needs duplicate detection, transfer recognition, correction, provenance, and reconciliation. Never silently treat uncertain classifications as confirmed facts.

### Data and calculation principles

- Keep original transaction data and provenance.
- Model money with currency and decimal-safe precision; never use floating-point arithmetic for financial amounts.
- Distinguish transfers from income and expenses to prevent double-counting.
- Support pending, posted, corrected, and excluded transactions where needed.
- Define treatment of refunds, chargebacks, credit-card purchases/payments, debt balances, foreign currency, and parent/sub-account relationships.
- Preserve historical period results or calculation versions where needed for explainable reviews.
- Treat user corrections as first-class inputs.

### Security and privacy

Financial data is highly sensitive. Establish data minimization, encryption, access control, auditability, consent, deletion/export, secure secrets handling, and clear household visibility rules before integrating real financial accounts. Do not use private financial data for unrelated purposes without clear consent.

## 14. Initial Product Scope and Release Strategy

These releases are proposals, not a committed schedule. Validate the smallest coherent product with users before locking scope.

### Release 0 — Foundations and validation
- Confirm vision, terminology, user journeys, and product principles.
- Document domain rules and open decisions.
- Validate the problem with potential users.
- Define privacy, security, and data-handling requirements.
- Create a prioritized, testable initial backlog.

### Release 1 — Reliable Financial Operations
- User/account setup and account types.
- Manual income, expense, and transfer entry.
- Categories and transaction editing.
- Account balance calculations and transaction history.
- Basic cash-flow and category summaries.
- CSV import if it can be implemented reliably.
- Clear data-source and completeness indicators.

This release should already be useful to a user who only wants a register and balance view.

### Release 2 — Reviews and Financial Discovery
- User-selected financial periods.
- Comparisons across comparable periods.
- First Discovery Review when evidence is sufficient.
- Data coverage and confidence indicators.
- Basic spending patterns and recurring-expense insights.
- Transparent calculations and correction workflows.

### Release 3 — Financial Planning
- Buckets and optional Funding Container links.
- Goals, priorities, target dates, and progress.
- Allocations that reconcile with accounts and avoid double-counting.
- Goal impact and funding status.

### Release 4 — Financial Guidance
- Evidence-backed recommendations.
- Impact analysis and simple scenarios.
- Strategies and commitments.
- Review of outcomes over time.
- Controls to accept, dismiss, modify, or pause guidance.

### Release 5 — AI Advisor and deeper automation
- Natural-language explanations grounded in structured calculations.
- Conversational exploration of reviews and scenarios.
- Better transaction import and categorization automation.
- Integrations selected according to market, availability, cost, consent, and compliance.

### Later capabilities
- Net-worth history and richer forecasting.
- Advanced debt and investment scenarios.
- Open-finance synchronization.
- Annual financial story/review and milestones.
- More household collaboration and permissions.

## 15. Suggested Documentation Repository

The project previously established the intention to keep documentation in English and maintain it in GitHub repository `alejandrobtz/buckets-product-docs`, with manual uploads acceptable if connector access is unavailable.

```text
/
├── README.md
├── docs/
│   ├── 00-foundation/
│   │   ├── why.md
│   │   ├── product-vision.md
│   │   ├── product-philosophy.md
│   │   ├── product-principles.md
│   │   └── glossary.md
│   ├── 01-domain/
│   │   ├── domain-landscape.md
│   │   ├── bounded-contexts.md
│   │   ├── ubiquitous-language.md
│   │   ├── financial-knowledge-model.md
│   │   ├── aggregates.md
│   │   ├── value-objects.md
│   │   ├── domain-events.md
│   │   └── commands.md
│   ├── 02-product/
│   │   ├── personas.md
│   │   ├── user-journeys.md
│   │   ├── discovery-journey.md
│   │   ├── financial-review.md
│   │   ├── financial-guidance.md
│   │   ├── ai-advisor.md
│   │   ├── capabilities-roadmap.md
│   │   └── metrics.md
│   ├── 03-architecture/
│   │   ├── architecture-principles.md
│   │   ├── modular-monolith.md
│   │   ├── data-modeling.md
│   │   ├── api-guidelines.md
│   │   ├── frontend-architecture.md
│   │   └── security-and-privacy.md
│   └── 04-delivery/
│       ├── releases.md
│       ├── initial-backlog.md
│       └── decisions/
│           ├── ADR-001-modular-monolith.md
│           └── ADR-002-optional-funding-container.md
└── product-brief.md
```

Do not create every file merely to fill the tree. Start with core documents and add details as decisions are made. Avoid duplicating rules across files; link to each rule's canonical home.

### Document governance

Every substantive document should include purpose, status (`Draft`, `In Review`, `Accepted`, or `Superseded`), last updated date, and relevant decisions/cross-references. Use Architecture Decision Records (ADRs) for consequential technical decisions. Preserve superseded decisions and explain why they changed rather than silently erasing project history.

## 16. Decisions and Working Agreements

### Accepted direction from discussion

1. Documentation is written in English.
2. The project needs a maintained documentation repository.
3. Buckets must be more than a transaction log: it should support understanding, planning, and guidance.
4. Users must be able to use the product only to record transactions and review balances.
5. Goals, Buckets, Strategies, and Commitments are optional.
6. Discovery should depend on evidence quality, not a fixed number of days alone.
7. Financial periods should be configurable by the user.
8. Reviews should connect observed patterns to potential consequences and options.
9. A Bucket represents purpose; it is not a bank account.
10. Linking a Bucket to a Funding Container is optional.
11. Balances and consolidated account information remain essential.
12. Avoid double-counting balances when accounts contain sub-accounts or savings boxes.
13. Financial guidance must be explainable and grounded in reliable data.
14. AI should explain evidence-backed results rather than be the authority for financial calculations.
15. Mobile access and low-friction transaction capture are important product goals.
16. Begin with clear modular boundaries; a modular monolith is the current architectural proposal, not a final commitment to microservices.

### Proposals that need validation

- Final product vision and slogan.
- Exact bounded contexts and whether Financial Behavior, Reviews, Scenarios, or AI Advisor are separate contexts.
- Exact first-release scope.
- Financial-cycle options and comparison rules.
- Data Confidence metrics and thresholds.
- Definitions of Goal, Bucket, Funding Plan, Strategy, Commitment, Habit, and Rule.
- Calculation rules for available/unallocated funds, net worth, and cash position.
- Mobile implementation strategy.
- Bank/open-finance providers and integration timing.
- Recommendation prioritization and personalization rules.
- Metrics that demonstrate user value without encouraging harmful or shame-based behavior.

## 17. Open Questions to Resolve

### Product and user experience
1. Who is the first target market: individuals, households, or both?
2. Which country/currency and financial conventions should the first release prioritize?
3. What is the smallest useful release for a transaction-only user?
4. Should household sharing be in the first release or a later one?
5. What does “close a financial cycle” mean: automatic review, user-confirmed review, or both?
6. How should users correct unusual events or explain a one-off expense?
7. How should the product handle recommendations a user repeatedly dismisses?

### Domain and calculations
8. What exactly constitutes an account, a sub-account, and a Funding Container?
9. How are transfers, credit-card purchases, card payments, refunds, and debt principal/interest represented?
10. How are pending transactions and stale balances handled?
11. How is money allocated across multiple Buckets without double-counting?
12. What evidence is required before a review may compare spending or estimate goal delays?
13. How should shared versus individually owned assets and liabilities be represented?

### Architecture and delivery
14. Which mobile approach best balances reach, cost, offline behavior, and maintenance?
15. Which integrations are feasible and compliant for the first target market?
16. Which data needs immediate consistency and which can be derived asynchronously?
17. What are the initial privacy, retention, export, and deletion requirements?
18. What is the first testable end-to-end user journey?

## 18. How to Build the Solution

### Step 1 — Consolidate the foundation

Review existing `WHY`, `PRODUCT_VISION`, `PRODUCT_PRINCIPLES`, `DOMAIN_PRINCIPLES`, and `UBIQUITOUS_LANGUAGE` documents. Update them deliberately so this brief does not conflict with earlier accepted artifacts. Keep the original history in Git.

### Step 2 — Validate the problem and initial audience

Interview people who currently track spending in spreadsheets, banking apps, or not at all. Test whether transaction tracking, trustworthy balances, and a useful review solve a recurring problem. Avoid validating only with people who already enjoy budgeting.

### Step 3 — Define the canonical language

Create a first accepted glossary for concepts affecting the data model and user experience: `Household`, `Account`, `Transaction`, `Transfer`, `Balance`, `Financial Period`, `Bucket`, `Goal`, `Funding Container`, `Financial Review`, `Insight`, `Recommendation`, `Strategy`, and `Commitment`.

### Step 4 — Specify a vertical slice

Choose one end-to-end scenario:
1. User creates an account.
2. User records income and expenses.
3. User corrects and categorizes a transaction.
4. Account balance and cash-flow summary update correctly.
5. User chooses a review period.
6. Product shows a transparent summary and identifies missing data.
7. User can inspect the transactions behind each total.

This validates the foundation before adding AI or complex planning.

### Step 5 — Design the financial model and calculation rules

Write explicit rules and tests for monetary precision/currency, transaction lifecycle/provenance, transfers and duplicate detection, account/sub-account aggregation, period assignment, categorization/corrections, reconciliation, reserved/unallocated funds, and missing/stale/incomplete data.

### Step 6 — Implement the first release

Use a modular architecture with explicit ownership and testable domain rules. Keep financial calculations deterministic and covered by unit/integration tests. Build accessible mobile-friendly flows for quick transaction entry and review.

### Step 7 — Add discovery reviews

Start with transparent, explainable rules. Show the period, transaction coverage, comparison baseline, and limitations. Allow users to inspect evidence and correct data. Do not introduce opaque AI-generated financial judgments before the data pipeline is reliable.

### Step 8 — Add optional planning

Introduce Buckets and Goals as a natural next step for interested users. Ensure the product remains useful to users who decline planning.

### Step 9 — Add strategies and impact analysis

Allow users to adopt a recommendation, define measurable actions, and review outcomes over time. Separate actual outcomes from estimated or modeled impacts.

### Step 10 — Add AI responsibly

Use AI to explain structured facts, help users explore alternatives, and communicate uncertainty. Retain evidence and assumptions behind recommendations so they can be audited and reproduced.

### Step 11 — Measure product value

Potential measures:
- Time and effort required to record or import transactions.
- Transaction completeness and correction rate.
- Percentage of users who can reconcile displayed balances.
- Review usefulness rating.
- Percentage of insights with inspectable evidence.
- Adoption and retention across tracker-only and planning users.
- User-reported clarity about spending and next steps.
- Strategy outcomes, while avoiding simplistic causal claims.

### Step 12 — Iterate based on evidence

Prioritize reliability and user trust over feature volume. Add automation and integrations where they materially reduce friction and are feasible within privacy, compliance, and cost constraints.

## 19. Recommended Immediate Next Steps

1. Treat this brief as a **Draft v0.1** baseline.
2. Compare it with existing project documents and resolve conflicts.
3. Finalize Foundation documents: `why.md`, `product-vision.md`, `product-philosophy.md`, and `product-principles.md`.
4. Define the initial Ubiquitous Language.
5. Create a Domain Landscape diagram and mark boundaries as provisional.
6. Define and test the transaction/account/balance model before designing recommendation algorithms.
7. Specify the first vertical slice and turn it into a small backlog.
8. Validate the vertical slice with prospective users.
9. Record important decisions as ADRs.
10. Keep all claims about balances, reviews, and recommendations explainable and auditable.

## 20. Closing Summary

Buckets should let people start simply and grow naturally:

- **First, record and know:** transactions, accounts, balances, and cash flow.
- **Then, understand:** reviews, trends, data coverage, and spending patterns.
- **If they choose, plan:** Buckets, goals, priorities, and funding containers.
- **When useful, decide:** evidence-backed recommendations, scenarios, strategies, and commitments.
- **Over time, learn:** compare outcomes and help users understand how repeated choices affect their financial future.

The product's central promise is not that it will automatically make users wealthy. It is that it will help them understand their financial reality, see the consequences of their choices, and make more informed decisions with less friction.

**Working product principle:**

> Every recommendation should be traceable to trustworthy financial data, explain its assumptions, and help the user understand the choices available—without taking away the user's agency.
