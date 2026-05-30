# NeNe Vault — Product Strategy

Cross-project strategy for **NeNe Vault**. Implementation docs live in the public
repository [`nene-vault`](https://github.com/hideyukiMORI/nene-vault).

Decision record: [`0005-nene-vault-nene-profile-product-strategy.md`](../decisions/0005-nene-vault-nene-profile-product-strategy.md).

---

## One line

**Self-hosted received-document archive for Japan SMB** — store, search, and
preserve vendor PDFs/images for 電子帳簿保存法 visibility **without** accounting software.

---

## Portfolio position

| Layer | Products |
| --- | --- |
| **Back office — billing** | NeNe Invoice |
| **Back office — reconciliation** | NeNe Clear |
| **Back office — CSV normalization** | **NeNe Profile** |
| **Back office — received documents** | **NeNe Vault** |

```
Operator back office (same server or VPS)
  ├── Invoice  — issued 見積 · 請求 · 入金
  ├── Clear    — 消込 · 督促        ← consumes Profile output
  ├── Profile  — bank CSV → standard rows
  └── Vault    — received PDF archive
```

HTTP only between apps. Separate databases.

---

## Ideals

1. **Storage wedge, honest marketing** — replaces storage-only subscription fees, not a full bundled accounting suite.
2. **Received ≠ issued** — Invoice SSOT for outbound billing; Vault for inbound evidence.
3. **Compliance as structure** — binding scope contract + received-document compliance doc.
4. **Self-hosting** — Tier A beside siblings.
5. **No third-party product names** in repository docs (ADR 0013 in `nene-vault`).

---

## Core MVP (NeNe Vault)

- Multi-tenant foundation
- Document upload (PDF/image) + metadata (date, amount, counterparty)
- Search (date, amount, counterparty, combinations)
- Void/version audit trail; 7–10 year retention policy
- Export manifest for advisors
- Admin UI (ja + en)
- Tier A installer

**Not in Vault MVP:** expense approval, bank CSV, reconciliation, invoice issuance.

---

## Target persona

SMB paying **¥数千–数万/月** for document storage inside a bundled cloud suite but only using
upload and search — wants self-hosted 電帳法-oriented archive.

---

## Publication (when public)

| Phase | Action |
| --- | --- |
| Phase 0 (2026-05-30) | **Public** repo; strategy here; runtime MVP pending |
| MVP | Article: self-hosted received-document archive story |
| Do not | Claim full accounting replacement |

Last updated: 2026-05-29
