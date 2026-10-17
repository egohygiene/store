# Agent Instructions

## Mission

Preserve the provider-neutral commerce reference and its evidence while the
website owns the proposed V1 customer-facing storefront.

## Start or resume

Read [current state](docs/context/current-state.md), its latest dated checkpoint,
and the linked ownership comparison before changing architecture. Refresh both
repositories' heads, PRs, and checks. Website issue #75 selects
`egohygiene/egohygiene.io` and one composed V1 build for review; this repository
retains useful commerce code and research. The paired ownership PRs are drafts,
so do not mistake the selection for an accepted deployment or completed migration.
Consult [DECISIONS.md](DECISIONS.md) for durable decisions; dated conversation
notes preserve the reasoning, preferences, and open questions behind them.

At a checkpoint, update current state and add a dated note with source commits,
decisions, actual validation, unresolved questions, and the next action. Do not
replace historical notes with a transcript or treat them as new authorization.
The latest instruction authorized merging the planning PRs and undertaking the
first bounded ownership issue. The wider proposed issue hierarchy still awaits
review. Repository transfer, provider activation, purchases, and deployment are
not authorized by these records. Follow later explicit instructions when scope
changes.

## Dependency direction

```text
apps/storefront
  -> packages/store-ui
  -> packages/store-config
  -> packages/commerce
```

The application may depend on packages. Packages must never import application
modules.

## Commerce rules

- Keep Fourthwall details inside `packages/commerce/src/fourthwall`.
- UI components consume normalized commerce models only.
- Preserve mock mode so a clean clone can run without credentials.
- Never expose Fourthwall Platform API keys in browser code.
- The Storefront token is configured through Vite environment variables.
- Checkout remains hosted by Fourthwall.

## Engineering standards

- TypeScript strict mode.
- Descriptive names over abbreviations.
- No hidden global state beyond documented browser cart persistence.
- No direct user-facing output from package internals.
- Accessible semantics and keyboard support are required.
- Respect reduced-motion preferences.
- Add tests for provider normalization and business-state changes.
- Use conventional commits.
- Use long-form CLI flags in documentation and scripts.
- Shell functions must have shdoc-compatible docstrings.
- Prefer `printf` over `echo`.

