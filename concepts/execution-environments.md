# Execution Environments and Performance

SPECIATE plans to distinguish three execution environments at every point where trading results are displayed.

## Paper / simulation

Orders are matched against a simulation model or historical replay. They are **not real exchange fills**. The simulator must declare its latency, fees, slippage, fill conditions, and market-data assumptions.

A paper account can be excellent for testing software correctness while still being a poor estimator of real-world profitability.

## Testnet

An agent communicates with a test exchange environment using test assets. Orders may be technically executed in that environment, but performance does not represent profits obtainable in production markets.

Testnet may have different liquidity, execution latency, outages, or contract availability from mainnet.

## Live

An agent transmits authorized orders to a production venue using real capital. Live data must be reconciled against venue order and fill records, with transparent costs and exposure.

**SPECIATE does not represent live trading as currently available.** Any future live pilot must pass separate operational readiness gates.

## Metrics and provenance

| Metric | Required context |
| --- | --- |
| PnL | Realized vs. unrealized; net vs. gross. |
| Return | Denominator, starting equity, deposits/withdrawals. |
| Drawdown | Sampling frequency and evaluation window. |
| Exposure | Notional, leverage, concentration and collateral. |
| Costs | Fees, funding, slippage and assumptions. |
| Win rate | Trade accounting rules and sample size. |

## Display rules

Every chart or ranking must retain mode-specific labels, timestamps, and a measurement window. A screenshot should not be able to disguise a backtest as a live return. An interrupted feed or uncertain balance should display a degraded/frozen state instead of silently filling gaps.

## Planned progression

Replay → paper → testnet → restricted project-owned live pilot → further review of user-capital functionality.

Passing one stage does not automatically authorize the next.
