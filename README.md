# TROA Admin Overseer

Current release: **v0.8.56**. Rewards include a named bundle catalog that Overseer fills with registered vanilla and modded physical items while preserving owner edits, configurable daily/playtime/travel milestones, player progress, and offline admin-grant queuing. Players use `!ov rewards progress`; admins use `!ova rewards list`, `!ova rewards preview <rewardId>`, and `!ova rewards grant <player> <rewardId>`. Vote claims, reward data, and reward commands remain owned by Admin Overseer. Owner-only `!ova restart` waits for a successful world save, then announces 60, 30, 10, 5, 4, 3, 2, and 1 seconds remaining in global game chat and through the configured Server webhook route. Torch restarts 60 seconds after the save completes. On the next qualifying startup, it logs “Restart and Save were successful.” in green where Torch's console honors ANSI colors and sends a green success embed through the configured Server webhook route. Failed, timed-out, or already-running saves cancel the restart.

> A single-DLL Torch administration and server-operations plugin for Space Engineers dedicated servers.

TROA Admin Overseer gives server owners one clear place for player support, moderation, staff cases, roles, safe grid tools, events, rewards, auditing, and webhooks.

Admin Overseer owns its command behavior, reward data, and configured webhook routes. Monitor+ can transport Discord `!ov` and `!ova` commands to Torch and return their replies; it does not take over or re-post Admin Overseer's webhook events. Econ+ owns balance commands, while GridVault owns grid backups and recovery.

The current version is **v0.8.56**. See the [release index](docs/RELEASES.md) for version summaries and package contents. Version 0.8.52 explains how to fix malformed webhook routes; v0.8.51 repairs raw ampersands in Webhooks and Rewards XML URL values. See the [full configuration sample set](#full-configuration-examples).

## What it does

| Area | Included |
|---|---|
| Player support | MOTD, ticket link, reports, daily/playtime rewards, vote claims, reward history, limits feedback, owned-grid recovery |
| Staff operations | Player dossiers, moderation, cases, roles, permissions, grid tools, audit history |
| Owner operations | Config reload, save, save-confirmed delayed restart, maintenance status, announcements, scheduled summaries, exports |
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
- `!ova restart` — wait for a successful Torch save, pause for 60 seconds, then request restart. A failed, timed-out, or already-running save cancels the restart.

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
Edit the TROA-prefixed file in the plugin's `StoragePath` shown in the startup log. XML URL query separators should be `&amp;`; v0.8.51 repairs bare ampersands automatically without resetting the route.

For scheduled summaries, set `OperationsSummaryEnabled=true` and `OperationsSummaryIntervalHours` to `1–168`. Summaries flow through the Audit webhook route.

## Full configuration examples

The public repository includes a complete, secret-free sample for every current configuration file. Copy the files you need into Overseer's plugin `StoragePath` and remove the `.example` suffix. Review all settings before use. Private keys, tokens, webhook URLs, channel IDs, and account IDs are blank or placeholders; replace them privately and keep completed configs out of public repositories. Reward integrations, limits, and webhooks are disabled in the samples. Review connection privacy settings before enabling IP or geolocation features.

- [Master](TROA%20Admin%20Overseer.cfg.example) · [Webhooks](TROA%20Admin%20Overseer%20Webhooks.cfg.example) · [Moderation](TROA%20Admin%20Overseer%20Moderation.cfg.example) · [Broadcast](TROA%20Admin%20Overseer%20Broadcast.cfg.example)
- [Rewards](TROA%20Admin%20Overseer%20Rewards.cfg.example) · [Limits](TROA%20Admin%20Overseer%20Limits.cfg.example) · [Connections](TROA%20Admin%20Overseer%20Connections.cfg.example) · [Audit](TROA%20Admin%20Overseer%20Audit.cfg.example)
## Configuration files

- `TROA Admin Overseer.cfg` — server identity, safety, maintenance, policy, summaries.
- `TROA Admin Overseer Webhooks.cfg` — Discord routes.
- `TROA Admin Overseer Moderation.cfg` — warning escalation and moderation defaults.
- `TROA Admin Overseer Broadcast.cfg` — MOTD and announcements.
- `TROA Admin Overseer Rewards.cfg` — rewards and vote integration.
- `TROA Admin Overseer Limits.cfg` — block limits.
- `TROA Admin Overseer Connections.cfg` — session/network history settings.
- `TROA Admin Overseer Audit.cfg` — audit controls.

### Rewards catalog and Monitor+ migration

Admin Overseer owns voting and rewards. The reward catalog at `Instance/TROA Admin Overseer/Rewards/Rewards.csv` is populated on startup with registered vanilla and modded physical items. Existing owner-authored rows and bundles are preserved; new server definitions are appended without replacing custom amounts or names. Repeat a `RewardId` across rows to make a multi-item bundle. Players use `!ov daily`, `!ov vote`, `!ov claim`,
`!ov rewards`, `!ov rewards progress`, and `!ov topvoters`; admins can browse, preview, and grant catalog bundles with `!ova rewards list`, `!ova rewards preview <rewardId>`, and `!ova rewards grant <player> <rewardId>`. Offline grants stay queued until the player is online. Linked Discord
users can reserve a vote reward with `!reward` in the configured channel or `/adminoverseer reward`,
then claim it in-game using `!ov claim`. Discord also provides `!votelink`, `!topvoters`, and
matching `/adminoverseer` slash commands. Discord reward replies are branded TROA Admin Overseer.

To migrate Monitor+ reservations and voter history, start Overseer once to create its Rewards config,
stop Torch, set `LegacyMonitorStorageDirectory` to the Monitor+ plugin storage directory, review the
`VoteReward` item bundle, then start a game session and confirm the import count in the Overseer log
before removing old Monitor+ reward files. The import is repeat-safe; imported pending claims use the
configured Overseer bundle. Monitor+ v1.1.5K8 retains account linking and becomes the Discord command
transport: it forwards owner-plugin commands and returns their replies while leaving each plugin's
features and webhook delivery with its owner. Econ+ owns economy and balance; GridVault owns grid
backup and recovery.

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

### Automatic block catalogue

After each server start or restart, the plugin writes `Instance/TROA Admin Overseer/data/block-subtypes.csv`. It lists every registered vanilla and mod block subtype plus live-use columns, so owners can prepare context-specific limits without memorising subtype IDs. `!ova limit exportcsv` refreshes it on demand.

## Documentation

Use [`docs/DEPLOYMENT.md`](docs/DEPLOYMENT.md) for installation, [`docs/CONFIGURATION.md`](docs/CONFIGURATION.md) and the full configuration samples for setup, [`docs/COMMANDS.md`](docs/COMMANDS.md) for commands, [`docs/PERMISSIONS.md`](docs/PERMISSIONS.md) for access, and [`docs/WEBHOOKS.md`](docs/WEBHOOKS.md) for webhook routing. The release index and README describe current feature/version boundaries.
