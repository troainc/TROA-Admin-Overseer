# Changelog

## 2026-09-21 — Server operations, staff workflow, events, and releases

Today’s release work consolidated TROA Admin Overseer into a full server-operations toolset.

### Staff, roles, and permissions

- Added durable staff case assignment, status, deadlines, internal updates, queue views, handoff, and timelines.
- Added role comparison, scoped role workflows, temporary roles, presentation, Discord role-ID mapping, and safe templates.
- Expanded opt-in policy enforcement for sensitive moderation, broadcast, and grid actions while preserving native Torch permissions.
- Added optional two-staff ownership-transfer approval that blocks requester self-confirmation.

### Operations and moderation

- Added maintenance status/banner controls, manual operations summaries, and opt-in scheduled audit/webhook summaries.
- Added player-risk context through existing cases, warnings, reports, notes, bans, watch flags, and audit records.
- Added CSV block catalog export, contextual limits, and player-safe grid recovery safeguards.
- v0.8.49 writes the complete vanilla-and-mod block catalogue automatically after every server start/restart to `Instance/TROA Admin Overseer/data/block-subtypes.csv`; manual `!ova limit exportcsv` remains available.

### Events and factions

- Added temporary event roles, event announcements, expiring event MOTD overrides, reward grants, durable check-ins, attendee lists, and attendee CSV exports.
- Added read-only faction dossier and roster commands.
- Verified the installed Torch/Space Engineers APIs do not expose safe public faction member/rank mutation methods; no private reflection workaround was added.

### Release and documentation work

- Validated every release ZIP as `Overseer.dll` plus `manifest.xml` only, with zero build warnings/errors.
- Consolidated the public release index and refreshed owner-facing documentation.

## 2026-09-20 — Core administration foundation

- Established the two-root command model: `!ov` for player-safe actions and `!ova` for administration/owner work.
- Added JSON persistence, auditing, webhooks, moderation, player tools, grid tools, rewards, role foundations, limits, diagnostics, and deployment safeguards.

For the current owner guide, see [README.md](README.md). For concise release history, see [docs/RELEASES.md](docs/RELEASES.md).