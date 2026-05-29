# NeNe Clear — Product Strategy

Cross-project strategy for **NeNe Clear**. Implementation docs and code live
in the private product repository [`nene-clear`](https://github.com/hideyukiMORI/nene-clear).

Decision record: [`0004-nene-clear-product-strategy.md`](../decisions/0004-nene-clear-product-strategy.md).

---

## Domain split (read first)

**NeNe Clear and NeNe Invoice are completely separate products.**

| Product | Repository | Domain |
| --- | --- | --- |
| **NeNe Invoice** | [`nene-invoice`](https://github.com/hideyukiMORI/nene-invoice) | Quote, invoice, payment management — **見積・請求・入金管理** |
| **NeNe Clear** | `nene-clear` | Payment reconciliation & dunning — **入金消込・督促管理** |

- **Not upper compatible.** Clear does not replace Invoice. No migration path.
- **Intended production:** both apps on the same server, **HTTP between them**, separate databases.

---

## One line

**Self-hosted payment reconciliation and dunning for Japan SMB** — match bank
deposits to billed receivables, send logged overdue reminders.

**Not** quote or invoice issuance — that is NeNe Invoice.

---

## Portfolio position

| Layer | Products |
| --- | --- |
| **Framework** | NeNe, NENE2, nene2-python, nene2-node |
| **Front office** | NeNe Records, NeNe Corpus, NeNe Concierge |
| **Back office — billing documents** | **NeNe Invoice** (`nene-invoice`) |
| **Back office — reconciliation** | **NeNe Clear** (`nene-clear`) |

```
Operator back office (same server or VPS)
  ├── Invoice  — 見積 · 請求 · 入金管理
  └── Clear    — 入金消込 · 督促管理
        ↓ HTTP (Invoice API)
      Invoice
```

Integration: **HTTP only** — never shared databases.

---

## Ideals

1. **One domain, done well** — reconciliation and dunning only; no invoice scope creep.
2. **Invoice upstream is truth** — Clear never owns issued invoice figures.
3. **Human confirms, AI proposes** — match suggestions require operator confirmation.
4. **Compliance as structure** — binding reconciliation/dunning rules in Clear repo.
5. **Self-hosting** — beside Invoice on Tier A shared hosting.

---

## Core MVP (NeNe Clear)

- Multi-tenant foundation
- NeNe Invoice API upstream (read invoices/outstanding; write payments on match)
- Bank CSV import → `bank_transaction`
- Human-confirmed match → `payment_reconciliation` + audit
- Dunning templates + send log + minimum interval
- Admin UI (ja + en)
- Tier A: web installer + release ZIP (Clear as second app)

**Not in Clear MVP:** quotes, invoices, PDF, tax validation — see `nene-invoice`.

---

## What is NOT on Clear's roadmap

These belong to **NeNe Invoice** (or future Invoice expansions), not Clear:

- Purchase orders & delivery notes
- Contract renewal
- Subscription billing
- Expense reimbursement

Legacy Clear docs that listed these as "Expansion #2–5" are **void** — see
Clear repo `docs/explanation/scope-boundary.md`.

---

## Target persona

Regional **food ingredient wholesaler** already on NeNe Invoice. Office manager
downloads bank CSV weekly, matches in Excel, sends overdue emails manually.
Wants **reconciliation screen + audit trail + dunning history** without moving
invoices out of Invoice.

---

## Publication strategy (when public)

| Phase | Action |
| --- | --- |
| Pre-launch | Private `nene-clear`; strategy here |
| MVP complete | Flip Clear public; document **Invoice + Clear** two-app setup |
| Article | Reconciliation/dunning story — link Invoice as prerequisite |
| Do not | Describe Clear as "full billing" or Invoice replacement |

Track stars separately: **`nene-invoice`** for billing, **`nene-clear`** for reconciliation.

---

## Repository map

| Repo | Purpose |
| --- | --- |
| `nene-invoice` | **Quote · invoice · payment** — public, active |
| `nene-clear` | **Reconciliation · dunning** — private until launch |
| `publication-strategy` | This file + decision 0004 |

**Not:** "discard Invoice after migration."

---

## Review

Revisit when Clear MVP lands or Invoice upstream OpenAPI stabilizes — 2026-Q3 or later.

Last updated: 2026-05-29 (domain split amendment)
