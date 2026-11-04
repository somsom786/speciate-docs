# Maintaining the documentation

This repository is designed for GitBook Git Sync.

## Structure

- `README.md`: landing page.
- `SUMMARY.md`: navigation and page order.
- `.gitbook.yaml`: GitBook configuration.
- `introduction/`, `ecosystem/`, `concepts/`, `developers/`, `resources/`: documentation sections.

## Editorial rules

1. Distinguish **planned**, **tested**, **testnet**, **live**, and **deprecated** features.
2. Never write a fabricated endpoint, contract address, chain ID, SDK install command, integration status, trading result, or partner claim.
3. Use a dated source for claims about supported networks or integrations.
4. Avoid forward-looking performance promises or implications of guaranteed returns.
5. Any documentation that describes real-money execution must be reviewed alongside the implementation and risk policy.
6. Keep navigation links valid when moving files; edit `SUMMARY.md` at the same time.
7. If a page's technical details are undecided, say that clearly rather than presenting conjecture as API reference.

## Suggested workflow

Open a feature branch, update Markdown, verify links, inspect rendered GitBook output, obtain review for technical/security claims, and merge to the synced branch.

## Future work

Once the actual codebase exists, align docs with tested interfaces and add API references, runnable SDK examples, changelogs, operational runbooks, and reproducible trading metrics.
