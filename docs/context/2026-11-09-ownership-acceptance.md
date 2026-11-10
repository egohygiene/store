# Storefront ownership acceptance reconciliation — 2026-11-09

Alan authorized a bounded website closeout batch while asleep, with a next-day
sync. Website #75's acceptance audit found that the paired ownership PRs were
merged while this repository still described the choice as proposed. This change
records the existing accepted decision; it makes no new topology decision.

| Source | Live evidence |
| --- | --- |
| Website ownership PR #76 | Merged; head `98cc8d8eee1e3446a0fe10bbffb1b7aaf6f7526c`, merge `08174a9ce39dfd3f2be806181b20153e94642e6a` |
| Store ownership PR #34 | Merged; head `3c2a46ad74057b4ed4c7e9298bfc08193eff804f`, merge `13279f96491d3dad49d9d6ebf558404eccc8103f` |
| Store main inspected | `5786fd40bfe40b0d338eb96087355b98f7e16d42` |
| Accepted website decision | [ADR 0007](https://github.com/egohygiene/egohygiene.io/blob/08174a9ce39dfd3f2be806181b20153e94642e6a/docs/architecture/decisions/0007-canonical-storefront-owner.md) |
| Original comparison and source dispositions | [Immutable website comparison](https://github.com/egohygiene/egohygiene.io/blob/08174a9ce39dfd3f2be806181b20153e94642e6a/docs/architecture/storefront-ownership.md) |

The website is the canonical customer-facing V1 storefront in one composed site
build. This repository retains commerce reference code, provider research, tests,
source history and its original MIT notice. Individual future adaptations need
immutable provenance and qualification. Existing code is not copied or activated.

Updated ADR-0005's status and immutable counterpart links, marked ADR-0003's
independent V1 deployment superseded, and reconciled AGENTS/current-state. Original
October receipts and decision bodies remain historical evidence. The later website
#100 retirement request is separate and incomplete; no source repository is deleted
or archived. Software licensing decisions remain website #59.

Validation is documentation link/diff inspection and live merged-PR/commit ancestry
evidence. No application or browser suite is needed for these status-only changes;
no new runtime/provider/deployment/transaction success is claimed. Review/integrate
this focused draft before treating reciprocal current pointers as fully delivered
on both main branches. Website #75 remains open for that disposition.
