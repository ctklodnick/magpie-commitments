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
