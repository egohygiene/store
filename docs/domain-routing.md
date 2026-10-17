# Domain Routing

## Current checkpoint, 2026-10-16

The user-facing goal is `egohygiene.io/` for the Ego Hygiene mission and future
product, with community commerce at `/store`. Existing documentation subdomains
can remain independently hosted. The root site is not intended to become an
artist-only shop.

The independent-deployment proposal below is retained as historical context.
This repository's [ADR-003](../DECISIONS.md#adr-003-deploy-independently-beneath-the-store-route)
conflicts with the website's
[high-level ADR-004](https://github.com/egohygiene/egohygiene.io/blob/db634b887ede348ce85d9c03af789467ab535dcf/DECISIONS.md#adr-004-consolidate-the-store-v1-website-and-use-hosted-checkout),
which places the store inside the website application. Both implementations
exist. Compare them and choose a canonical owner before implementing a gateway
or consolidating code. The old `egohygiene/website` name below is not the current
canonical website repository, `egohygiene/egohygiene.io`.

One composed deployment and independent deployments routed beneath `/store`
remain possible. For either choice, verify assets, direct navigation, router
base paths, and provider handoffs. The prefix-stripping example below is not a
verified rule for a future Netlify, Cloudflare, or Google deployment.

Keep one coordinator for any shared deployment destination; separate workflows
must not replace each other's site output. See the
[current handoff](context/current-state.md) and
[canonical launch-plan draft](https://github.com/egohygiene/egohygiene.io/blob/docs/store-launch-direction-20261016/docs/architecture/store-launch-plan.md).

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

