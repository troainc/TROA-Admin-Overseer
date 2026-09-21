# Project context

TROA Admin Overseer is a clean-room Torch administrative plugin for Space Engineers. Public product name and data path are `TROA Admin Overseer`; server owners choose `ServerName` only for branding. It is a single managed-DLL plugin with JSON persistence under `Instance/TROA Admin Overseer/Overseer.json`.

Current command contract: `!ov` for player-safe commands and `!ova` for privileged commands. Legacy `!ov` admin spellings are redirects only.
Current staff workflow includes !ova case <player> for moderation context and !ova caseevents <player> [count] for player-specific persisted audit events.

Moderation audit events use stable target SteamIDs for case-history correlation; display names are never the matching key.

Player-report submissions and resolutions are both SteamID-correlated in the persisted audit trail.

Player self-service grid recovery is available under !ov fixship, !ov stop, and !ov gridcheck; it is limited to an in-game caller's wholly major-owned mechanical group and master-config limits.

Player grid recovery uses the owner-configurable `PlayerGridToolsMaxPcu` master-config limit (default 20000 PCU; 0 disables the additional plugin cap).
Advanced roles support durable parent-role inheritance with cycle protection. Effective Torch rank and custom permission nodes resolve across direct and inherited roles; `!ova perms check` explains node grants.
Temporary direct roles persist in JSON and expire every 30 seconds through the roles module; expiry removes the role, reapplies effective native rank, and emits an audit event.
Role records now retain safe presentation labels and owner-managed Discord role-ID mappings. This plugin stores no Discord token and never auto-grants access from a Discord mapping without an authenticated identity bridge.
Limits now support independent ship/station and large/small context filters for the same subtype. Owners export observed current-world subtype IDs with !ova limit exportcsv; player !ov limits feedback names the applying context.
Live limit previews: !ova limit preview [grid] is admin read-only; !ov limitcheck is player-safe and requires whole-group major ownership.
The owner CSV export now lists every registered cube-block definition, including unbuilt definitions, alongside live total/ship/station usage counts.
Role templates now provide previewable, non-overwriting standard ranks; review generated roles before assignment.
Scoped permission grants now support faction, player, gridtag, and category policies with explainable simulation.
Public v0.8.31/v0.8.32 documentation records optional, enforced second-staff approval for grid ownership transfers without exposing private source.

Public v0.8.33 guidance documents durable report assignment, status, deadline, and internal update workflows.
2026-09-21: Rebuilt public README as a server-owner how-to and consolidated the changelog by date.