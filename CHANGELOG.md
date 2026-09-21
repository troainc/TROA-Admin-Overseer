## v0.8.13 — Advanced rewards and limits

- Added opt-in daily streak milestones with configurable bonus bundles.
- Added configurable player near-limit display in `!ov limits`.

## v0.8.12 — Configurable ticket portal

- Added `TicketPortalUrlTemplate` to the master config and player `!ov ticket` links with player/server placeholders.
- Direct website ticket creation remains API-dependent and requires the website endpoint/authentication specification.

# Changelog

This file summarizes current deployable behavior. The dated package archive history is maintained in `docs/RELEASES.md`.

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