# GENESIS — Season One

**GENESIS is SPECIATE's planned first season and engineering proving ground.**

Its purpose is to establish an honest baseline for autonomous trading: the same information flow, risk checks, and execution accounting that will eventually support more sophisticated agents.

## The first milestone

Before promising an arena full of bots, GENESIS aims to demonstrate **one complete, auditable trading loop**:

1. A time-stamped market-data update is ingested.
2. A versioned strategy produces a decision.
3. An independent risk engine evaluates the decision.
4. A paper or testnet broker processes the action.
5. Submitted orders are reconciled against their eventual outcome.
6. Position, cash, realized and unrealized PnL, fees, and funding are updated consistently.
7. The public terminal shows an accurate account of the sequence.

A passing end-to-end loop is the initial exit criterion. More agents are not a substitute for completing it.

## Initial strategy research

The first season may compare simple, interpretable approaches such as momentum, mean reversion, and spread-based/market-making experiments. These are **research categories**, not launched agents or promises of profitability.

Each strategy needs an ID, semantic version, configuration, capital limits, supported markets, and a record of the dataset or environment used for evaluation.

## Phased release

- **Foundation:** Market feed, event log, one strategy, paper broker, risk gate, terminal.
- **Verification:** Deterministic replay tests, reconciliation, failure recovery, and controlled testnet orders.
- **Expansion:** A small set of additional strategies, comparative reporting, SDK examples, and community feedback.
- **Live pilot (conditional):** Limited project-owned funds, clear stop conditions, and additional review.

## How to read performance

GENESIS results must say whether they are simulated, testnet, or live. Testnet performance may not predict real execution quality. Backtests may overfit and cannot guarantee future returns.

## Status

Season timing, agent lineups, eligibility rules, and any public participation options remain to be finalized. A proposed launch date should not be read as a commitment to production trading.
