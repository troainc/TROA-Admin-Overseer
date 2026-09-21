# TROA Admin Overseer

> A single-DLL Torch administration and server-operations plugin for Space Engineers dedicated servers.

TROA Admin Overseer gives server owners one clear place for player support, moderation, staff cases, roles, safe grid tools, events, rewards, auditing, and webhooks.

## What it does

| Area | Included |
|---|---|
| Player support | MOTD, ticket link, reports, daily/vote rewards, limits feedback, owned-grid recovery |
| Staff operations | Player dossiers, moderation, cases, roles, permissions, grid tools, audit history |
| Owner operations | Config reload, save, maintenance status, announcements, scheduled summaries, exports |
| Events | Event roles, announcements, temporary MOTD, check-ins, rewards, attendee export |

It deliberately does **not** delete grids, manage GridVault/Hangar storage, perform Cleaner+ cleanup/restarts, or bundle native/third-party DLLs.

## Install or upgrade

1. Stop the Torch server.
2. In the server `Plugins` folder, remove every older TROA Admin Overseer ZIP.
3. Install exactly one newest `TROA Admin Overseer v… .zip`.
4. Start Torch. The ZIP contains only `Overseer.dll` and `manifest.xml`.
5. Confirm the startup log says **TROA Admin Overseer** loaded without dependency warnings.
6. Run `!ova status` in-game or from the Torch console.

> Keep the JSON data folder in backups: `Instance/TROA Admin Overseer/Overseer.json`.

## Command roots

| Root | Who uses it | Purpose |
|---|---|---|
| `!ov` | Players | Safe self-service and support commands only |
| `!ova` | Admins and owners | Moderation, staff, grid, configuration, and owner operations |

`!ov` never performs an admin action. Old admin-style `!ov` commands only redirect to their `!ova` equivalent.

## First-time owner setup

The master config is `TROA Admin Overseer.cfg`, beside your other server `.cfg` files.

1. Set `ServerName`.
2. Set `TicketPortalUrlTemplate` if you have a support website. It accepts `{player}`, `{steamid}`, and `{server}`.
3. Keep webhooks, rewards, limits, announcements, policy enforcement, and scheduled summaries disabled until configured.
4. Run `!ova doctor` after any major configuration change.
5. Run `!ova reload` after editing config files.

### Recommended first commands

- `!ova status` — plugin and module health.
- `!ova doctor` — read-only configuration checks.
- `!ova audit 20` — latest recorded actions.
- `!ova opssummary 100` — operational totals by category.
- `!ova maintenance on <message>` — show a persisted maintenance banner.
- `!ova save` — request a Torch save.

## Everyday workflows

### Staff cases

- `!ova reports` / `!ova reportqueue` — open report work.
- `!ova reportassign <id> [staff]` — assign or hand off a case.
- `!ova reportstatus <id> <open|investigating|waiting>` — update workflow state.
- `!ova reportdue <id> <hours|clear>` — set a deadline.
- `!ova reportupdate <id> <text>` / `!ova reporttimeline <id>` — internal staff record.
- `!ova case <player>` — player moderation context.

### Roles and permissions

- `!ova role template list|preview|apply` — create safe starting roles.
- `!ova role assign <player> <role>` — assign a durable role.
- `!ova role temporary <player> <role> <duration>` — automatically expiring role.
- `!ova role diff <roleA> <roleB>` — compare rank, nodes, and inheritance.
- `!ova perms check <player> <node>` — explain access.

Set `EnforceCustomPermissions=true` only after reviewing role assignments. It adds TROA policy nodes on top of native Torch permissions; it is off by default.

### Grid safety

Admins can look at a grid and use `!ova gridcheck`, `!ova fixship`, and `!ova stop`. Ownership transfer always starts as a preview with `!ova gridtransfer`.

Set `RequireSecondStaffApprovalForTransfers=true` to require a different administrator to use `!ova approve <requesterSteamId>`; the requester cannot use `!ova confirm` while it is enabled.

Players can use `!ov fixship`, `!ov stop`, and `!ov gridcheck` only on wholly major-owned mechanical groups, subject to the configured cooldown and PCU cap.

### Events

- `!ova event role <player> <role> <duration>`
- `!ova event announce <message>`
- `!ova event motd <hours> <message>` or `clear`
- `!ova event checkin <player> <eventId>`
- `!ova event attendees <eventId>` / `!ova event export <eventId>`
- `!ova event reward <player>`

### Webhooks and operations summaries

Webhook routes are closed by default. Add a valid URL, set its route `Enabled=true`, then run `!ova reload`.

For scheduled summaries, set `OperationsSummaryEnabled=true` and `OperationsSummaryIntervalHours` to `1–168`. Summaries flow through the Audit webhook route.

## Configuration files

- `TROA Admin Overseer.cfg` — server identity, safety, maintenance, policy, summaries.
- `TROA Admin Overseer Webhooks.cfg` — Discord routes.
- `TROA Admin Overseer Moderation.cfg` — warning escalation and moderation defaults.
- `TROA Admin Overseer Broadcast.cfg` — MOTD and announcements.
- `TROA Admin Overseer Rewards.cfg` — rewards and vote integration.
- `TROA Admin Overseer Limits.cfg` — block limits.
- `TROA Admin Overseer Connections.cfg` — session/network history settings.
- `TROA Admin Overseer Audit.cfg` — audit controls.

## More documentation

- [Commands](docs/COMMANDS.md)
- [Configuration](docs/CONFIGURATION.md)
- [Roles and permissions](docs/PERMISSIONS.md)
- [Webhooks](docs/WEBHOOKS.md)
- [Deployment verification](docs/DEPLOYMENT.md)
- [Release index](docs/RELEASES.md)
- [Changelog](CHANGELOG.md)

## Live acceptance checklist

After install, verify a fresh Torch log and test `!ov help`, `!ova status`, player-owned `!ov gridcheck`, staff `!ova reportqueue`, and `!ova audit`.

### Automatic block catalogue`r`n`r`nAfter each server start or restart, the plugin writes `Instance/TROA Admin Overseer/data/block-subtypes.csv`. It lists every registered vanilla and mod block subtype plus live-use columns, so owners can prepare context-specific limits without memorising subtype IDs. `!ova limit exportcsv` refreshes it on demand.
