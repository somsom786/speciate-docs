# Architecture

**Status: proposed reference architecture.** Interfaces, repository names, technologies, and component boundaries below are design choices; they are not a claim of a deployed production system.

## The end-to-end path

```text
Market feeds ──> Normalizer ──> Strategy runtime ──> Risk engine
                        │                  │            │
                        ▼                  ▼            ▼
                     Event log <────── Order manager ──> Broker adapter
                        ▲                                   │
                        └──────── Reconciliation <──────────┘
                        │
                        ▼
                   Public API / WS
                        │
                        ▼
                  SWARM terminal
```

## Suggested stack

- **Product UI:** Next.js + TypeScript, Tailwind CSS, accessible component primitives.
- **Visualization:** TradingView Lightweight Charts subject to the project's attribution and license requirements; chart feeds come from a separate normalized market-data service.
- **Engine and services:** TypeScript workers with explicit process boundaries for ingestion, strategy execution, orders, and reconciliation.
- **Storage:** PostgreSQL for durable identities, executions, accounting, and versioned experiments; an append-only event history for audit.
- **Exchange integration:** Official Hyperliquid APIs and/or audited, actively maintained wrappers. Verify endpoint details against current vendor documentation before deployment.
- **Onchain research:** Solidity/Foundry and viem for Elysium-related contract development, only after contracts, chain IDs, ABIs, and deployments are verified.

## Proposed service boundaries

### Data ingestion

Connect to supported market feeds, monitor connection health and sequence continuity, record source timestamps, and perform snapshot resynchronization after a gap.

### Strategy execution

Compute an action deterministically from inputs and configuration; prohibit direct access to signing keys or exchange write credentials.

### Risk and order management

Apply limits independently of strategy logic. Use idempotent client order IDs, avoid blind retries, model asynchronous acknowledgments and partial fills, and halt when state cannot be trusted.

### Reconciliation and accounting

Treat venue-confirmed orders, fills, positions, balances, fees, and funding as authoritative for a live or testnet account. Record both incoming external events and resulting local state transitions.

### Read models and API

Serve read-only public snapshots and streams derived from durable state. Expose mode, source, timestamps, and health. Never return secrets, session keys, or unrestricted order endpoints through the public API.

## Data model candidates

`agents`, `strategy_versions`, `agent_runs`, `market_events`, `agent_decisions`, `risk_decisions`, `orders`, `order_events`, `fills`, `positions`, `balances`, `accounting_entries`, `experiments`, `lineages`, and `system_incidents`.

These names are conceptual; final SQL migrations, event contracts, retention policy, and rate limits are part of the implementation process.

## Deployment gates

The minimum credible public release is a functioning, accurately labeled agent loop with reproducible tests. The next gate is reliable testnet state reconciliation. A real-capital pilot has a separate threshold that includes key isolation, limits, kill switches, observability, recovery tests, and review.
