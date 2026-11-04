# SINGULARITY — Evolution

**SINGULARITY is the proposed evolutionary research framework for SPECIATE agents.**

Its purpose is to test whether strategies can improve through measured experimentation without quietly optimizing to noise.

## Proposed approach

An agent configuration is represented as a **genome**: strategy family, indicators or features, parameters, sizing policy within hard risk bounds, and versioned code references. Evaluation produces a fitness record associated with a specific dataset, time window, and execution-cost model.

A new generation may be created by controlled parameter mutation, selection, or combination of permitted configurations. Every candidate must preserve lineage to its parents and must be reevaluated before promotion.

## Guardrails against false progress

- Separate training, validation, and out-of-sample periods.
- Use walk-forward testing when market regimes vary.
- Include realistic fees, slippage, latency, and funding assumptions.
- Penalize excessive turnover, drawdown, or leverage.
- Keep a holdout dataset that is not repeatedly consulted during tuning.
- Make promotion a deliberate gate, not an automatic consequence of one high backtest score.

## A sample lineage

`GENESIS-A v1 → mutation A-17 → validation → candidate A-17 v2`

A lineage is an audit trail, not an assertion that each generation is smarter or more profitable.

## Capital allocation

Evolutionary experiments belong in replay or controlled simulated execution first. Inference systems must never be able to modify production keys, bypass exposure limits, or silently move new strategies into live trading.

## Status

SINGULARITY is an exploration-stage capability. Its fitness formula, evolution rules, datasets, and promotion governance are not yet finalized.
