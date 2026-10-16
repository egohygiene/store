# Agent Instructions

## Mission

Maintain a small, explicit, provider-neutral commerce frontend for Ego Hygiene.

## Start or resume

Read [current state](docs/context/current-state.md), its dated discussion
checkpoint, and the linked canonical launch plan before changing architecture.
Refresh both repositories' heads, PRs, and checks: this store and the store
inside `egohygiene/egohygiene.io` overlap, and canonical ownership is unresolved.
Consult [DECISIONS.md](DECISIONS.md) for durable decisions; dated conversation
notes preserve the reasoning, preferences, and open questions behind them.

At a checkpoint, update current state and add a dated note with source commits,
decisions, actual validation, unresolved questions, and the next action. Do not
replace historical notes with a transcript or treat them as new authorization.
The current scope is documentation and review; issue creation, repository
transfer, provider activation, purchases, and deployment are not authorized by
these records. Follow subsequent explicit user instructions when scope changes.

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

