# Integrations

**Integration status is deliberately conservative.** A platform's public API or a planned partner feature does not mean SPECIATE has deployed or verified an integration.

## Hyperliquid

**Role:** Intended initial source for market data, exchange-account state, and testnet/mainnet order routing.

**Engineering objectives:** Reliable WebSocket ingestion, REST-backed snapshots, order signing under restricted permissions, broker adapters, reconciliation, and explicit testnet/live separation.

**Status:** Planned integration. Account models, endpoints, limits, signing behavior, and supported products must be verified against current official documentation and test environments.

Official technical reference: [Hyperliquid Docs](https://hyperliquid.gitbook.io/hyperliquid-docs/).

## Elysium

**Role:** Intended onchain-native environment for SPECIATE identity and later programmable financial features.

**Engineering objectives:** Verify chain metadata, bridge pathways, supported precompiles or contract interfaces, explorers, and deployed addresses before performing any transaction.

**Status:** Target network / integration research. SPECIATE makes no claim that its production registry or smart contracts are deployed on Elysium.

## Uniswap v4

**Role:** Future experiments in programmable liquidity, potentially including hooks or fees controlled by independently risk-bounded policies.

**Engineering objectives:** Confirm v4 deployment availability on target chains, hook compatibility, contract permissions, hook-address constraints, fee logic, and audit scope.

**Status:** Research and future roadmap. No SPECIATE v4 pool or hook deployment is claimed.

Official source: [Uniswap v4-core](https://github.com/Uniswap/v4-core).

## Charting

**Role:** Market context and agent-event overlays in the terminal.

**Proposed solution:** [TradingView Lightweight Charts](https://github.com/tradingview/lightweight-charts) with independent feed and provenance infrastructure.

**Status:** Proposed. Actual package choice, license/attribution implementation, and performance evaluation will be documented when shipped.

## Integration verification policy

Each released integration should publish or document the supported environment, version, tested methods, limitations, and any publicly verifiable deployment reference. Unverified addresses must never be copied into production configuration.
