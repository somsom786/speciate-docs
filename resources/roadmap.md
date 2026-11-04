# Roadmap

SPECIATE will advance by **verified capabilities**, not by fictional release milestones. Dates are indicative and may change as dependencies and testing results become clearer.

## Phase 0 — Foundation

**Goal:** Establish a stable repository, deployment pipeline, architectural contracts, and honest documentation.

- Project structure, CI, development/staging environments.
- Market-data adapter and normalized event formats.
- Initial design system and terminal skeleton.
- Test fixtures and basic monitoring.

**Exit condition:** A reproducible development environment and a readable terminal using labeled data.

## Phase 1 — GENESIS MVP

**Goal:** Make one complete trading-agent loop work end-to-end.

- One reproducible strategy and its configuration/version identity.
- Independent risk checks.
- Paper execution with accounting and event histories.
- Order lifecycle and reconciliation logic.
- Agent profile, live/recorded market context, and performance UI.

**Exit condition:** Repeatable tests demonstrate correct state transitions, and the UI displays data with accurate execution labels.

## Phase 2 — Testnet verification

**Goal:** Exercise the exchange execution path and recovery behavior.

- Controlled Hyperliquid testnet orders where supported.
- Real order/fill reconciliation, fee/funding accounting and persistent job recovery.
- Stale-data handling, idempotent retries, emergency stop.
- Monitoring, alerts, and failure-injection exercises.

**Exit condition:** Order and account records reconcile across restarts and known failure scenarios.

## Phase 3 — SWARM beta

**Goal:** Make the system useful to observers and developers.

- Several distinct strategies evaluated on the same accounting basis.
- Agent comparison views and audit history.
- Read-only public API and SDK examples after validation.
- Performance, accessibility, and operational hardening.

**Exit condition:** Beta users can inspect an agent and understand what happened without trusting a marketing claim.

## Phase 4 — Restricted live experiments

**Goal:** Evaluate a narrowly scoped strategy with project-owned capital, only after passing independent risk and security gates.

No user deposits, no public yield promise, and no unreviewed public vaults are included in this milestone.

## Phase 5 — Evolution and onchain expansion

**Goal:** Research SINGULARITY, developer participation, onchain registries, and programmable-liquidity mechanisms.

These features are conditional on actual chain support, verified deployments, security reviews, and regulatory considerations.

## Near-term emphasis

**November 2026:** Foundation, one auditable GENESIS loop, and testnet validation where available. A network mainnet launch target does not automatically mean SPECIATE will offer production trading that day.

This page is intentionally a commitment to sequencing and criteria—not to fabricated launch achievements.
