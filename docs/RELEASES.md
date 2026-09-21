## v0.8.13 — Advanced Rewards and Limits
- Opt-in daily streak milestones and configurable player near-limit indicators.
- ZIP validated: only `Overseer.dll` and `manifest.xml`.

## v0.8.12 — Configurable Ticket Portal
- `TicketPortalUrlTemplate` and `!ov ticket` support portal links with `{player}`, `{steamid}`, and `{server}` placeholders.
- ZIP validated: only `Overseer.dll` and `manifest.xml`.

## v0.8.11 — Owner Documentation and Access Guard
- `!ova help` now requires administrator access.
- Rebuilt all owner-facing guides: README, commands, configuration, webhooks, deployment, roadmap, and changelog.
- ZIP validated: only `Overseer.dll` and `manifest.xml`.

## v0.8.10 — Release Readiness Validation
- Automated package validator verifies version alignment and exactly two ZIP entries.
- Added deployment checklist and repository context files.

## v0.8.9 — Safe Legacy Command Migration
- Legacy `!ov` admin spellings only redirect to canonical `!ova` commands; no privileged behavior is exposed through the old root.
- ZIP contains only `Overseer.dll` and `manifest.xml`.

## v0.8.8 — Player GPS and Reward History
- `!ova gps <player>` for online player coordinates and `!ov rewards` for personal claim history.
- ZIP contains only `Overseer.dll` and `manifest.xml`.

## v0.8.7 — Durable Audit History
- Persists recent emitted events and provides `!ova audit [count]` for administrator review.
- Audit history is capped at 5,000 newest entries; ZIP contains only `Overseer.dll` and `manifest.xml`.

## v0.8.6 — Command Contract Completion
- `!ov claim` is registered; public MOTD, daily, vote, and claim are no longer duplicated under `!ova`.
- Corrected root references in owner documentation.
- ZIP contains only `Overseer.dll` and `manifest.xml`.

## v0.8.5 — Config Naming and Migration
- Master config remains `TROA Admin Overseer.cfg`; all supplementary configs are now consistently prefixed.
- Legacy generic config files are copied once to preserve existing settings.
- ZIP contains only `Overseer.dll` and `manifest.xml`.

## v0.8.4 — Owner Operations
- Owner `!ova save` uses the supported Torch save API.
- Owner announcement scheduler controls persist in `Broadcast.cfg`; no restart or cleanup control added.
- ZIP contains only `Overseer.dll` and `manifest.xml`.

## v0.8.3 — Moderation Workflows
- `!ov report` for players; `!ova` staff commands for reports, resolution, warnings, and notes.
- Warnings, notes, and reports persist in managed JSON; escalation is disabled by default.
- ZIP contains only `Overseer.dll` and `manifest.xml`.

## v0.8.2 — Managed JSON Persistence
- Persists player profiles, sessions, bans, roles, role assignments, and reward claims to `Instance/TROA Admin Overseer/Overseer.json`.
- Debounced background writes; ZIP contains only `Overseer.dll` and `manifest.xml`.

## v0.8.1 — Safe Grid Targeting
- Look-at targeting for `!ova fixship`, `!ova stop`, and `!ova gridtransfer`.
- Ownership transfers require a 30-second `!ova confirm` preview.
- No grid deletion command; GridVault and TROA-Hangar own archival workflows.
- ZIP contains only `Overseer.dll` and `manifest.xml`.

# TROA Admin Overseer release index

Archives are retained for traceability. Deploy the newest package unless you are intentionally testing an older version.

| File | Bytes | SHA-256 |
|---|---:|---|
| TROA Admin Overseer v0.7.1 - Legacy Native SQLite Package.zip | 1969344 | `C4BE759669051A4F3EAF07453C8DB0753C48500F6CF499D6E91BD4FDF005908D` |
| TROA Admin Overseer v0.7.1 - Managed Package Loader Fix.zip | 54380 | `27C66489064B478A47919CE4E6229FAFDDDA5D584CB4FA3E26E3E12496F8F181` |
| TROA Admin Overseer v0.7.2 - Harmony Dependency Removal.zip | 53520 | `5629DF6572A0DB408B843AABB4ED0BCD637A84A8C4FB488D699CC641EB05F39D` |
| TROA Admin Overseer v0.7.3 - Managed SQLite Dependency.zip | 215048 | `6F1B7568867383E4A72ECB5CA8BB5AB0EB4F7CF49C2EDAB5D931D69226E6979A` |
