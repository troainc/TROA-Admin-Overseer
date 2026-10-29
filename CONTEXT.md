# Project context

2026-10-10 release documentation adds deployment-draft [Terms of Service](docs/TERMS-OF-SERVICE.md) and [Privacy & GDPR Notice](docs/PRIVACY-GDPR.md). v0.8.89 also serves public `/terms` and `/privacy` routes and links them from sign-in/setup and the Panel footer; this UI behavior is included in the v0.8.93 release. The notice describes inspected self-hosted Panel data flows, is adapted from the Server Manager disclosure structure, and makes no GDPR-compliance claim.

Admin Overseer owns its reward and admin commands, persisted reward history, and configured webhook routes. Monitor+ is an optional Discord command transport; Econ+ owns balances and GridVault owns grid backup/recovery.

TROA Admin Overseer is a clean-room Torch administrative plugin for Space Engineers. Public product name and data path are `TROA Admin Overseer`; server owners choose `ServerName` only for branding. It is a single managed-DLL plugin with JSON persistence under `Instance/TROA Admin Overseer/Overseer.json`.

Current command contract: `!ov` for player-safe commands and `!ova` for privileged commands. Legacy `!ov` admin spellings are redirects only.
Current release is v0.8.93; v0.8.93 includes the current released Bifrost and restart coordination changes. Bifrost Panel is hosted by Admin Overseer and lists TROA plugins only. It provides plugin-owned config settings and Save/Reload for detected safe paths; Admin/Owner writes are role-gated, Moderator is read-only, secrets are masked, and unsupported plugins show Integration needed. A searchable console catalogs loaded TROA commands and routes submissions through Torch; Admin and Owner may execute, but commands marked Owner-level require the panel Owner, and execution is logged with account attribution. Profiler+, Cleaner+, and GridVault live summaries appear only when their runtime APIs expose data. AMPUtilities is excluded. Admin Overseer owns rewards, vote claims, configured webhook routes, and its save-confirmed `!ova restart`; Monitor+ only transports authorized commands and their replies. Cleaner+ owns cleanup scheduling, not restart execution.
Current staff workflow includes !ova case <player> for moderation context and !ova caseevents <player> [count] for player-specific persisted audit events.

Moderation audit events use stable target SteamIDs for case-history correlation; display names are never the matching key.

Player-report submissions and resolutions are both SteamID-correlated in the persisted audit trail.

Player self-service grid recovery is available under !ov fixship, !ov stop, and !ov gridcheck; it is limited to an in-game caller's wholly major-owned mechanical group and master-config limits.

Player grid recovery uses the owner-configurable `PlayerGridToolsMaxPcu` master-config limit (default 20000 PCU; 0 disables the additional plugin cap).
Advanced roles support durable parent-role inheritance with cycle protection. Effective Torch rank and custom permission nodes resolve across direct and inherited roles; `!ova perms check` explains node grants.
Temporary direct roles persist in JSON and expire every 30 seconds through the roles module; expiry removes the role, reapplies effective native rank, and emits an audit event.
Role records retain safe presentation labels and owner-managed Discord role-ID mappings; those role IDs do not grant access or synchronize roles. The optional Rewards module has a separately configured Discord bot token for channel-scoped vote reservations only, with explicit Discord-to-Steam mappings.

The local v0.8.60 release extends Bifrost with TROA-only plugin config workspaces, a searchable TROA command catalog and console, and live plugin summaries when supported. Admin and Owner accounts may execute commands, Owner-level commands require the panel Owner, and execution is account-attributed in the Torch log. GitHub release publication and dedicated-server runtime acceptance remain pending.
Limits now support independent ship/station and large/small context filters for the same subtype. Owners export observed current-world subtype IDs with !ova limit exportcsv; player !ov limits feedback names the applying context.
Live limit previews: !ova limit preview [grid] is admin read-only; !ov limitcheck is player-safe and requires whole-group major ownership.
The owner CSV export now lists every registered cube-block definition, including unbuilt definitions, alongside live total/ship/station usage counts.
Role templates now provide previewable, non-overwriting standard ranks; review generated roles before assignment.
Scoped permission grants now support faction, player, gridtag, and category policies with explainable simulation.
Public v0.8.31/v0.8.32 documentation records optional, enforced second-staff approval for grid ownership transfers without exposing private source.

Public v0.8.33 guidance documents durable report assignment, status, deadline, and internal update workflows.

Public v0.8.50 guidance documents Discord vote reservations, persistent pending claims/history, the voter leaderboard, and the repeat-safe Monitor+ import. Monitor+ v1.1.5K6 no longer owns voting/rewards; its account-linking and optional economy features remain separate. Current package build/ZIP checks passed; dedicated-server gameplay and Discord runtime acceptance remain server-side validation.

Public v0.8.51 guidance documents safe repair of bare ampersands in Webhooks and Rewards XML values. Owners should edit config files under the plugin `StoragePath` reported in the startup log; runtime acceptance remains separate from package validation.
2026-09-21: Rebuilt public README as a server-owner how-to and consolidated the changelog by date.

v0.8.49 documentation: block-subtypes.csv is generated automatically after each server session start/restart at `Instance/TROA Admin Overseer/data/`.


Public v0.8.54 guidance documents owner-only !ova restart: confirmed successful save, fixed 60-second delay, then a one-time persisted startup confirmation. On the next qualifying load, the plugin logs “Restart and Save were successful.” in green where Torch honors ANSI colors and sends a green success embed through its enabled Server webhook route. Markers expire after two hours. Build/package validation is separate from dedicated-server runtime acceptance.


## Detailed public guide

The maintained setup and feature guide is docs/USER_GUIDE.md; keep its status statements aligned with the public release and roadmap.


Bifrost Panel v0.8.58 release adds separate webserver settings, one-time owner bootstrap, Owner/Admin/Moderator accounts, salted PBKDF2 password hashes, and in-memory 12-hour sessions. Save/Reload access is intended for server owners/admins; moderators remain read-only. Cross-plugin settings are not yet available until each owner supplies a validated adapter.
