# Project context

TROA Admin Overseer is a clean-room Torch administrative plugin for Space Engineers. Public product name and data path are `TROA Admin Overseer`; server owners choose `ServerName` only for branding. It is a single managed-DLL plugin with JSON persistence under `Instance/TROA Admin Overseer/Overseer.json`.

Current command contract: `!ov` for player-safe commands and `!ova` for privileged commands. Legacy `!ov` admin spellings are redirects only.
Current staff workflow includes !ova case <player> for moderation context and !ova caseevents <player> [count] for player-specific persisted audit events.

Moderation audit events use stable target SteamIDs for case-history correlation; display names are never the matching key.
