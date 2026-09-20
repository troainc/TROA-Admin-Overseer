# Overseer Configuration

All configuration lives in XML files under `<Torch>/Instance/Overseer/`. Files are created with
sensible defaults on first run. Edit them on disk and apply changes without a restart with
`!ov reload`. A malformed file is backed up (`*.bad-<ticks>`) and replaced with defaults.

> **Secrets:** webhook URLs and API keys live in these files. They are excluded from git via
> `.gitignore` (`Instance/`, `*.cfg`). Never commit them.

## Overseer.cfg (root)
| Field | Default | Meaning |
|---|---|---|
| `ServerName` | `My Space Engineers Server` | Shown in status and webhook footers. |
| `CommandRoot` | `ov` | Command root (used after Torch's `!`). |
| `Modules` | (all enabled) | Per-module `<ModuleToggle Id="..." Enabled="true/false"/>`. Missing entries default to enabled. Module ids: `diagnostics`, `audit`, `connections`, `moderation`, `broadcast`, `limits`, `rewards`. |

## Webhooks.cfg
| Field | Default | Meaning |
|---|---|---|
| `Enabled` | `false` | Master switch for all webhook delivery. |
| `Routes` | 8 named routes | Each `<WebhookRoute Name="...">` has `Url`, `Enabled`, and `CriticalMentionRoleId`. |
| `Mappings` | see below | `<CategoryRoute Category="..." Route="..."/>` — points an event category at a route. Empty route = muted. |

**Default routes:** `audit`, `moderation`, `joins`, `performance`, `rewards`, `limits`, `server`,
`critical`. **Event categories:** `Server`, `Audit`, `Connections`, `Moderation`, `PlayerTools`,
`GridTools`, `Limits`, `Performance`, `Rewards`, `Broadcast`.

To start: set `Enabled` to `true`, paste a Discord webhook URL into one or more routes, and set
`CriticalMentionRoleId` to a Discord role id to ping on critical events (bans, alerts). See
[WEBHOOKS.md](WEBHOOKS.md) for the full walkthrough.

## Audit.cfg
| Field | Default | Meaning |
|---|---|---|
| `LogCommands` | `true` | Log chat commands (messages starting with the prefix). |
| `LogChat` | `false` | Log ordinary chat messages (noisy). |
| `LogModerationEvents` | `true` | Log kicks, bans, and promotions. |
| `CommandPrefix` | `!` | Prefix used to identify commands. |

## Connections.cfg
| Field | Default | Meaning |
|---|---|---|
| `AnnounceJoinLeave` | `true` | Emit join/leave events. |
| `CaptureIp` | `true` | Capture player IP via Steam P2P session state. |
| `GeoLookup` | `true` | Resolve captured IPs to country/ISP (ip-api.com). |
| `AltDetection` | `true` | Flag accounts sharing an IP. |
| `WatchlistAlerts` | `true` | Critical alert when a watchlisted SteamID connects. |
| `Watchlist` | empty | List of `<unsignedLong>` SteamIDs to watch. |

> **IP note:** capture uses Steam's P2P session state, which yields a public IP for direct P2P
> connections. When Steam routes a client through its relay/SDR there is no public IP, so geo and
> alt-detection stay idle for that session. Everything else works regardless.

## Moderation.cfg
| Field | Default | Meaning |
|---|---|---|
| `UnbanSweepSeconds` | `60` | How often to check for and lift expired temporary bans (min 15). |
| `AppealUrlTemplate` | empty | Appeal link included in ban embeds; use `{id}` for the appeal id. |
| `DefaultKickReason` | `Kicked by an administrator` | Used when `!ov kick` has no reason. |

## Broadcast.cfg
| Field | Default | Meaning |
|---|---|---|
| `Author` | `Server` | Name shown as the sender of MOTD/announcements/broadcasts. |
| `Font` | `Blue` | Message color name (White, Red, Green, Blue, Yellow, Orange, Cyan, Purple, Pink, Gray). |
| `MotdEnabled` | `true` | Show the MOTD when a player joins. |
| `MotdDelaySeconds` | `5` | Delay after join before showing the MOTD (lets the client load). |
| `MotdLines` | 2 lines | Lines to show. Placeholders `{player}`, `{server}`. |
| `AnnouncementsEnabled` | `false` | Rotate announcements to everyone on a timer. |
| `AnnouncementIntervalSeconds` | `900` | Seconds between announcements (min 30). |
| `Announcements` | 2 lines | Messages to rotate through. |
| `JoinLeaveMessages` | `false` | Post in-game "X joined/left" chat lines (webhooks already cover this). |

## Limits.cfg
Scan-based block limits. **Disabled by default** so it never surprise-enforces.

| Field | Default | Meaning |
|---|---|---|
| `Enabled` | `false` | Master switch. |
| `ScanIntervalSeconds` | `600` | Seconds between scans (min 60). Scans run on the game thread — keep this high on large worlds. |
| `MaxAlertsPerScan` | `15` | Max violation events per scan before a summary line (anti-spam). |
| `Limits` | 1 example | List of `<LimitRule>`. |

Each `<LimitRule>`:

| Field | Meaning |
|---|---|
| `Name` | Friendly name shown in alerts and `!ov limits`. |
| `Match` | Block `SubtypeId` (e.g. `LargeBlockLargeThrust`), a `TypeId` (e.g. `Reactor` or `MyObjectBuilder_Reactor`), or `*` for all blocks. |
| `Scope` | `Player`, `Faction`, `Grid`, or `Global`. |
| `Max` | Allowed count within the scope. |
| `Punishment` | `Alert` (event/webhook only) or `TurnOff` (disable the excess functional blocks, then alert). |
| `ExemptRoles` | Roles whose members are exempt (Player scope). |
| `ExemptSteamIds` | SteamIDs exempt (Player scope). |

> Enforcement is scan-based (no placement hooks), so a violation is caught and acted on at the next
> scan rather than blocked at placement. `TurnOff` disables excess **functional** blocks only.

## Rewards.cfg
Item-bundle rewards. **Disabled by default.**

| Field | Default | Meaning |
|---|---|---|
| `Enabled` | `false` | Master switch. |
| `DailyEnabled` | `true` | Allow `!ov daily`. |
| `DailyCooldownHours` | `24` | Hours between daily claims. |
| `DailyReward` | 500 Iron ingots | Bundle of `<RewardItem>` for the daily. |
| `PlaytimeEnabled` | `false` | Auto-grant a bundle to online players on an interval. |
| `PlaytimeIntervalMinutes` | `60` | Minutes between playtime grants. |
| `PlaytimeReward` | 100 Iron ingots | Bundle for playtime grants. |
| `VoteSiteEnabled` | `false` | Enable space-engineers.com vote claiming (`!ov claim`). |
| `SpaceEngineersComApiKey` | empty | Your space-engineers.com server API key. |
| `VoteReward` | 1000 Iron ingots | Bundle granted on a confirmed vote claim. |
| `VoteLinks` | 1 example | URLs shown by `!ov vote` (your space-engineers.com server page). |

Each `<RewardItem>`: `TypeId` (e.g. `MyObjectBuilder_Ingot`, `MyObjectBuilder_Component`,
`MyObjectBuilder_Ore`, `MyObjectBuilder_PhysicalGunObject`), `SubtypeId` (e.g. `Iron`, `SteelPlate`,
`Construction`), and `Amount`. Items are added to the player's inventory, so they must be online.

**Voting** uses the [space-engineers.com API](https://space-engineers.com/help/api/): `!ov claim`
checks the player's SteamID for a vote in the last 24h and, when the site confirms the claim, grants
`VoteReward`. Get your key from your server's page on space-engineers.com. Economy/credit payouts are
not yet supported (item bundles only).

## Data
The SQLite database is `Instance/Overseer/Overseer.db`. If it cannot be created or loaded, the
plugin keeps running and events still reach logs and webhooks — only the database-backed features
(`lookup`, `alts`, `history`, `bans`, playtime) are disabled.
