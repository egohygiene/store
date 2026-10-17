# Store Architecture

Read the [current handoff](context/current-state.md) and
[ADR-005](../DECISIONS.md#adr-005-select-the-website-as-the-v1-storefront-owner)
before architecture changes. The issue #75 comparison selects the website as
the canonical V1 app and one composed build in paired drafts for review. The
boundaries below describe this preserved reference implementation, not an
accepted second production deployment.

## System boundary

This repository implements a standalone reference shopping experience. Under
the selected direction, the website owns the V1 customer-facing site. Selected
commerce capabilities may be adapted into that app after qualification; provider
operations stay behind contracts, with provider-hosted checkout.

```text
apps/storefront
  presentation, routing, interaction, browser persistence

packages/store-ui
  reusable visual primitives

packages/store-config
  typed environment parsing and validation

packages/commerce
  provider-neutral models and commerce port
  mock adapter
  Fourthwall Storefront API adapter

Fourthwall
  product system of record
  carts
  hosted checkout
  payment processing
  manufacturing
  fulfillment
  shipping
  customer-order support
```

## Provider boundary

The application imports only normalized models and `CommerceClient`.
Fourthwall payload parsing and endpoint knowledge stay inside the adapter.

## Runtime modes

### Mock

The default. Uses a local catalog and in-memory cart. This mode powers local
onboarding, automated tests, and visual development.

### Fourthwall

Fetches the public product catalog through the Storefront API and redirects a
provider cart to hosted checkout when configured. This is implemented behavior,
not evidence of a verified live provider session or completed order.

## Preservation and qualification

Preserve `packages/commerce`'s normalized client and adapters, configuration
parsing, mock fixtures, and useful cart/UI behavior as source candidates. Keep
the original revision and MIT notice with any substantial copied code. The
website's public catalog, identifiers, purchase-state gates, and design/song
relationships remain authoritative for the selected app; provider responses
must not replace that catalog wholesale.

At the inspected revision, tests cover mock cart basics, configuration, money
formatting, and one add-to-cart browser path. No Fourthwall adapter-specific
tests or checkout-handoff assertion were found. Cart IDs use one unscoped browser
storage key; mock contents are in memory. Mutation error feedback, concurrent
changes, invalid prices/stock payloads, and modal focus behavior need
qualification before reuse. These observations do not claim fresh test runs.

## Future proxy

A server-side proxy can be introduced later without changing page components:
implement another `CommerceClient` adapter that calls `/api/storefront/*`.

