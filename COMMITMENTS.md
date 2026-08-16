# Commitments (append-only)

2026-08-13 | audit-2-sampling-seed | 1d7a2955ae197e6d34cb2d112a95cd95bf5a7a6f2dbe39ea91802a4e4169bd15 | Arc Audit #2 N=500 stratified sampling seed; committed in the private repo (docs/10 §5) before any audit result existed; seed revealed in the audit report 2026-08-14. NOTE: this entry retro-publishes a commitment originally repo-local (disclosed limitation D8.19); entries after this line are anchored here BEFORE use per D8.38.
2026-08-14 | t85b-reaudit-sampling-frame | 74ba28bcb3619d38dc3ebf75550fd5947f1b94a63b69203ca248e34caac1ddb2 | sha256 of the frame definition string "features:<dataset_manifest_id>|shadow:<dataset_manifest_id>" naming the two pinned union dataset manifests the T8.5B re-audit samples from; minted BEFORE any draw.
2026-08-14 | t85b-reaudit-sampling-seed | bc51bb3578080ee2544601a2969c1c001d3453e7ca4bab6a12a72a7cf07dd04d | sha256(seed) for the T8.5B/re-audit stratified draws; FRESH seed (audit-2 seed retired, never reused); runbook version = private-repo commit ae128b3b2a217555f851e0769ce28f62a8a9cb75 (reports/audits/audit-2-plan.md as amended by the ratified review rounds); seed held off-repo by the architect, revealed in the re-audit report at draw time; draws derive via Python random.Random(seed_hex) with per-stratum labeled draws.

## 2026-08-15 — Study-2 rerun evidentiary window declaration (audit2d)

Anchored BEFORE evidentiary T0 per D8.38. The prior same-day audit2c window
is reclassified ENGINEERING_RUN (declared but not ledger-anchored pre-T0).

```
declaration_file   = reports/audits/t85b/study2-rerun-declaration.md (private repo)
declaration_sha256 = 7edd7cb3235a3b8ea88bc6bbc724e35116e2be3b49b8ddd73b77eb7d40f3a2a4
runbook_commit     = 37b0f0eea3c378af41bb89ccfc340f27713a07b8 (private repo main)
window             = [T0, T0 + 6.0h] wall-clock; T0 = audit2d open-meta t, stamped at launch
trim_authority     = per-line capture timestamp t
seed               = revealed t85b seed (commitment bc51bb35..., this ledger, entry 324b244)
sub_draw_labels    = -study2d-slots, -study2d-class (first use)
published_at       = 2026-08-15T08:48:25+00:00
```

## 2026-08-15 — Study-5 chaos drill declaration (pre-run)

Anchored BEFORE the first drill. Pass criteria fixed at declaration time.
Close-plan drill (a) mid-open-position is DEFERRED, declared in advance:
the trader's own UTC-day drawdown halt is active, so no position can open,
and the halt will not be cleared to manufacture a test condition.

```
declaration_file   = reports/audits/t85b/chaos-drill-declaration.md (private repo)
declaration_sha256 = adb1644d2c6a28c2d8d1638a51862f4ce4183d2593a87c4e349c48aa051336f1
runbook_commit     = 17e12cd1d41ea69b7c3a30c3f0ecc7a083df7e04
pre_state          = run shadow-1786782891, open_positions 0, drawdown 1587853168 lamports,
                     loss_streak 2, halts_raised 8, entries_allowed false
published_at       = 2026-08-15T21:53:39+00:00
```

## 2026-08-15 — Study-5 chaos drills ROUND 2 declaration (pre-run)

Round 1 drill A' FAILED (restart cleared an active drawdown halt; root cause
F25a: store URL defaulted to port 5432, server on 55432, so every daemon start
ran without persistence). Round 1's FAIL stands and is not superseded.
Round 2 asks the separate open question: does persistence work once attached?

```
declaration_file   = reports/audits/t85b/chaos-drill-declaration-round2.md
declaration_sha256 = 6ee647748cbeabf65059ae577a50a3db80bbe94f9fb588be2b47b1195633e7f4
runbook_commit     = f4e7cbb4ce4f204aa3f3a1423160f5c34a483a34
store_attached_at  = 2026-08-15T22:05:48Z (log: state rebuilt from the decision log)
run_id             = shadow-1786831548
published_at       = 2026-08-15T22:08:51+00:00
```

## 2026-08-15 — Study-5 chaos ROUND 3 declaration (pre-run): halt survival

Round 1 drill A' FAILED (restart cleared an active drawdown halt). Round 2
proved persistence works once the store is attached but could NOT score halt
survival - no halt was active at kill time - and recorded it as still open.
This drill closes that sub-case against the fixed build (F25a+F25b, 07821ba).
A 90-minute bound is precommitted: if no halt fires naturally within it, the
drill is recorded NOT RUN rather than provoked.

```
declaration_file   = reports/audits/t85b/chaos-drill-declaration-round3.md
declaration_sha256 = e36be77aa57752980ac449c1ff1c2d7a5087e039d68ab1849079ef2814d4b5ea
runbook_commit     = 891c0d267100a6bea8190175dfe41e024dc7b451
bound              = 90 minutes; halts must fire naturally, never induced
published_at       = 2026-08-16T03:08:01+00:00
```

## 2026-08-15 — Study-5 chaos ROUND 4 declaration (pre-run): drill A, mid-open-position

Last unexercised preregistered element of Arc Audit #2. Deferred at round 1
because a drawdown halt blocked entries and the halt was not cleared to
manufacture the condition. 30-minute bound precommitted; positions must open
naturally.

```
declaration_file   = reports/audits/t85b/chaos-drill-declaration-round4.md
declaration_sha256 = ed61addc63392f87aa1c2be2392926d58f1baac48edffe972ffb62fdbe6d02ce
runbook_commit     = 3b4fd7e8e5c8fa463764b649a30ad06a0352a580
published_at       = 2026-08-16T03:19:00+00:00
```

## 2026-08-16 — Study-2 RECALL classification declaration (pre-inspection)

External review established that Study 2 proved precision far better than
recall: n=30 with 0 findings bounds the miss fraction only at ~9.5%. This
declares a powered reclassification on the FROZEN audit2d corpus. Anchored
before any signature is looked up, because reclassification on frozen data
carries the same temptation to peek as a fresh window.

```
declaration_file   = reports/audits/t85b/study2-recall-declaration.md
declaration_sha256 = 4385482e462f69afd9615726d8cdb8d846a3dfd7c889e1f889ab26314cf137b4
runbook_commit     = 5c5406951940a11ee6fdd5bdc743e5dd3482f90d
population         = REFERENCE_ONLY = 227,438 (matched 768,068; magpie-only 3,713,930)
sample             = n=3000, label -study2d-recall-3000 (first use)
tolerance          = one-sided 95% upper bound on supported-event fraction <= 0.1%
published_at       = 2026-08-16T03:48:39+00:00
```
