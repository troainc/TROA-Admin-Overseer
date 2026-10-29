## v0.8.93 local package candidate - Source alignment and restart coordination (not a public release)

- Reconciles the closed source line with the complete v0.8.92 tree; the new package is v0.8.93 instead of the stale-base v0.8.61 prototype.
- Adds a default four-hour Overseer restart schedule and owner `!ova restart status|now|cancel` controls. Overseer requests Cleaner+ deep cleanup and waits for the explicit drained state, then confirms a Torch save, sends the 60-second countdown, and requests Torch restart.
- Failed/unavailable cleanup, timed-out cleanup, failed save, or inability to save the restart-confirmation marker cancels that cycle. Cleaner+ remains cleanup owner; Overseer owns restart timing.
- Carries the alert-only block-limit starter examples and subtype-family wildcard matching into the v0.8.93 private package.
- Private ZIP: `TROA Admin Overseer v0.8.93 - Scheduled Restart Coordination.zip` (328320 bytes; SHA-256 `A5F65C86A1DE561CB5737250A34BE83F1E047B7550628FF3BE4B6090C5570F47`). Release build passed with zero warnings/errors and the ZIP contains only `Overseer.dll` and `manifest.xml`; Linux/Wine AMP runtime acceptance remains pending. No public binary release is published.

## Superseded v0.8.61 candidate - stale source base

The v0.8.61 prototype was built from source v0.8.49 even though v0.8.92 packages already existed. It is archived from the current `releases/` list and must not be used as the latest version. Its restart work was carried forward into v0.8.93 on the complete source base.
## 2026-10-10 — v0.8.89 legal information pages (candidate; not in published binary)

- Adds deployment-draft Terms of Service and Privacy & GDPR documents modeled on the structured Bifrost Server Manager privacy notice and limited to Admin Overseer's self-hosted Panel data flows.
- The candidate Panel adds unauthenticated `/terms` and `/privacy` pages, linked from sign-in/owner setup and the main footer. This runtime behavior is not included in the currently published binary.
- The drafts identify current local records, session lifetime, count-based history/event caps, plugin data ownership, retention gaps, and operator security/privacy responsibilities. They require deployment verification and qualified review; they make no GDPR-compliance claim.

## 2026-10-09 — Bifrost Plugin Panel operator guide

- Adds an operator guide for webserver setup, owner sign-in, accounts, plugin workspaces, capability labels, data freshness, and troubleshooting.
- Documents release-dependent availability and keeps plugin actions with their owning plugins. Documentation only; no adapter or runtime behavior change is claimed.

## v0.8.61 — Bifrost live plugin dashboards

- Expanded every detected TROA plugin workspace with visual live metrics, version/state/registered-command cards, plugin-owned command shortcuts, readable formatting, and responsive desktop/mobile styling.
- GridVault displays live world grids, unique stored grids, retained and incomplete backups, cleanup archives, stored size, latest backup/grid, queue/pass status, and a 14-day history chart.
- Econ+ exposes player-account and credit/treasury totals plus open contracts. Hangar+ exposes stored grids, market listings/bids, and recent storage activity where owner data is available. Other workspaces show operational readings supplied by their owning plugin APIs.
- Corrected the command browser to use paths from Torch's registered command tree.
- Release package validation passed. Dedicated Torch runtime and device acceptance are unverified.
# Changelog
## 2026-10-08 — v0.8.62 Bifrost native live dashboards

- Repaired embedded workspace CSS that could appear as page text.
- Fixed command authorization lookup to mirror Torch's prefix stripping while preserving the prefixed command for execution.
- Added 10-second live plugin workspace refresh, native trend/bar charts, and percentage/ratio gauges without a Grafana installation.
- Cleaner+ visualizes tracked/concealed/flagged grids, simulation ratio, queued removals, and cleanup history. Econ+ adds recent transaction/recovery totals and completed volume. Existing Profiler+, GridVault, and Hangar+ metrics remain sourced from owner data.
- Build succeeded with 0 warnings and 0 errors; release ZIP verification passed. Dedicated Torch/browser runtime acceptance is unverified.

## 2026-10-08 — v0.8.60 Bifrost TROA plugin workspaces (local candidate; not published)

- Added TROA-only plugin workspaces with configuration editing saved/reloaded through each recognized plugin's existing configuration path; non-TROA tools such as AMPutilities are omitted.
- Owners and Admins can edit allowed settings; Moderators are read-only. High-impact Cleaner settings are Owner-only. Secret values remain masked, and scalar-list inputs are JSON-validated.
- Added live operational summaries for Profiler+, Cleaner+, and GridVault when their data APIs are available. The panel does not invent unavailable metrics; AIO Updater settings apply on its next scan. Added a searchable console for loaded TROA commands, with plugin owner, syntax, and Torch permission levels. Admin and Owner logins can submit one command at a time; Owner-level commands require the panel Owner.
- Added the public webserver sample config and Bifrost setup/use documentation. Plugins without a safe detected save/reload path show “Integration needed.”
- Local Release build completed with 0 warnings and 0 errors. ZIP validation confirms only `Overseer.dll` and `manifest.xml`, version 0.8.60. Dedicated Torch runtime acceptance and GitHub publication remain pending.

## 2026-10-08 — v0.8.59 Bifrost Panel webserver (candidate; no GitHub release)

- Added the initial Bifrost Panel - SE Torch dashboard, hosted inside Admin Overseer and connected to Torch's live plugin manager.
- A dedicated `TROA Admin Overseer Webserver.cfg` controls the listener (`Enabled`, `BindAddress`, `Port`, `PublicUrl`) and is created beside the other Overseer configs. It defaults to loopback; use an HTTPS reverse proxy for untrusted networks.
- After the game session loads, log a green “Bifrost Webpanel is online and ready to use” message and publish the Server success event only if the listener started successfully.
- Added one-time owner account setup, individual Owner/Admin/Moderator accounts, salted PBKDF2 password hashes, 12-hour in-memory sessions, and owner-only account creation/removal.
- All panel endpoints require sign-in except setup-status and health checks. Per-plugin config Save/Reload remains pending owner-plugin adapters; the candidate does not directly write other plugins' files.
- Clean local Release build and package verification passed with 0 warnings and 0 errors. The local package includes the webserver config example; dedicated Torch config creation and browser access need runtime acceptance. This is not a published GitHub release.

## Public operator documentation expansion - 2026-10-06

- Added a detailed user guide under docs/USER_GUIDE.md and linked it from the documentation index and root README.
- Documented current setup, feature ownership, command/config references, operational workflows, safety boundaries, and version/status limitations using the published behavior.
- Added repository-local context, contribution instructions, and a dated documentation log entry. No private source or credentials are included.

## 2026-09-30 — v0.8.56 Rewards catalog and progression

- Added an editable rewards CSV catalog that automatically includes registered vanilla and modded physical items, preserves existing owner rows, and supports multi-item bundles.
- Added configurable daily streak, continuous-session playtime, and travel-distance milestones plus a player progress command.
- Added admin catalog list, preview, and grant commands, including durable queuing for offline players; bounded catalog list output for servers with many modded items.
- Branded Discord reward command responses as TROA Admin Overseer. Vote links, reservations, claims, and reward history remain owned by Admin Overseer.
- Build and ZIP verification passed with zero warnings/errors; dedicated-server runtime acceptance remains pending.

## 2026-09-29 — v0.8.55 Restart countdown

- After a successful save, owner-only `!ova restart` announces 60, 30, 10, 5, 4, 3, 2, and 1 seconds remaining in global in-game chat and through the configured Server webhook route.
- Torch restarts 60 seconds after save completion; announcement dispatch does not add time to the countdown. Failed, timed-out, or already-running saves still cancel the restart.
- The next-startup green “Restart and Save were successful.” confirmation remains in place. Build/package passed with 0 warnings and 0 errors; dedicated-server runtime acceptance is pending.
- Local package: `TROA Admin Overseer v0.8.55 - Restart Countdown.zip`; SHA-256 `CF710825BD47AFCABDD11A3C6B4D007592ECE27CC664ABF8C39C8F8410F3EC1F`.

## 2026-09-28 — v0.8.54 Restart and save confirmation

- After `!ova restart` confirms the save and completes its 60-second delay, Overseer persists a one-time startup confirmation marker before asking Torch to restart.
- On the next qualifying startup, Overseer logs “Restart and Save were successful.” in green where Torch's console honors ANSI colors and sends a green success embed through the configured Server webhook route.
- Stale markers expire after two hours. Build/package validation passed with 0 warnings and 0 errors; dedicated-server console coloring and webhook delivery still need runtime acceptance.
- Local package: `TROA Admin Overseer v0.8.54 - Restart and Save Confirmation.zip`; SHA-256 `4606ABF906D072187A1D560F0607F67AAE02F3D6BFD7A9EC54A77E5BBCEA3E6A`.

## 2026-09-28 — v0.8.53 Save-confirmed delayed restart

- Added owner-only `!ova restart`: await successful Torch world-save completion, wait 60 seconds, then restart Torch.
- A save already in progress, failure, timeout, or exception cancels the restart. Duplicate restart sequences are rejected.
- Package build passed with 0 warnings and 0 errors after disabling unavailable NuGet audit feed lookup for the offline build; ZIP contains only `Overseer.dll` and `manifest.xml`. Dedicated-server runtime acceptance remains pending.
- Local package: `TROA Admin Overseer v0.8.53 - Save Confirmed Delayed Restart.zip`; SHA-256 `9A43697C0583D0A9C1614B44B6927F630FFB1FB9AA5C306E0EAF6236C1939969`.

## 2026-09-28 — v0.8.52 Full public configuration examples

- Added secret-free examples for all eight v0.8.52 config files, not only Webhooks.
- Linked the full set from the README and documented placeholders and private secrets.

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

## Documentation navigation - 2026-10-03

- Added direct README navigation to deployment, configuration, commands, permissions, and webhook guides.
## Documentation correction - 2026-10-06

- Clarified that Admin Overseer owns its save-confirmed restart workflow and Monitor+ is only its authorized command transport.
- Updated public roadmap ownership and release-gated rewards/restart priorities; current public version remains v0.8.56.
- Added a root-level `ROADMAP.md` and linked it from the README for easier discovery.
