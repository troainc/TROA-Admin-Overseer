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
