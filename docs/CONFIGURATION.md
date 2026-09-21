# Configuration guide

All owner configuration lives beside the normal server configuration files. Start Torch once to create missing files, edit the **TROA Admin Overseer-prefixed** files, then run `!ova reload`.

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

## Master config

Set `ServerName` to the branding you want players to see. It does not rename the plugin, release package, data folder, or configuration files.

Set `TicketPortalUrlTemplate` to your ticket-site URL. It can include `{player}`, `{steamid}`, and `{server}` and is shown by `!ov ticket`.

Use `Modules` only when you want an entire feature area off. Missing module switches remain available by default.

### Player grid recovery

`PlayerGridToolsEnabled` controls player `!ov fixship`, `!ov stop`, and `!ov gridcheck` (default `true`). `PlayerGridToolsCooldownMinutes` defaults to `10`; set `0` to disable the cooldown. `PlayerGridToolsMaxPcu` defaults to `20000` PCU across the complete mechanical group; set `0` to disable this plugin-specific PCU cap. These commands always require the player to be a major owner of every connected grid, cannot target by name or from console, and emit GridTools audit/webhook events.

## Rewards: streak milestones

Rewards remain disabled until `Enabled` is set to true. To add a streak bonus, set `DailyStreakEnabled` to true, choose `DailyStreakMilestone` (for example `7`), and configure `DailyStreakReward`. A missed 48-hour window resets the streak; the normal daily cooldown still applies.

## Limits: player warning threshold

Set `PlayerNearLimitPercent` in `TROA Admin Overseer Limits.cfg` (default `80`). `!ov limits` marks player usage as NEAR at or above that percentage and OVER when it exceeds the rule maximum. This display setting does not enable enforcement.

### Context-aware block rules

Each rule can independently filter by `GridKind` (`Any`, `Ship`, or `Station`) and `GridSize` (`Any`, `Large`, or `Small`). This means the same subtype can have different limits in the same config. For example, use two `Grid`-scope rules matching the reactor subtype: one with `GridKind=Ship`, `GridSize=Large`, `Max=5`; another with `GridKind=Station`, `GridSize=Large`, `Max=10`. Rules do not replace one another—the appropriate contextual rule is counted and shown to players as, for example, `Large Ship` or `Large Station`.

Run `!ova limit exportcsv` as an owner to write `Instance/TROA Admin Overseer/exports/block-subtypes.csv`. It inventories fat-block subtype IDs currently present in the loaded world, with type, grid size, grid kind, and observed count. Use those exact subtype IDs when writing rules. The export never changes blocks or limits.

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
