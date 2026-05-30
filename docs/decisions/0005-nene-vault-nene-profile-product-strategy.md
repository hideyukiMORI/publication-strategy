# Decision 0005: NeNe Vault and NeNe Profile — Parallel Back-Office Products

Date: 2026-05-29

## Status

Accepted

## Context

The maintainer is completing **NeNe Clear** (reconciliation & dunning) and wants
two additional self-hosted products to:

1. **Displace storage-only SaaS fees** (MF BOX, freee document modules) — **NeNe Vault**
2. **Displace closed bank CSV presets** and reduce Clear scope creep — **NeNe Profile**

Both products inherit NENE2 governance, run beside Invoice/Clear on Tier A hosting,
and integrate via **HTTP only** — no shared databases.

Portfolio already defines:

| Product | Domain |
| --- | --- |
| NeNe Invoice | Issued billing documents |
| NeNe Clear | Reconciliation & dunning |

Adding Vault and Profile completes a **four-app back office** without recreating
Money Forward as a monolith.

## Decision

### NeNe Vault

| Field | Value |
| --- | --- |
| **Name** | NeNe Vault |
| **Domain** | Received-document archive (電子帳簿保存法-oriented storage & search) |
| **Repo** | [`hideyukiMORI/nene-vault`](https://github.com/hideyukiMORI/nene-vault) (public since 2026-05-30) |
| **Replaces (honest wedge)** | Storage + search subscription slice of mega-SaaS — **not** full accounting |
| **Required upstream** | None (optional links to Invoice/Clear) |

### NeNe Profile

| Field | Value |
| --- | --- |
| **Name** | NeNe Profile |
| **Domain** | Bank CSV column mapping & normalization |
| **Repo** | [`hideyukiMORI/nene-profile`](https://github.com/hideyukiMORI/nene-profile) (public since 2026-05-30) |
| **Replaces (honest wedge)** | Closed bank-format handling / manual Excel cleanup |
| **Primary downstream** | NeNe Clear (StandardTransaction ingest) |

### Boundaries (binding across repos)

```
[Vendor PDF]     → NeNe Vault     (store · search · retain)
[Bank CSV raw]   → NeNe Profile   (map · normalize)
[StandardTxn]    → NeNe Clear     (match · dunning)
[Issued invoice] → NeNe Invoice   (quote · bill · payment SSOT)
```

- Profile **must not** implement reconciliation (ADR in `nene-profile`).
- Vault **must not** implement bank CSV or expense approval (ADR in `nene-vault`).
- Clear **should consume** Profile output schema v1.0 when Profile MVP lands.

### Parallel bootstrap

Both repos Phase 0 documentation bootstrapped together (2026-05-29) with
**binding scope contracts** before runtime scaffold.

## Alternatives Considered

| Option | Rejected because |
| --- | --- |
| Vault + Profile as Clear modules | Scope creep; Clear becomes monolith |
| Profile only inside Clear | No standalone value; preset engine not reusable |
| Vault inside Invoice | Blurs issued vs received SSOT |
| Wait until Clear ships | Maintainer capacity + token budget favor parallel Phase 0 |

## Consequences

- `docs/products/nene-vault.md` and `docs/products/nene-profile.md` added.
- Four back-office repos; publication articles must name correct product per domain.
- Clear repo may later ADR to delegate CSV parsing to Profile.

## Related

- Decision 0004 (Invoice vs Clear)
- `nene-vault` scope contract
- `nene-profile` output schema v1.0
- Issue: TBD in publication-strategy
