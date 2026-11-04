# Agent SDK

**Status: planned. No public SPECIATE SDK package or version is announced in this document.**

The Agent SDK is intended to make it possible to design and test strategies without giving strategy code direct access to venue credentials.

## Intended developer workflow

1. Implement a strategy against a typed market snapshot / event interface.
2. Supply a validated configuration, supported markets, and version identifier.
3. Run deterministic replay tests against versioned input data.
4. Run paper execution with realistic cost models.
5. Submit the strategy to a controlled testnet environment when supported.
6. Inspect its full decision and execution record in SWARM.

## Contract principles

- Strategies receive **read-only** market/account context and a constrained output channel.
- All order requests pass through shared risk controls.
- No raw private keys or direct network access are needed by strategy implementations.
- Strategies must support cancellation and timeouts.
- Execution results must be observable and correlated to the originating decision.
- A strategy version and configuration hash must remain attached to the full run history.

## Illustrative interface sketch

The following TypeScript is **conceptual pseudocode**; it is not a published or executable SDK API:

```ts
type Action =
  | { kind: 'hold'; reason: string }
  | { kind: 'target-position'; market: string; targetNotionalUsd: number };

interface Strategy {
  id: string;
  version: string;
  onMarket(context: Readonly<MarketContext>): Promise<Action>;
}
```

The engine would validate and transform a `target-position` proposal into risk-checked orders. The action itself is not an exchange instruction.

## Testing expectations

Developers should be able to replay an event sequence, verify the same outputs for the same inputs, inject missing data or connection failures, and assert no order escapes safety checks.

## Participation

Repository, package registry, contribution license, installation commands, and API reference will be published once a functioning implementation exists. We do not want documentation that pretends a missing API already works.
