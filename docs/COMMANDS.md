# Overseer Command Reference

Commands have two explicit roots: `!ov` is player-safe only; `!ova` is administrator/owner only. Permission levels use Torch promote levels:
**None** (any player), **Admin**, **Owner**. Arguments in `<angle brackets>` are required;
`[square brackets]` are optional.

Player arguments accept a **SteamID**, an **online display name** (exact, then case-insensitive
partial), or a **previously-seen name** (resolved from the Overseer database for offline players).
Grid arguments accept a grid **name** (exact, then partial) or an **EntityId**.

## Core
| Command | Perm | Description |
|---|---|---|
| !ova status` | Admin | Version, server name, loaded module count, webhook state. |
| !ova modules` | Owner | List all modules and whether each is loaded. |
| !ova reload` | Owner | Hot-reload every config file and re-initialize modules. |
| `!ov help` | None | Command summary. |

## Player intel
| Command | Perm | Description |
|---|---|---|
| !ova who` | Admin | Online players with playtime. |
| !ova lookup <player>` | Admin | Dossier: playtime, sessions, first/last seen, country, known names/IPs, alts, flags. |
| !ova alts <player>` | Admin | Accounts that share an IP with the player. |
| !ova history <player>` | Admin | Up to 10 recent sessions with duration and country. |
| !ova flag <player> [note]` | Admin | Flag a player for watch. |
| !ova unflag <player>` | Admin | Remove a player's flag. |

## Moderation
| Command | Perm | Description |
|---|---|---|
| !ova ban <player> <duration\|perm> [reason]` | Admin | Ban with reason and appeal id. See durations below. |
| !ova unban <player>` | Admin | Lift a ban. |
| !ova kick <player> [reason]` | Admin | Kick a player. |
| !ova mute <player>` | Admin | Mute a player's chat. |
| `!ova unmute <player>` | Admin | Unmute a player. |
| !ova bans` | Admin | List active bans with expiry and reason. |

**Duration format:** `30s`, `30m`, `12h`, `7d`, `2w`; a bare number is minutes; `perm`, `0`, or
omitted means permanent. Temporary bans are lifted automatically by the unban sweep.

## Player tools
| Command | Perm | Description |
|---|---|---|
| !ova heal [player]` | Admin | Restore health (defaults to you). |
| !ova feed [player]` | Admin | Refill energy, hydrogen, and oxygen. |
| !ova tp <player>` | Admin | Teleport yourself to a player. |
| !ova tphere <player>` | Admin | Teleport a player to you. |
| !ova promote <player>` | Owner | Raise a player's promote level by one step. |
| !ova demote <player>` | Owner | Lower a player's promote level by one step. |

## Ranks
Space Engineers' built-in promote ladder: **None → Scripter → Moderator → SpaceMaster → Admin → Owner**.

| Command | Perm | Description |
|---|---|---|
| !ova setrank <player> <rank>` | Owner | Set a player's rank directly. Accepts `none`, `scripter`, `moderator`, `spacemaster` (`sm`), `admin`, `owner`, plus `mod`/`player`/`default`. |
| !ova rank <player>` | Admin | Show a player's current rank. |
| !ova ranks` | Admin | Show the rank ladder. |

> `promote`/`demote` step one level at a time; `setrank` sets an absolute rank (like Essentials' setrank).

## Roles & permissions
A **role** bundles a Torch promote level (native enforcement) with optional custom Overseer
permission nodes. Default roles are seeded on first run: `member`, `scripter`, `moderator`,
`spacemaster`, `admin`, `owner`. Assigning a role re-applies the player's effective promote level,
so `role assign <player> admin` actually grants admin.

| Command | Perm | Description |
|---|---|---|
| !ova role list` | Admin | All roles with their rank. |
| !ova role info <role>` | Admin | A role's rank and permission nodes. |
| !ova role create <name> [rank]` | Owner | Create a role (rank defaults to none). |
| !ova role delete <name>` | Owner | Delete a role and its assignments. |
| !ova role grant <role> <node>` | Owner | Grant a permission node (e.g. `moderation.*`, `grid.fixship`, `*`). |
| !ova role revoke <role> <node>` | Owner | Revoke a node. |
| !ova role assign <player> <role>` | Owner | Give a player a role (applies its rank). |
| !ova role remove <player> <role>` | Owner | Remove a role (recomputes rank). |
| `!ova roles <player>` | Admin | A player's roles and effective rank. |

**Permission nodes** use `area.command` with wildcards: `*` (all), `area.*` (e.g. `moderation.*`),
or an exact node. The effective promote level is the highest among a player's roles.

## Broadcast & MOTD
| Command | Perm | Description |
|---|---|---|
| !ova broadcast <message>` | Admin | Send a message to everyone now. |
| `!ov motd` | None | Show the message of the day. |

MOTD (shown on join) and rotating announcements are configured in `Broadcast.cfg`. Messages are
sent to the player or to everyone — Overseer never intercepts or rewrites player chat, so it won't
conflict with a Discord bridge. Placeholders: `{player}`, `{server}`.

## Limits
Scan-based block limits (BlockLimiter-style). Rules count matching blocks per scope and either
alert or turn off the excess. Configured in `Limits.cfg` (disabled by default).

| Command | Perm | Description |
|---|---|---|
| `!ov limits [player]` | None* | Your block-limit usage; `[player]` requires Moderator+. |
| !ova limit recount` | Admin | Force a limit scan now. |

\* Players may view their own limits; viewing another player requires Moderator or higher.

## Rewards
Item-bundle rewards (configured in `Rewards.cfg`, disabled by default). Items go to the player's
inventory, so the recipient must be online.

| Command | Perm | Description |
|---|---|---|
| `!ov daily` | None | Claim your daily reward (respects the configured cooldown). |
| `!ov vote` | None | Show the configured vote links. |
| `!ov claim` | None | Claim your **space-engineers.com** vote reward. |
| !ova reward <player>` | Admin | Grant the daily reward bundle to a player. |

**Voting (space-engineers.com):** set `VoteSiteEnabled` and `SpaceEngineersComApiKey` in `Rewards.cfg`.
`!ov claim` checks the site's API for the player's vote in the last 24h, claims it, and grants
`VoteReward` — only when the site confirms the claim (no double-claims). Automatic **playtime
rewards** (to online players on an interval) are also configured in `Rewards.cfg`.

## Server health
| Command | Perm | Description |
|---|---|---|
| !ova perf` | Admin | Read-only: sim speed (~TPS), online players, entity count, uptime. |

> Overseer does **not** do cleanup or lag auto-moderation — Cleaner+ handles that. `perf` is
> read-only reporting only.

## Grid tools
| Command | Perm | Description |
|---|---|---|
| `!ova fixship [grid]` | Admin | Rebuild the looked-at grid (or an explicit name/entity ID) and its mechanically-connected subgrids. Aborts without changes if capture fails. |
| `!ova stop [grid]` | Admin | Stop the looked-at grid or an explicit target. |
| `!ova gridtransfer <player> [grid]` | Admin | Preview transfer of a looked-at or explicit grid. |
| `!ova confirm` | Admin | Apply your own pending transfer preview within 30 seconds. |
| `!ova gridlist <player>` | Admin | List grids owned by a player. |

> Look-at targeting accepts only a grid directly in the admin's aim path. Console callers must specify a grid. Grid deletion, backup, restore, and storage belong to TROA GridVault and TROA-Hangar.
## Reports, warnings, and staff notes
| Command | Perm | Description |
|---|---|---|
| `!ov report <player> <reason>` | None | Submit a report to server staff. Players cannot report themselves. |
| `!ova reports` | Admin | List unresolved player reports. |
| `!ova resolvereport <id> [resolution]` | Admin | Resolve a report and retain its outcome. |
| `!ova warn <player> <reason>` | Admin | Record a durable warning and notify the moderation webhook route. |
| `!ova note <player> <text>` | Admin | Add a staff-only durable note. |
| `!ova notes <player>` | Admin | Show the ten most recent staff notes. |

`WarningEscalationCount` is closed by default (`0`). Set it above zero only when you also choose a safe `WarningEscalationBanDuration`; escalation occurs once when the threshold is reached.