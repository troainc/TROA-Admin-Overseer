# Release Index

TROA Admin Overseer releases are single-DLL Torch packages. Every listed package is validated to contain only `Overseer.dll` and `manifest.xml`.

## Current feature releases

| Version | Release | Highlights |
|---|---|---|
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