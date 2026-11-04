# Security and Risk

Autonomous trading is an engineering and financial-risk problem. SPECIATE is being designed to treat risk boundaries as a core system feature, not an afterthought.

## Core safety model

### Separation of permissions

Strategy processes must not hold unrestricted signing keys, withdrawal credentials, or authority to change limits. Exchange credentials should be isolated per environment and role where supported.

### Independent execution gates

Risk checks should enforce position and notional limits, leverage bounds, loss and drawdown thresholds, supported-market allowlists, data freshness, and allowed order types before any order submission.

### Emergency stop

The operating system should support an explicit kill switch to stop **new** orders and have an independently tested plan for existing orders and positions. Stopping a process alone does not cancel exchange orders or close positions.

### Reconciliation before trust

A service restart, network partition, or WebSocket gap should trigger resynchronization. When the system cannot confidently determine live account state, it should not keep trading optimistically.

### Audit and observability

Record decision identifiers, order identifiers, external fill references, timestamps, risk denials, restarts, and incidents. Sensitive data must be excluded from public logs and responses.

## Security development practices

- Dedicated testnet credentials and isolated deployment secrets.
- Minimal access permissions and short-lived credentials where feasible.
- Automated unit, integration, end-to-end, fuzz, and failure-recovery tests appropriate to the subsystem.
- Contract-level reviews before significant onchain capital exposure.
- Dependency updates, CI checks, and incident response procedures.
- Independent review of financial calculations and execution-state transitions.

## Readiness boundaries

**Paper ready:** deterministic simulation and transparent assumptions.

**Testnet ready:** reliable signed execution, order lifecycle, and reconciliation.

**Restricted live ready:** additional key isolation, limits, operational observability, manual intervention, and rehearsed recovery.

**Public capital ready:** substantial additional security, legal, regulatory, custody, and smart-contract work—**not part of the initial launch**.

## Financial disclosure

Trading and liquidity provision carry substantial risk, including loss of principal. Simulated and testnet performance do not establish expected future results. SPECIATE does not promise returns or currently solicit public deposits.

The materials here describe intended engineering behavior; do not rely on them as a certification of an existing secure deployment.
