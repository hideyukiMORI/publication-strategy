# Decision 0004: NeNe Clear — Product Strategy and Repository Split

Date: 2026-05-29

## Status

Accepted

## Context

The maintainer identified a new **application-layer** product in the NeNe
portfolio: self-hosted **quote-to-cash billing** for Japan SMB (適格請求書,
shared hosting, MCP-ready). Working name exploration landed on **NeNe Clear**
(clearing / clarity / 消込).

An initial public repository **`nene-invoice`** was used for early governance
and runtime experiments. Strategy, philosophy, and long-term product identity
belong in **this repository** (`publication-strategy`). The **canonical product
repository** is **`nene-clear`** (private until launch-ready).

Sibling applications already shipped: NeNe Records, NeNe Corpus, NeNe Concierge.

## Decision

### Product identity

| Field | Value |
| --- | --- |
| **Public product name** | **NeNe Clear** |
| **Tagline (EN)** | Clear billing from quote to cash. |
| **Tagline (JA, marketing)** | 見積から入金まで、明快に。 |
| **Canonical private repo** | `hideyukiMORI/nene-clear` |
| **Framework** | NENE2 (PHP 8.4), same pattern as Records / Corpus / Concierge |
| **Primary market** | Japan SMB on Tier A shared hosting (FTP + MySQL) |
| **License (when public)** | MIT |

### Repository roles

| Repository | Visibility | Role |
| --- | --- | --- |
| **`nene-clear`** | **Private** (until launch) | Canonical product: docs, code, OpenAPI, releases |
| **`nene-invoice`** | Public | Early experiment; **do not** treat as strategy source of truth; maintainer may revert or archive |
| **`publication-strategy`** | Public | Portfolio decision, expansion sequence, philosophy summary (this file + `docs/products/nene-clear.md`) |

Product implementation Issues and PRs go to **`nene-clear`** after initialization.

### Post-MVP expansion sequence (approved)

Implement **in order** after Phase 1–3 core billing (quote → invoice → payment → PDF/admin):

1. **Payment reconciliation & dunning** — 入金消込・督促管理
2. **Purchase order & delivery note** — 発注書・納品書管理
3. **Contract term & renewal** — 契約期限・更新管理
4. **Small-scale subscription billing** — 小規模サブスク請求管理
5. **Minimal expense reimbursement** — 経費申請の最小版

Details: [`docs/products/nene-clear.md`](../products/nene-clear.md).

### AI-era design principle

Operators confirm in Admin UI; AI assistants (Claude, Codex, MCP clients)
**propose** via OpenAPI/MCP. Billing truth stays in MySQL on the operator's
server — not in chat logs. FTP Tier A does not require AI on the server.

### What NeNe Clear is not

- Not full accounting / general ledger (freee / Money Forward territory)
- Not payroll or expense platform at full scope (Expansion #5 is minimal only)
- Not a WordPress plugin; sibling HTTP integration to Records / Concierge only

## Alternatives Considered

| Option | Rejected because |
| --- | --- |
| Keep only `nene-invoice` public | Name too narrow; strategy docs mixed with throwaway experiment |
| Strategy docs only in `nene-clear` | Portfolio decisions invisible; repeats publication-strategy purpose |
| Product name **NeNe Invoice** | Sounds like PDF-only; undersells reconciliation roadmap |
| Product name **NeNe Collect** | Too aggressive (debt collection tone) |
| Public `nene-clear` from day one | Premature before MVP; private allows doc/code iteration |

## Consequences

- `docs/products/nene-clear.md` is the durable strategy reference (English).
- Profile README and articles should link **NeNe Clear** when the repo goes public.
- `nene-invoice` stars/traffic are not success metrics for this product.
- Review positioning when `nene-clear` reaches Phase 3 (Tier A installer).

## Related

- Product strategy detail: [`docs/products/nene-clear.md`](../products/nene-clear.md)
- Portfolio weapons: [`docs/positioning-matrix.md`](../positioning-matrix.md)
- Issue: #11 (publication-strategy)
