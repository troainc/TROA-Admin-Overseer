# Work log

- 2026-09-20: Established single-DLL release validation and paired private/public publication workflow.
- 2026-09-20: Published v0.8.11: access correction, documentation refresh, and validated release workflow.
## v0.8.16 — Staff case summary
- Added !ova case <player> backed by persisted moderation records.
- Removed the obsolete SQLite package reference; release remains one managed DLL plus manifest.

## v0.8.17 — Player audit trail
- Added !ova caseevents <player> [count], capped at 25 SteamID-matched persisted events.

## v0.8.18 — Correlated moderation audit
- Added target SteamID fields to mute, unmute, staff-note, and player-report events.

## v0.8.19 — Resolved report audit link
- Report resolution now returns the resolved record internally and emits its target SteamID.

## v0.8.20 — Player grid recovery
- Added owned-grid !ov fixship, !ov stop, and !ov gridcheck with major-owner, cooldown, block-cap, and audit safeguards.

## v0.8.21 — Configurable player PCU cap
- Replaced the recovery block cap with `PlayerGridToolsMaxPcu`; gridcheck now reports group PCU.
## v0.8.22 — Advanced role inheritance
- Added parent-role persistence, effective role resolution, cycle protection, and permission inspection.
## v0.8.23 — Temporary role grants
- Added durable timed role assignment, automatic expiry, rank recalculation, and audit trail.
## v0.8.24 — Role presentation and Discord mappings
- Added durable prefix/color role presentation plus audited Discord role-ID mapping commands; no Discord credential or automatic access grant is introduced.
## v0.8.25 — Context-aware block limits
- Added per-rule grid kind/size filters, current-world CSV subtype export, and player NEAR/OVER context feedback.
## v0.8.26 — Live limit preview
- Added read-only administrator and player grid-limit feedback commands.
## v0.8.27 — Complete block catalog export
- Exported all registered cube-block definitions with live usage columns for limits planning.
## v0.8.28 — Standard role templates
- Added non-overwriting helper/staff/builder/event/admin/owner role-template workflow.
## v0.8.29 — Scoped role permissions
- Added durable scoped grants and simulator commands.