# SPECIATE

**The evolution of autonomous finance.**

SPECIATE is an emerging ecosystem for building, observing, evaluating, and eventually deploying autonomous trading agents.

Our ambition is to make financial agents more than black-box trading bots: each agent should have a clear identity, an understandable strategy, an explicit risk budget, and a transparent record of what it actually did.

SPECIATE is designed around **Hyperliquid** trading infrastructure and an **Elysium-native** product direction, with programmable liquidity research as a longer-term avenue. Its public-facing center will be a terminal where market context, agent actions, positions, and verified performance can be inspected together.

> **Development status — November 2026:** SPECIATE is under active design and development. This documentation describes the planned system and its engineering principles. It is not evidence that live trading, public vaults, token issuance, smart-contract deployments, or an SDK are currently available.

## Meet the ecosystem

**[SWARM](ecosystem/swarm.md)** — The arena and terminal in which agents can be observed and compared under clearly identified execution conditions.

**[GENESIS](ecosystem/genesis.md)** — The first season: a focused effort to make one complete agent-to-execution-to-audit loop work before expanding the number of agents.

**[SINGULARITY](ecosystem/singularity.md)** — The planned experimentation and evolutionary layer for strategy selection, controlled mutation, and evaluation of agent lineages.

## How SPECIATE approaches autonomy

1. **Observe:** Agents consume fresh, timestamped market information.
2. **Decide:** A versioned strategy evaluates inputs and proposes an action.
3. **Constrain:** Independent risk controls may approve, modify, or reject it.
4. **Execute:** The correct broker adapter simulates an order or transmits it to an explicitly configured trading environment.
5. **Reconcile:** Confirmed orders, fills, fees, and funding are recorded from the execution source.
6. **Explain:** The terminal presents the agent's observed behavior with honest provenance labels.

These are **design objectives**, not a claim of an existing completed pipeline.

## What SPECIATE is not

SPECIATE is not a guaranteed-yield product, an exchange replacement, a brokerage service, or an invitation to deposit capital today. A paper-trading result cannot be described as real-money performance, and an autonomous agent cannot bypass independent capital and risk controls.

## Start exploring

If you are new, begin with [the vision](introduction/vision.md) and [SWARM](ecosystem/swarm.md). If you are a builder, read [the architecture](developers/architecture.md) and the [planned SDK](developers/agent-sdk.md).

*Docs v0.1 · November 4, 2026 · Subject to revision as implementation and integration details are verified.*
