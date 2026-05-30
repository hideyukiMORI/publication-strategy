# NeNe Profile — Product Strategy

Cross-project strategy for **NeNe Profile**. Implementation docs live in the public
repository [`nene-profile`](https://github.com/hideyukiMORI/nene-profile).

Decision record: [`0005-nene-vault-nene-profile-product-strategy.md`](../decisions/0005-nene-vault-nene-profile-product-strategy.md).

---

## One line

**Self-hosted bank CSV column mapping for Japan SMB** — any bank format → one
**StandardTransaction** output for Clear, Excel, or scripts.

---

## Portfolio position

Profile sits **upstream of Clear** in the bank pipeline:

```
[Bank CSV] → Profile → StandardTransaction → Clear → Invoice API
```

Vault and Invoice are **not** Profile dependencies.

---

## Ideals

1. **User mapping beats hardcoded banks** — presets are starting points, not prison.
2. **Thin Clear** — reconciliation product does not own a preset engine forever.
3. **Schema contract** — output v1.0 is binding for Clear downstream.
4. **Standalone value** — export to Excel without Clear installed.

---

## Core MVP (NeNe Profile)

- Mapping preset CRUD + versioning
- CSV import job with transformers (dates, debit/credit amounts)
- StandardTransaction JSON + CSV export (schema v1.0)
- Row-level error reporting
- Admin mapping UI (ja + en)
- At least one bundled bank preset (MUFG or SMBC)

**Not in Profile MVP:** invoice matching, dunning, document storage.

---

## Target persona

Office manager who reformats bank CSV in Excel every month before reconciliation —
or Clear operator blocked when their regional bank changes export columns.

---

## Publication (when public)

| Phase | Action |
| --- | --- |
| Phase 0 (2026-05-30) | **Public** repo; runtime MVP pending |
| MVP | Article with Clear two-app pipeline demo |
| Do not | Market as reconciliation tool — that's Clear |

Last updated: 2026-05-29
