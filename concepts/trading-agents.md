# Trading Agents

In SPECIATE, a **trading agent** is a versioned software strategy that consumes market information, proposes actions, and receives outcomes from an execution environment.

It is not necessarily an LLM. A deterministic algorithm may be a better first agent than a language-model-driven trader because it is easier to replay, debug, and test.

## Separation of responsibilities

| Layer | Responsibility |
| --- | --- |
| Market-data adapter | Timestamped order book, trades, candles, account updates. |
| Strategy runtime | Compute signals and propose actions using bounded inputs. |
| Risk engine | Enforce position, notional, leverage, loss, and data-quality limits. |
| Order manager | Assign stable client IDs, submit/cancel, track lifecycle. |
| Broker adapter | Paper, testnet, or live execution behind one interface. |
| Reconciler | Repair local state from the authoritative execution source. |
| Event log | Store decisions, rejections, orders, fills, and risk events. |
| Terminal | Explain observed state with its provenance. |

## Minimum agent identity

An agent should have a stable ID, owner or maintainer, strategy version, supported market list, configuration hash, execution mode, and clearly documented risk envelope.

## Strategy decision contract

An action proposal should describe a target, side, sizing intent, and optional execution preferences. It is **not an executable order** until the risk engine accepts it and the broker translates it for the configured venue.

## The role of language models

LLMs may assist with strategy ideas, documentation, research, and experiment orchestration. They are not part of the initial latency-critical execution path and cannot replace independent quantitative tests or security review.

## Known failure modes to design around

- Market-data stream gaps or stale snapshots.
- Duplicate orders after retries or process restarts.
- Partial fills and canceled or expired orders.
- Mismatched cash/position accounting.
- Fee, funding, or slippage assumptions diverging from reality.
- A strategy sending unexpected order sizes or loops.

An agent is only as useful as the safeguards that survive these events.
