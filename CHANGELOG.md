# Changelog

## 2026-09-28 — v0.8.52 Webhooks config example

- Added a public, secret-free Webhooks config example showing URLs in the correct <WebhookRoute> <Url> field.
- Linked the example from the README and Webhooks guide; corrected the README current version to v0.8.52.

## 2026-09-28 — v0.8.52 Clear webhook config errors

- Webhook config errors tell owners to put each Discord URL inside its `<WebhookRoute Name="...">` block's `<Url>...</Url>` field, not directly under `<Routes>`.
- The diagnostic points to the XML line/column where available, explains that defaults loaded and a `.bad-*` backup was created, and tells the owner to correct the route and run `!ova reload`.
- The v0.8.52 package built with 0 warnings/errors and passed ZIP validation. Dedicated-server runtime acceptance remains pending.
- Local package: `TROA Admin Overseer v0.8.52 - Clear Webhook Config Errors.zip`; SHA-256 `43260A7E9E288F0F3DF45B35D2252720100C9D26E2FF9AF3E943C5211466D58B`.

## 2026-09-28 — v0.8.51 XML URL configuration repair

- Documents the automatic repair of unescaped ampersands in Webhooks and Rewards XML values, preserving multi-parameter URLs and other settings.
- Records the fix for configured Webhooks routes and Rewards lists replacing initialized defaults instead of being appended after them.
- Server owners should edit the plugin's active `StoragePath`; unrecoverable XML still produces a `.bad-*` backup and startup-log error.
- Admin Overseer retains its reward/admin commands and webhook routes while Monitor+ supplies Discord command transport; Econ+ owns balance and GridVault owns grid backup/recovery.
- Build/package validation is distinct from dedicated-server runtime acceptance.

## 2026-09-27 — v0.8.50, consolidated Discord vote rewards

- Added linked Discord vote reservations through channel-scoped `!reward` and `/adminoverseer` commands; pending claims are completed in-game with `!ov claim`.
- Added persistent pending reservations, vote history, voter leaderboard, and reward claim history.
- Added a repeat-safe importer for pending reward IDs and voter history from Monitor+ storage. Monitor+ v1.1.5K6 removes its voting/rewards implementation and retains account linking and optional economy balance support.
- Build and release ZIP validation passed. Dedicated-server runtime acceptance remains to be confirmed on the target server.

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
