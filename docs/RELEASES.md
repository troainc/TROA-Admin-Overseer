# Release Index

TROA Admin Overseer releases are single-DLL Torch packages containing only Overseer.dll and manifest.xml. This public repository carries release notes and operator documentation.

## Current feature releases

Current release: **v0.8.96**. Bifrost maps Linux-online logical processors by physical core where topology is available and distinguishes host inventory from the subset allocated to Torch. The page offers selectable CPU tiles, preview, and an advanced hexadecimal mask editor. The package built with 0 warnings/errors and passed local verification (258530 bytes; SHA-256 EBA847895740BF2AB2FDBA919987EB472EEC43D1424A7C9E4F652DC8CFF13F22). Linux/Wine browser rendering and Profiler+ A/B acceptance remain operator-side.

| Version | Release | Highlights |
|---|---|---|
| v0.8.96 | CPU Topology Map and Affinity Picker | Full online logical CPU map; physical-core/socket groups; Torch allocation highlighted separately; selection picker; advanced mask; fixed confirmation flow. |
| v0.8.95 | Host-bounded Core Controller and Bifrost workspace | Owner-only multi-logical-CPU affinity bounded by Linux/AMP allocation; preview, verified apply, rollback, startup restore. |
| v0.8.93 | Scheduled Restart Coordination | Four-hour cadence; owner restart controls; Cleaner+ deep-clean handoff; save-confirmed countdown/restart. |
| v0.8.60 | Bifrost TROA plugin workspaces | Settings Save/Reload through recognized owning-plugin APIs, TROA-only list, live plugin workspaces, searchable command catalog/console, and public webserver config sample. Build and package are documented; runtime acceptance is tracked separately. |
| v0.8.59 | Bifrost Panel webserver (superseded release) | Local package built and verified with the full webserver config example; dedicated Torch runtime acceptance pending.  |
| v0.8.55 | Restart Countdown | Announces restart timing in global game chat and through the configured Server webhook after a confirmed save. Build: 0 warnings/errors; ZIP verified; dedicated-server runtime acceptance pending. |
| v0.8.54 | Restart and Save Confirmation | On the next qualifying startup after `!ova restart`, logs and sends a green success confirmation. Build: 0 warnings/errors; ZIP verified; dedicated-server runtime acceptance pending. |
| v0.8.53 | Save-Confirmed Delayed Restart | Owner-only `!ova restart` waits for a successful save, then waits 60 seconds before restarting Torch. Build: 0 warnings/errors; ZIP verified; dedicated-server runtime acceptance pending. |
| v0.8.52 | Clear Webhook Config Errors | Logs actionable instructions when the Webhooks XML is malformed. |
| v0.8.51 | XML Configuration Repair | Repairs unescaped URL ampersands and ensures configured Webhooks routes and Rewards lists replace defaults. |
| v0.8.50 | Consolidated Discord Vote Rewards | Discord vote reservations, persistent claims/history, voter leaderboard, and repeat-safe Monitor+ migration. |
| v0.8.49 | Automatic Block Catalogue | Complete vanilla-and-mod subtype CSV refreshed at every server startup in the plugin data folder. |
| v0.8.46 | Scheduled Operations Summary | Opt-in audit/webhook summaries every 1–168 hours. |
| v0.8.45 | Maintenance Mode | Persisted maintenance status and visible banner. |
| v0.8.44 | Event MOTD | Separate expiring event MOTD override. |
| v0.8.43–v0.8.40 | Event Operations | Event rewards, participant check-ins, announcements, and temporary roles. |
| v0.8.39–v0.8.38 | Faction Read Views | Read-only faction dossier and roster. |
| v0.8.37 | Operations Summary | Manual recent audit summary. |
| v0.8.36 | Role Comparison | Read-only role rank/node/inheritance comparison. |
| v0.8.35 | Policy Enforcement | Opt-in custom-node gates for sensitive actions. |
| v0.8.34–v0.8.33 | Staff Cases | Queue, assignment, deadlines, timelines, and internal updates. |
| v0.8.32–v0.8.31 | Two-Staff Transfers | Optional distinct-admin approval workflow. |
| v0.8.30–v0.8.16 | Core Operations | Policy, roles, limits, moderation audit, player recovery, and durable JSON storage. |

## Install

1. Stop Torch.
2. Remove every older TROA Admin Overseer ZIP from the plugin directory.
3. Install exactly one newest ZIP.
4. Start Torch and verify a fresh load log.

See the project [changelog](../CHANGELOG.md) for detailed historical notes.
