# NeNe Clear — Product Strategy

Cross-project strategy for **NeNe Clear**. Implementation docs and code live
in the private product repository [`nene-clear`](https://github.com/hideyukiMORI/nene-clear)
(when accessible to maintainers).

Decision record: [`0004-nene-clear-product-strategy.md`](../decisions/0004-nene-clear-product-strategy.md).

---

## One line

**Self-hosted quote-to-cash billing for Japan SMB** — qualified invoices, payment
clearing, and dunning on infrastructure the operator already owns.

---

## Portfolio position

| Layer | Products |
| --- | --- |
| **Framework** | NeNe, NENE2, nene2-python, nene2-node |
| **Front office** | NeNe Records (CMS), NeNe Corpus (knowledge chat), NeNe Concierge (scenario chat) |
| **Back office** | **NeNe Clear** (billing) |

```
Visitor-facing site
  ├── Corpus    — ask questions (cited)
  ├── Concierge — convert (scenario chat)
  └── Records   — content & catalog

Operator back office (same server or VPS)
  └── Clear       — quote → invoice → collect → clear
```

Integration: **HTTP only** between siblings — never shared databases.

---

## Ideals

1. **Clear money trail** — quote, invoice, deposit, and outstanding balance in
   one auditable place (not email + Excel + bank CSV).
2. **Self-hosting as feature** — Tier A shared hosting beside WordPress; no
   extra SaaS subscription for billing ops.
3. **Compliance as structure** — 適格請求書 rules enforced in the API, not
   decorative PDF fields.
4. **Human confirms, AI proposes** — Admin UI for decisions; OpenAPI/MCP for
   agents; audit log for matches and dunning.
5. **Narrow and deep** — quote-to-cash first; resist becoming freee.

---

## Philosophy (summary)

- **Clear over clever** — explicit layers, integer cents, registered terminology,
  OpenAPI before UI.
- **Dual surface** — every operator action reachable by documented HTTP/MCP;
  no hidden SQL paths for agents.
- **Bilingual operators, Japanese law** — admin UI ja + en; statutory invoice
  content Japanese (same pattern as other NeNe apps).

Full product philosophy doc: `nene-clear` repo → `docs/explanation/philosophy.md`.

---

## Core MVP (Phase 1–3)

Before any expansion item:

- Multi-tenant foundation (`organization_id`, roles: superadmin / admin / member)
- Clients, quotes, invoices, line items, payments
- Japan qualified invoice validation + PDF
- Admin UI (ja + en)
- Tier A: web installer + release ZIP

---

## Post-MVP expansion roadmap (approved order)

### 1. Payment reconciliation & dunning — 入金消込・督促管理

**Why first:** Completes quote-to-cash; daily pain for office managers; extends
`payment` / `overdue` without new document types.

| MVP | Out of scope (initially) |
| --- | --- |
| Bank CSV import → `bank_transaction` | Bank API / Moneytree sync |
| Manual + rule-based match suggestions | Fully automatic clearing without confirm |
| AI-assisted match via MCP (propose only) | AI silent writes |
| Dunning email templates + send log | Debt-collection automation |

Phases: import → manual match → suggestions → dunning.

### 2. Purchase order & delivery note — 発注書・納品書管理

**Why second:** Extends document chain PO → delivery → invoice for B2B
wholesale/manufacturing persona.

- `purchase_order` to suppliers; `delivery_note` linked to quote/invoice
- Reuses line-item and PDF patterns
- Not inventory / stock (future NeNe Shop territory)

### 3. Contract term & renewal — 契約期限・更新管理

**Why third:** Client master + renewal quotes before subscription engine.

- `contract`: start/end, auto_renew, renewal_notice_days
- Expiry dashboard; one-click renewal quote
- Not full CLM (DocuSign / CloudSign)

### 4. Small-scale subscription billing — 小規模サブスク請求管理

**Why fourth:** Needs stable invoice + payment + preferably reconciliation.

- Monthly/yearly plans; scheduled draft invoices
- Pause / cancel
- Not proration, metered billing, or card-on-file in MVP

### 5. Minimal expense reimbursement — 経費申請の最小版

**Why last:** Different actor (employee); approval workflow; minimal scope only.

- Submit → single-step approve → CSV export for accountant
- Not payroll, commute rules, or corporate card feeds

---

## Target persona

Regional **food ingredient wholesaler**, ~8 staff, shared hosting, office manager
issues 適格請求書 from admin UI instead of Excel + manual PDF. freee monthly
fee feels heavy; operator already pays for hosting.

Same pattern: small manufacturers, agencies, equipment dealers — B2B
quote-before-invoice.

---

## Publication strategy (when public)

| Phase | Action |
| --- | --- |
| Pre-launch | Private `nene-clear`; strategy here only |
| Phase 3 complete | Flip repo public; GitHub About + profile README row |
| Article | One product story — Japan SMB self-hosted billing + MCP (Zenn JP or DEV EN) |
| Do not | Mix Clear launch with framework or Records narrative in same post |

Track stars/traffic on **`nene-clear`** after public — not `nene-invoice`.

---

## Repository map

| Repo | Purpose |
| --- | --- |
| `nene-clear` | **Canonical** — private until launch |
| `nene-invoice` | Discard or archive after migration; not strategy SSOT |
| `publication-strategy` | This file + decision 0004 |

---

## Review

Revisit when `nene-clear` Phase 3 lands or Expansion #1 ships — 2026-Q3 or later.

Last updated: 2026-05-29 (Issue #11)
