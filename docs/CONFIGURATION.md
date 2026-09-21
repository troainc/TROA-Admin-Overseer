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

## Rewards: streak milestones

Rewards remain disabled until `Enabled` is set to true. To add a streak bonus, set `DailyStreakEnabled` to true, choose `DailyStreakMilestone` (for example `7`), and configure `DailyStreakReward`. A missed 48-hour window resets the streak; the normal daily cooldown still applies.

## Limits: player warning threshold

Set `PlayerNearLimitPercent` in `TROA Admin Overseer Limits.cfg` (default `80`). `!ov limits` marks player usage as NEAR at or above that percentage and OVER when it exceeds the rule maximum. This display setting does not enable enforcement.

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