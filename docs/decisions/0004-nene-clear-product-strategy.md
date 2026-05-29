# Decision 0004: NeNe Clear vs NeNe Invoice — Domain Split

Date: 2026-05-29 (amended 2026-05-29)

## Status

Accepted (amended)

## Context

The maintainer identified two **separate back-office domains** for Japan SMB
self-hosted ops:

| Domain (JA) | Domain (EN) | Product |
| --- | --- | --- |
| 見積・請求・入金管理 | Quote, invoice, payment management | **NeNe Invoice** → `nene-invoice` |
| 入金消込・督促管理 | Payment reconciliation & dunning | **NeNe Clear** → `nene-clear` |

These are **not** one product with phases. They are **not** upper/lower layers,
**not** a migration path, and **not** upper compatible. Operators who need both
run **two sibling applications** connected via HTTP.

Early documentation incorrectly described Clear as "quote-to-cash billing" with
reconciliation as "Expansion #1." That conflation is **rejected**.

## Decision

### Product identity — NeNe Clear

| Field | Value |
| --- | --- |
| **Public product name** | **NeNe Clear** |
| **Tagline (EN)** | Clear deposits. Collect with confidence. |
| **Tagline (JA, marketing)** | 入金を消込し、未収を見える化する。 |
| **Domain** | Payment reconciliation & dunning **only** |
| **Canonical repo** | `hideyukiMORI/nene-clear` (private until launch) |
| **Framework** | NENE2 (PHP 8.4) |
| **License (when public)** | MIT |

### Product identity — NeNe Invoice

| Field | Value |
| --- | --- |
| **Domain** | Quote, invoice, payment management |
| **Canonical repo** | `hideyukiMORI/nene-invoice` (public) |
| **Relationship to Clear** | **Upstream sibling** — not deprecated, not to be archived for Clear |

### Repository roles

| Repository | Visibility | Role |
| --- | --- | --- |
| **`nene-invoice`** | Public | **Quote · invoice · payment** — billing document SSOT |
| **`nene-clear`** | Private (until launch) | **Reconciliation · dunning** — bank match & overdue reminders |
| **`publication-strategy`** | Public | Portfolio decisions (this file + `docs/products/nene-clear.md`) |

**Do not** describe `nene-invoice` as "discard after migration." **Do not**
describe `nene-clear` as replacing or superseding Invoice.

### Integration

- `NeNe Clear → NeNe Invoice API` (read invoices/payments; write payments after match)
- Separate databases, separate admin UIs, separate OpenAPI contracts
- No shared PHP codebase beyond NENE2 framework dependency

### AI-era design principle (both products)

Human confirms in Admin UI; AI proposes via OpenAPI/MCP. Audit trail for
matches (Clear) and issuance/payments (Invoice).

### What NeNe Clear is not

- Not quote, invoice, or qualified invoice PDF
- Not upper compatible with `nene-invoice`
- Not full accounting / general ledger
- Not a debt collection agency

## Alternatives Considered

| Option | Rejected because |
| --- | --- |
| One repo "quote-to-cash" | Conflates document and reconciliation domains; wrong product boundaries |
| Clear as successor to Invoice | Implies migration and upper compatibility — false |
| Clear absorbs Invoice features | Scope creep toward freee; violates narrow-product strategy |
| Shared database | Couples schemas; bypasses API contracts |

## Consequences

- `docs/products/nene-clear.md` describes **reconciliation/dunning only**.
- Invoice roadmap items (PO, contracts, subscriptions, expenses) stay with Invoice strategy — not Clear.
- Profile README and articles must **name both products** when describing back office.
- Success metrics: Invoice stars on `nene-invoice`; Clear stars on `nene-clear` after public launch.

## Related

- Product strategy: [`docs/products/nene-clear.md`](../products/nene-clear.md)
- Clear ADR 0009: `nene-clear` repo
- Issue: #11 (original), amendment #13
