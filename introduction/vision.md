# Vision and Principles

## Why SPECIATE exists

Trading systems are increasingly automated, but their actual behavior is often difficult to inspect. Performance charts can conceal assumptions about fees, execution, leverage, or whether a trade occurred at all.

SPECIATE explores a different kind of financial software: an environment in which trading agents can be created, run, compared, and improved, while their permissions, execution history, and risk constraints remain explicit.

The long-term thesis is that useful autonomous agents require three things at once:

- **AX — Agent Experience:** structured market inputs, robust execution interfaces, explicit feedback, and safe constraints.
- **DX — Developer Experience:** reproducible test environments, simple strategy contracts, strong debugging, and transparent versioning.
- **UX — User Experience:** immediate market context, understandable agent decisions, comparable performance, and clear distinctions between simulation and live trading.

Improving one dimension at the expense of the others is not enough.

## Five commitments

### 1. Verifiability over spectacle

A claimed trade is not a verified fill. SPECIATE intends to distinguish decision logs, simulated fills, testnet fills, and real-world executions. Performance representations must include their source, costs, and measurement window.

### 2. Autonomy with boundaries

A strategy's decision layer should never serve as the final authority on order size, leverage, exposure, or emergency shutdown. These controls belong to an independent risk and execution layer.

### 3. Reproducible experimentation

Strategies should be versioned. Backtests should preserve dataset versions, execution assumptions, fees, and random seeds where relevant. Evolution without out-of-sample evaluation is optimization theater.

### 4. Open interfaces

The intended SDK and interfaces should let external developers participate without first understanding the entire internal platform. Any repository, package, license, or contribution process will be announced when it is actually available.

### 5. Gradual capital responsibility

SPECIATE is intended to progress from replay and paper execution to testnet, then narrowly scoped project-owned live testing. User deposits, shared vaults, and permissionless capital allocation would require much stronger technical, legal, and security review.

## A longer horizon

Programmable liquidity, onchain registries, and decentralized coordination are areas of investigation, not prerequisites for demonstrating a capable autonomous trading system.

SPECIATE begins by proving a small system can be correct, observable, and safe enough to evaluate. The ecosystem expands only as the evidence supports it.
