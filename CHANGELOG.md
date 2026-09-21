# Changelog

## v0.8.37 — Operations summary
- Added !ova opssummary for recent persisted event totals and critical-event visibility.

## v0.8.36 — Role comparison
- Added administrator role comparison for rank, direct nodes, and inheritance.

## v0.8.35 — Expanded opt-in policy enforcement
- Added optional TROA permission-node gates to sensitive moderation and broadcast actions.

## v0.8.34 — Staff case queue
- Added delegated assignment, active queue, deadline visibility, and internal timeline commands.

## v0.8.33 — Staff case workflow
- Added durable assignment, status, deadline, and internal-update workflows for unresolved player reports.

## v0.8.32 — Enforced two-staff transfer approval
- When the optional two-staff transfer setting is enabled, the requester cannot confirm their own transfer; a distinct administrator must approve it.
- ZIP validated: only Overseer.dll and manifest.xml.

## v0.8.31 — Optional two-staff transfer approval
- Added owner-configurable second-staff approval for ownership transfers, with a 30-second pending preview.


## v0.8.30 — Opt-in command policy enforcement

- Added closed-by-default custom-node policy gates for selected sensitive commands while retaining native Torch rank requirements.

## v0.8.29 — Scoped role permissions

- Added durable faction, player, grid-tag, and command-category scoped permission grants.
- Added scoped grant management and !ova perms scopedcheck explainability without unexpectedly restricting existing commands.

## v0.8.28 — Standard role templates

- Added owner-only !ova role template list|preview|apply for Helper, Moderator, Senior Moderator, Builder, Event Host, Administrator, and Owner starting roles.
- Template application is non-destructive: it never overwrites a live role and tells owners to review before assignment.

## v0.8.27 — Complete block catalog export

- Upgraded !ova limit exportcsv from a current-world list to every registered cube-block definition.
- CSV now includes exact subtype/type IDs, cube size, and live total/ship/station usage columns for rule planning.



This file summarizes current deployable behavior. The dated package archive history is maintained in docs/RELEASES.md.

## v0.8.26 — Live limit preview

- Added read-only !ova limit preview [grid] showing active grid-scoped rules, context, counts, caps, and configured action.
- Added player-safe !ov limitcheck for a wholly major-owned crosshair-targeted grid, including NEAR/OVER feedback.

## v0.8.25 — Context-aware block limits

- Added independent GridKind and GridSize rule filters, allowing the same subtype to have separate ship/station and large/small caps.
- Added owner !ova limit exportcsv current-world subtype catalog and contextual near/over feedback in !ov limits.

## v0.8.24 — Role presentation and Discord mappings

- Added owner-managed custom role prefix/color presentation with !ova role style and safe clear support.
- Added durable, audited Discord role-ID maps through !ova role discord add|remove|list; IDs are stored bridge-ready but do not grant access without a future authenticated identity bridge.

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



This file summarizes current deployable behavior. The dated package archive history is maintained in `docs/RELEASES.md`.

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
