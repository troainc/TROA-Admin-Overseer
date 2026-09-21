# Changelog

This file summarizes current deployable behavior. The dated package archive history is maintained in `docs/RELEASES.md`.

## v0.8.23 — Temporary role grants

- Added durable `!ova role temporary <player> <role> <duration>` grants, automatic 30-second expiry sweep, rank recalculation, and audit/webhook events.
- Added `!ova role temporarylist <player>` for administrator review.
## v0.8.22 — Advanced role inheritance

- Added durable custom-role inheritance with cycle protection and inherited effective Torch ranks and permission nodes.
- Added owner commands `!ova role inherit` / `!ova role uninherit` and administrator `!ova perms check` for explainable custom access.
## v0.8.21 — Configurable player PCU cap

- Replaced the player grid-recovery block cap with `PlayerGridToolsMaxPcu`, an owner-configurable PCU maximum (default `20000`; `0` disables the additional cap).
- `!ov gridcheck` now reports total PCU for the owned mechanical group.
## v0.8.20 — Player grid recovery

- Added player-safe !ov fixship, !ov stop, and !ov gridcheck for the owned grid under a player's crosshair.
- Player recovery requires major ownership across the complete mechanical group and uses configurable cooldown and block-cap safeguards.

## v0.8.19 — Resolved report audit link

- Resolved-report events now include the reported player’s SteamID and name, making them visible in !ova caseevents.

## v0.8.18 — Correlated moderation audit

- Added target SteamIDs to mute, unmute, staff-note, and player-report audit events so they appear reliably in !ova caseevents.

## v0.8.17 — Player audit trail

- Added !ova caseevents <player> [count] to show up to 25 stored audit events explicitly tied to that player’s SteamID.

## v0.8.16 — Staff case summary

- Added read-only !ova case <player> for a unified staff view of active ban status, watch flags, warnings, notes, reports, roles, and possible alts.
- Removed the obsolete SQLite package reference so release builds do not carry that dependency.

## v0.8.15 — Grid health scanner

- Added `!ova gridcheck [grid]` for read-only grid identity, block, owner, motion, and mechanical-group details.

## v0.8.14 — Configuration doctor

- Added owner-only `!ova doctor` for read-only webhook, rewards, limits, ticket, and legacy-config checks.
- Restored administrator-only access for `!ova help`.

## v0.8.13 — Advanced rewards and limits

- Added opt-in daily streak milestones with configurable bonus bundles.
- Added configurable player near-limit display in `!ov limits`.

## v0.8.12 — Configurable ticket portal

- Added `TicketPortalUrlTemplate` to the master config and player `!ov ticket` links with player/server placeholders.
- Direct website ticket creation remains API-dependent and requires the website endpoint/authentication specification.

## v0.8.11 — Owner documentation and access consistency

- Rebuilt the server-owner README, command reference, configuration guide, webhook guide, deployment checklist, and roadmap.
- `!ova help` now requires administrator access, matching the privileged command root.
- Documented the single-DLL release validator and live-server acceptance process.

## v0.8.10 — Release readiness

- Added `verify-release.ps1`; every `pack.ps1` run now verifies a matching manifest/DLL version and exactly two ZIP entries.
- Added repository context and work-log guidance.

## v0.8.9 — Safe legacy migration

- Legacy `!ov` administration spellings are redirects only. They show the required `!ova` form and cannot run privileged actions.

## v0.8.8 — Player support

- Added `!ova gps <player>` for online player coordinates.
- Added `!ov rewards` for a player’s own recorded claims.

## v0.8.7 and earlier — Core modernization

- Two-tier command model: `!ov` for player-safe commands and `!ova` for administration/owner workflows.
- Safe look-at grid repair/stop, confirmation-gated grid ownership transfer, and no grid deletion command.
- Managed JSON persistence for player records, sessions, roles, bans, claims, notes, reports, and audit history.
- Moderation reports/warnings/notes, owner save and scheduler controls, webhook routing, and TROA-prefixed config migration.

## Boundaries

TROA Admin Overseer does not own grid deletion/backup/restore, hangar storage, cleanup, or restart automation. Those remain with TROA GridVault, TROA-Hangar, and TROA Cleaner+.
