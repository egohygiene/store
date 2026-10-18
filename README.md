# Ego Hygiene Store

A preserved React + Vite commerce reference for Ego Hygiene, with mock and
Fourthwall adapters, cart operations, and hosted-checkout handoff code.

[Website issue #75](https://github.com/egohygiene/egohygiene.io/issues/75) selects
the existing website app as the canonical V1 storefront, with one composed
build, in paired draft PRs for review. This repository remains available for
selective reuse and provider research; it is not archived or replaced by a third
implementation. See [ADR-0005](DECISIONS.md#adr-0005-select-the-website-as-the-v1-storefront-owner).

The repository boots in **mock commerce mode**, so it runs immediately without
credentials. Fourthwall mode additionally requires a Storefront token and
checkout-domain configuration; configured code is not evidence of a qualified
live purchase path.

Start architecture work with the [current handoff](docs/context/current-state.md).
It links the launch discussion and the cross-repository plan. A configured
adapter does not establish provider qualification or a production-ready shop.

## Architecture

```text
Browser
  -> storefront application
      -> commerce port
          -> mock adapter (default)
          -> Fourthwall Storefront API adapter
              -> Fourthwall hosted checkout
```

The UI never imports Fourthwall-specific response shapes. Provider data is
normalized behind `@egohygiene/commerce`, which keeps the application ready for
another provider or a server-side proxy later.

## Requirements

- Node.js 22 or newer
- Corepack
- pnpm 10

## Run locally

```bash
corepack enable
pnpm install
cp .env.example .env.local
pnpm dev:store
```

Open:

```text
http://localhost:5173/store/
```

## Connect Fourthwall

Edit `.env.local`:

```dotenv
VITE_COMMERCE_PROVIDER=fourthwall
VITE_FOURTHWALL_STOREFRONT_TOKEN=ptkn_replace_me
VITE_FOURTHWALL_CHECKOUT_DOMAIN=your-shop.fourthwall.com
```

Then restart the development server.

See [`docs/fourthwall-setup.md`](docs/fourthwall-setup.md).

## Commands

```bash
pnpm dev:store
pnpm build
pnpm preview:store
pnpm format
pnpm lint
pnpm typecheck
pnpm test
pnpm test:e2e
pnpm check
```

## Deployment model

This reference application still builds with `/store/` as its public base path.
Its existing Vercel configuration is retained historical implementation. The
selected V1 direction gives the website one composed build for `/`, `/store`,
and its other public routes. Do not connect this repository to a competing
deployment destination. Ownership remains under review in the paired draft PRs;
no hosting configuration changes are included.

The October 16 direction prefers Netlify development previews triggered by
merges into `development`, using a reusable GitHub Actions workflow. Production
hosting remains undecided between Cloudflare and Google. This documentation
does not configure or activate that pipeline.

See [`docs/domain-routing.md`](docs/domain-routing.md).

## Current scope

Included:

- mock product catalog
- Fourthwall product collection adapter
- product listing and product-detail routes
- provider-neutral cart operations
- hosted-checkout redirect
- persistent cart identifier
- responsive shell with reduced-motion styles; accessibility qualification remains
- dark cosmic visual foundation
- unit and end-to-end test scaffolding
- Vercel and GitHub Actions configuration

Deliberately deferred:

- customer accounts
- order-history UI
- webhooks
- analytics
- search
- product reviews
- inventory administration
- custom Fourthwall Platform API operations

## License

MIT

