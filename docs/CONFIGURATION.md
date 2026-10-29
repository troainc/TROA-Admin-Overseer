# Configuration guide

All owner configuration lives beside the normal server configuration files. Start Torch once to create missing files, edit the **TROA Admin Overseer-prefixed** files, then run `!ova reload`.

The active location is the plugin `StoragePath` printed at startup. XML URL query separators should be written as `&amp;`; v0.8.51 repairs bare ampersands and replaces initialized Webhooks/Rewards list defaults with the values from the file. If `.bad-*` backups continue to appear, inspect the matching startup log exception for the remaining XML syntax error.

To recover settings already reset by an older build, stop Torch and restore the desired `.bad-*` backup over its matching TROA-prefixed config file, then restart v0.8.51. Keep config backups private because they may contain credentials.

## Downloadable config samples

Secret-free examples for all nine configuration files are available in the repository root: [master](../TROA%20Admin%20Overseer.cfg.example), [webhooks](../TROA%20Admin%20Overseer%20Webhooks.cfg.example), [moderation](../TROA%20Admin%20Overseer%20Moderation.cfg.example), [broadcast](../TROA%20Admin%20Overseer%20Broadcast.cfg.example), [rewards](../TROA%20Admin%20Overseer%20Rewards.cfg.example), [limits](../TROA%20Admin%20Overseer%20Limits.cfg.example), [connections](../TROA%20Admin%20Overseer%20Connections.cfg.example), [audit](../TROA%20Admin%20Overseer%20Audit.cfg.example), and [webserver](../TROA%20Admin%20Overseer%20Webserver.cfg.example). Remove `.example` when copying into plugin storage. Replace placeholders privately; never publish real tokens, IDs, or webhook URLs.
## Files

| File | Purpose | Safe default |
|---|---|---|
| `TROA Admin Overseer.cfg` | Server name and module switches | Modules available |
| `TROA Admin Overseer Webhooks.cfg` | Discord delivery and routes | Disabled |
| `TROA Admin Overseer Moderation.cfg` | Ban sweep, appeal link, warning escalation | Escalation off |
| `TROA Admin Overseer Broadcast.cfg` | MOTD and rotating announcements | Announcements off |
| `TROA Admin Overseer Rewards.cfg` | Daily, vote, and playtime rewards | Disabled |
| `TROA Admin Overseer Limits.cfg` | Scan-based block limits | Disabled |
| `TROA Admin Overseer Connections.cfg` | Join history and optional IP/geo lookups | Review privacy settings |
| `TROA Admin Overseer Audit.cfg` | Command/chat auditing | Command auditing on; chat off |
| `TROA Admin Overseer Webserver.cfg` | Bifrost Panel web server | Loopback only; port 18750 |

## Master config

Set `ServerName` to the branding you want players to see. It does not rename the plugin, release package, data folder, or configuration files.

Set `TicketPortalUrlTemplate` to your ticket-site URL. It can include `{player}`, `{steamid}`, and `{server}` and is shown by `!ov ticket`.

Use `Modules` only when you want an entire feature area off. Missing module switches remain available by default.

Set RequireSecondStaffApprovalForTransfers to `true` when grid ownership transfers need two staff members. The requester creates the preview with !ova gridtransfer; a different administrator must use !ova approve <requesterSteamId> within 30 seconds. This is off by default, which retains !ova confirm for the requesting administrator.

### Player grid recovery

`PlayerGridToolsEnabled` controls player `!ov fixship`, `!ov stop`, and `!ov gridcheck` (default `true`). `PlayerGridToolsCooldownMinutes` defaults to `10`; set `0` to disable the cooldown. `PlayerGridToolsMaxPcu` defaults to `20000` PCU across the complete mechanical group; set `0` to disable this plugin-specific PCU cap. These commands always require the player to be a major owner of every connected grid, cannot target by name or from console, and emit GridTools audit/webhook events.

## Rewards: streak milestones

Rewards remain disabled until `Enabled` is set to true. To add a streak bonus, set `DailyStreakEnabled` to true, choose `DailyStreakMilestone` (for example `7`), and configure `DailyStreakReward`. A missed 48-hour window resets the streak; the normal daily cooldown still applies.

## Rewards: Discord voting and Monitor+ migration

In `TROA Admin Overseer Rewards.cfg`, configure `VoteSiteEnabled` and `SpaceEngineersComApiKey` for
vote claims, plus `VoteReward` for the item bundle. `VoteLeaderboardEnabled` and
`VoteLeaderboardCount` control `!ov topvoters`. For Discord reservations, set
`DiscordRewardsEnabled`, `DiscordBotToken`, `DiscordCommandChannelId`, and
`DiscordSteamMappings` (`discord-user-id:steam-id-64`). `DiscordCommandPrefix` defaults to `!` and
`DiscordReconnectDelaySeconds` defaults to `5`. Keep the bot token private.

To migrate existing Monitor+ data, start Torch once with Admin Overseer installed to create the
Rewards config, stop Torch, set `LegacyMonitorStorageDirectory` to Monitor+'s plugin storage folder,
and review `VoteReward`. Start a game session with both plugins' data folders present and check the
Overseer log for the import count before removing Monitor+. Overseer imports pending reward IDs,
voter history, and compatible vote/Discord settings once per source directory; it leaves the old
files intact. Imported pending rewards use the configured Overseer item bundle.

## Limits: player warning threshold

Set `PlayerNearLimitPercent` in `TROA Admin Overseer Limits.cfg` (default `80`). `!ov limits` marks player usage as NEAR at or above that percentage and OVER when it exceeds the rule maximum. This display setting does not enable enforcement.

### Context-aware block rules

Each rule can independently filter by `GridKind` (`Any`, `Ship`, or `Station`) and `GridSize` (`Any`, `Large`, or `Small`). This means the same subtype can have different limits in the same config. For example, use two `Grid`-scope rules matching the reactor subtype: one with `GridKind=Ship`, `GridSize=Large`, `Max=5`; another with `GridKind=Station`, `GridSize=Large`, `Max=10`. Rules do not replace one another—the appropriate contextual rule is counted and shown to players as, for example, `Large Ship` or `Large Station`.

The downloadable limits sample is an alert-only starter policy for thrusters, gyros, jump drives, reactors, batteries, drills, grinders, welders, programmable blocks, timers, assemblers, refineries, gravity generators, projectors, sensors, pistons, rotors/hinges, controllable guns, and TierTech accelerated welder families. It remains disabled (`Enabled=false`) until you opt in. Its `Player` scope counts blocks by block owner across that owner's grids; unowned blocks cannot be attributed to a player. Review and adjust the caps for your server before enabling it.

`Match` accepts an exact subtype ID, a subtype prefix ending in `*`, or a block TypeId with or without the `MyObjectBuilder_` prefix. TypeId matches also cover mod blocks built on the same standard block type. For mod blocks with custom TypeIds, read `SubtypeId` and `TypeId` in `block-subtypes.csv`, then add an exact subtype or family-prefix rule. The catalog includes installed mod definitions; no fixed example can anticipate every mod or its naming scheme. Overlapping rules are independent caps, so keep both broad TypeId and narrower contextual rules only when you want both constraints to apply.

After every server start or restart, TROA Admin Overseer automatically writes `Instance/TROA Admin Overseer/data/block-subtypes.csv`. It inventories every registered vanilla-and-mod cube-block subtype, with type and cube size. Live-world columns show total observed use plus ship and station use, while unbuilt definitions remain present with zeroes. Use `!ova limit exportcsv` for an immediate refresh; the export never changes blocks or limits.

## Configuration doctor

Run `!ova doctor` after your first setup and any larger config change. It checks the server name, webhook routes, reward/streak setup, limit rules, ticket URL, and retained legacy config files. It is read-only and never enables a feature for you.

## Safe enablement order

1. Confirm `!ova status` works.
2. Configure one webhook route and test it.
3. Enable rewards only after setting reward items and, for vote claims, the API key.
4. Enable limits only after reviewing every rule and punishment.
5. Enable warning escalation only after choosing a threshold and duration.
6. Enable announcements only after reviewing message text and interval.

## Legacy filenames

On first load, an old generic file such as `Broadcast.cfg` is copied to `TROA Admin Overseer Broadcast.cfg`. The old file is not deleted. After migration, edit only the prefixed file.

## Data

Operational records are stored separately in `Instance/TROA Admin Overseer/Overseer.json`. Back it up with your normal server instance data. Do not edit it while Torch is running.
### Live rule preview

Use !ova limit preview [grid] to verify the exact active Grid-scope rules, context, count, cap, and action for a targeted grid. Players can run !ov limitcheck on a wholly major-owned grid under their crosshair. Both are read-only: they never alter blocks or invoke enforcement.

## Bifrost Panel webserver (v0.8.58 release)

`TROA Admin Overseer Webserver.cfg` is generated beside the other Overseer configs. `BindAddress` accepts an IP literal: `127.0.0.1` keeps access on the Torch host, a specific server IPv4 binds one interface, and `0.0.0.0` listens on all IPv4 interfaces. Set `PublicUrl` to the browser-facing address or domain; DNS must point to the server. The embedded listener uses HTTP, so use an HTTPS reverse proxy for secure domain access. All panel APIs require sign-in. On first start, create the owner account using the one-time code at `TROA Admin Overseer/BifrostPanel/OwnerSetupCode.txt` under the plugin `StoragePath`. The owner can create/remove individual Admin and Moderator accounts. Password hashes are salted PBKDF2; sessions are held in memory for 12 hours. Open the green ready URL after the game session loads. Use `!ova reload` after changing this config. Current panel features are live status and account management; each plugin must implement its own validated adapter before panel-based config Save/Reload is available.
