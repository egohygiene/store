# Domain Routing

## Current checkpoint, 2026-10-17

The user-facing goal is `egohygiene.io/` for the Ego Hygiene mission and future
product, with community commerce at `/store`. Existing documentation subdomains
can remain independently hosted. The root site is not intended to become an
artist-only shop.

The [issue #75 comparison](https://github.com/egohygiene/egohygiene.io/blob/docs/storefront-ownership-75/docs/architecture/storefront-ownership.md)
selects `egohygiene/egohygiene.io` as the canonical V1 storefront, built with the
rest of the website as one composed artifact. This is recorded in paired draft
PRs for review. The independent-deployment proposal below is historical context;
[ADR-005](../DECISIONS.md#adr-005-select-the-website-as-the-v1-storefront-owner)
describes its proposed supersession without erasing ADR-003.

The composed build does not require a separate store origin or `/store` proxy.
Verify root/store direct navigation, assets, client navigation, refreshes, and
provider handoffs on the eventual host. The prefix-stripping example below is
not a deployment rule for the selected direction. The old `egohygiene/website`
name in that example is not the current website repository.

Keep one coordinator for any shared deployment destination; separate workflows
must not replace each other's site output. See the
[current handoff](context/current-state.md) and
[merged launch plan](https://github.com/egohygiene/egohygiene.io/blob/ee59e2f83c59c084c23a5f8bcc3311c2dc830859/docs/architecture/store-launch-plan.md).

## Earlier independent-deployment proposal

The storefront deploys independently but is presented beneath the main domain:

```text
https://egohygiene.io/store/
```

## Store project

The Vite build uses `/store/` as its public base. The store deployment includes
SPA and asset rewrites so its preview URL can resolve the prefixed paths.

## Main website gateway

The main `egohygiene/website` deployment should proxy the path while stripping
the prefix before forwarding to the independent store deployment.

Conceptual rule:

```json
{
  "source": "/store/:path*",
  "destination": "https://egohygiene-store.vercel.app/:path*"
}
```

Add an additional exact `/store` rule when the gateway platform requires it.

## Local development

The local URL is:

```text
http://localhost:5173/store/
```

React Router derives its basename from Vite's configured base path.

