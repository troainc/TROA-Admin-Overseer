# Admin Overseer command reference

> Public documentation for the currently published Admin Overseer v0.8.148. This list is checked against that release; commands from unreleased builds are not included.

This reference documents the in-game commands registered by Admin Overseer. `!ov` is the player-safe command root. `!ova` is the staff and owner command root. Monitor+ can optionally carry authorized commands between Discord and the game; Admin Overseer still checks permissions and runs the command.

Use one command root exactly as shown. Text in `<angle brackets>` is required; text in `[square brackets]` is optional. A player name can usually be replaced by a SteamID when the command resolves online or stored player records. Torch's built-in permission level is listed below; server role/permission rules can further restrict access.

## Player commands — `!ov`

| Command | Access | What it does |
|---|---|---|
| `!ov help` | Everyone | Lists the player commands and points staff to `!ova help`. |
| `!ov motd` | Everyone | Sends the configured message of the day to you. From the server console, prints the MOTD text. |
| `!ov vote` | Everyone | Shows the configured vote links and the `!ov claim` follow-up. |
| `!ov claim` | Everyone, in game | Checks the configured vote service or claims a pending Discord-reserved vote reward. Grants the configured vote bundle when eligible. |
| `!ov daily` | Everyone, in game | Claims the configured daily reward and records your streak. A configured streak milestone may grant a bonus. Cooldown and reward settings apply. |
| `!ov rewards` | Everyone, in game | Lists your recorded reward claims. |
| `!ov rewards progress` | Everyone, in game | Shows your daily streak, tracked playtime/travel progress, connection time, and next configured reward milestones. |
| `!ov topvoters` | Everyone | Shows the configured vote leaderboard. |
| `!ov ticket` | Everyone | Shows the configured support portal URL, with your player name and SteamID filled into its template. |
| `!ov report <player> <reason>` | Everyone, in game | Submits a player report to staff. You cannot report yourself. The target must resolve to a known player. |
| `!ov limits [page]` | Everyone, in game | Runs a read-only scan of your major-owned grids and shows Player/Grid-scope block-rule counts. Results are paged at 15 rows. It does not show Faction/Global rules or grids you do not major-own. |
| `!ov limitcheck` | Everyone, in game | Shows grid-scoped block rules and near/over-limit status for the major-owned grid under your crosshair. It does not change blocks. |
| `!ov gridcheck [grid name]` | Everyone, in game | Shows block count, PCU, motion, ship/station type, and mechanical-group size for your wholly major-owned grid group. Omit the name to use the grid under your crosshair. |
| `!ov stop [grid name]` | Everyone, in game; if enabled by server | Clears motion on your wholly major-owned mechanical grid group. Configured PCU and cooldown limits apply. |
| `!ov fixship [grid name]` | Everyone, in game; if enabled by server | Captures and rebuilds your wholly major-owned mechanical grid group to recover a broken grid. Configured PCU and cooldown limits apply; if the snapshot cannot be captured, it aborts without changing the grid. |

Player grid tools can be disabled by the server. They require major ownership of every mechanically connected grid and respect the configured PCU ceiling and cooldown. `fixship` reconstructs the grid group, so use it as a recovery action rather than a routine refresh.

## Staff and owner commands — `!ova`

### Server operations and diagnostics

| Command | Minimum Torch rank | What it does |
|---|---|---|
| `!ova help` | Everyone | Lists the main staff command groups. Individual commands still enforce their own permissions. |
| `!ova status` | Admin | Shows Overseer version, configured server name, loaded module count, and webhook enabled state. |
| `!ova perf` | Admin | Read-only snapshot of SimSpeed/TPS, online player count, entity count, and session uptime. |
| `!ova doctor` | Owner | Read-only configuration check for server name, webhook routes, rewards, block limits, legacy configs, and ticket portal URL. It reports findings; it does not repair settings. |
| `!ova modules` | Owner | Lists registered Overseer modules and whether each is loaded. |
| `!ova reload` | Owner | Reloads Overseer configuration and reinitializes its modules. |
| `!ova save` | Owner | Requests an immediate world save. Reports if another save is already running. |
| `!ova restart [status|now|cancel]` | Owner | `status` shows the restart state; `now` requests a coordinated restart; `cancel` cancels an active countdown and resets the schedule. The default action is `now`. The coordinator waits for Cleaner+ deep cleanup and a successful save before the countdown/restart; failed cleanup or save prevents the restart. |
| `!ova schedule [status|start|stop]` | Owner | Shows or toggles rotating announcements. `on` is an alias for `start`; `off` is an alias for `stop`. Default action is `status`. |
| `!ova maintenance <on|off|status> [message]` | Owner | Reads or changes maintenance mode. `on` can set a message and broadcasts it; `off` disables the mode. |
| `!ova opssummary [count]` | Admin | Summarizes recent recorded operations by category and severity. Count defaults to 100 and is limited to 1–100; use `!ova audit` for event titles. |
| `!ova audit [count]` | Admin | Lists recent audit event IDs, times, severity, category, and title. Count defaults to 10. |
| `!ova core status` | Owner | Shows the CPU affinity controller and current masks. |
| `!ova core preview <hex-mask>` | Owner | Validates and previews a CPU affinity mask without applying it. |
| `!ova core enable <hex-mask>` | Owner | Applies a previously reviewed CPU affinity mask, bounded by the host/Torch CPU allowance. Preview first. It does not add CPU capacity or parallelize the game simulation thread. |
| `!ova core disable` | Owner | Restores/disables the Overseer CPU affinity override. |

### Moderation, reports, and player records

| Command | Minimum Torch rank | What it does |
|---|---|---|
| `!ova ban <player> [duration|perm] [reason]` | Admin | Bans a player and records the reason and appeal ID. Duration accepts forms such as `30m`, `12h`, or `7d`; omit it or use `perm` for a permanent ban. |
| `!ova unban <player or SteamID>` | Admin | Lifts the player's active ban. |
| `!ova bans` | Admin | Lists active bans, expiry, and recorded reason. |
| `!ova kick <player> [reason]` | Admin | Kicks an online player. Uses the configured default reason if omitted. |
| `!ova mute <player>` | Admin | Mutes the player's game chat. |
| `!ova unmute <player>` | Admin | Removes the game-chat mute. |
| `!ova warn <player> <reason>` | Admin | Records a staff warning. If the configured warning-escalation threshold is reached, the configured ban escalation is applied. |
| `!ova note <player> <text>` | Admin | Adds an internal staff note to the player's record. |
| `!ova notes <player>` | Admin | Shows up to 10 stored staff notes for the player. |
| `!ova reports` | Admin | Lists unresolved player-submitted reports. |
| `!ova reportqueue` | Admin | Shows the active report queue, including assignment and deadlines. |
| `!ova reportassign <id>` | Admin | Assigns an unresolved report to you (or the console operator). |
| `!ova reportstatus <id> <open|investigating|waiting>` | Admin | Changes the workflow status of an unresolved report. |
| `!ova reportdue <id> <hours|clear>` | Admin | Sets a report deadline 1–720 hours from now or clears its deadline. |
| `!ova reportupdate <id> <text>` | Admin | Adds an internal staff update to an unresolved report. |
| `!ova reporttimeline <id>` | Admin | Shows the internal timeline for a report. |
| `!ova resolvereport <id> [resolution]` | Admin | Resolves a report, optionally recording a resolution note. |
| `!ova who` | Admin | Lists online players and playtime. |
| `!ova lookup <player>` | Admin | Shows a stored player dossier such as playtime, known names, country when available, the count of known IP records, and watch flags. It does not print raw IP addresses. |
| `!ova alts <player>` | Admin | Finds stored accounts that share an IP record with the target. A shared IP is an investigative signal, not proof that accounts belong to one person. |
| `!ova history <player>` | Admin | Shows recent stored player sessions. |
| `!ova case <player>` | Admin | Summarizes moderation context for a player. |
| `!ova caseevents <player> [count]` | Admin | Shows recent stored audit events associated with a player. |
| `!ova faction <player>` | Admin | Shows the target player's faction name/tag, ID, member count, and founder identity. |
| `!ova faction roster <player>` | Admin | Lists identity IDs in the target player's faction, up to 30 entries. |
| `!ova flag <player> [note]` | Admin | Flags a recorded player for staff attention. The default note is `flagged`. |
| `!ova unflag <player>` | Admin | Clears the player's watch flag. |

### Player tools and ranks

| Command | Minimum Torch rank | What it does |
|---|---|---|
| `!ova heal [player]` | Admin | Restores an online player's health to 100%. Omit the target to heal yourself. |
| `!ova feed [player]` | Admin | Refills an online player's energy, hydrogen, and oxygen. Omit the target to refill yourself. |
| `!ova tp <player>` | Admin, in game | Teleports you to the target player's current position. |
| `!ova tphere <player>` | Admin, in game | Teleports the target online player to your position. |
| `!ova gps <player>` | Admin | Prints a GPS coordinate string for an online player. |
| `!ova promote <player>` | Owner | Promotes a player one step on Torch's built-in rank ladder. |
| `!ova demote <player>` | Owner | Demotes a player one step on Torch's built-in rank ladder. |
| `!ova setrank <player> <rank>` | Owner | Sets a player's Torch rank directly. Valid ranks: `none`, `scripter`, `moderator`, `spacemaster`, `admin`, `owner`; `player`, `default`, `mod`, and `sm` are aliases. |
| `!ova rank <player>` | Admin | Shows a player's current Torch rank. |
| `!ova ranks` | Admin | Lists the built-in Torch rank ladder from lowest to highest. |

### Custom roles and permissions

`!ova role create`, delete, grant, revoke, inherit, uninherit, style, role assignment, Discord mapping, and scoped grants are Owner-level changes. Read commands and permission checks are Admin-level unless noted. Role names and permission nodes are server-defined.

| Command | Minimum Torch rank | What it does |
|---|---|---|
| `!ova role list` | Admin | Lists configured roles and their base rank. |
| `!ova role info <role>` | Admin | Shows a role's base rank, direct and scoped permissions, inherited roles, Discord role IDs, and presentation. |
| `!ova role diff <roleA> <roleB>` | Admin | Compares the two roles' base ranks, direct permission nodes, and parent roles. |
| `!ova role create <name> [rank]` | Owner | Creates a custom role. Rank defaults to `none`. |
| `!ova role delete <name>` | Owner | Deletes a custom role. |
| `!ova role grant <role> <node>` | Owner | Grants a permission node directly to a role. |
| `!ova role revoke <role> <node>` | Owner | Removes a direct permission node from a role. |
| `!ova role inherit <role> <parent>` | Owner | Makes one role inherit another role's permissions. Cycles and invalid role pairs are rejected. |
| `!ova role uninherit <role> <parent>` | Owner | Removes a parent-role relationship. |
| `!ova role style <role> <prefix> [color]` | Owner | Sets the role's display prefix and optional color label. Use `clear` as the prefix to remove both. |
| `!ova role template list` | Owner | Lists built-in role templates. |
| `!ova role template preview <template>` | Owner | Shows what a built-in template would configure without creating it. |
| `!ova role template apply <template> [newRoleName]` | Owner | Creates a role from a built-in template. Review it with `!ova role info` before assigning it. |
| `!ova role discord add <role> <discordRoleId>` | Owner | Maps a Discord role ID to a TROA role for configured role synchronization. |
| `!ova role discord remove <role> <discordRoleId>` | Owner | Removes a Discord role mapping. |
| `!ova role discord list <role>` | Admin | Lists Discord role IDs mapped to a TROA role. |
| `!ova role scope grant <role> <node> <faction|player|gridtag|category> <value>` | Owner | Grants a permission node only within the specified faction, player, grid tag, or category scope. |
| `!ova role scope revoke <role> <node> <scope> <value>` | Owner | Removes the matching scoped grant. |
| `!ova role scope list <role>` | Admin | Lists a role's scoped grants. |
| `!ova perms check <player> <node>` | Admin | Explains whether the player has a permission node and which effective roles grant it. |
| `!ova perms scopedcheck <player> <node> <scope> <value>` | Admin | Explains whether the player has a permission within the requested scope and which roles grant it. |
| `!ova role assign <player> <role>` | Owner | Assigns a persistent role to a player and updates their effective Torch rank. |
| `!ova role remove <player> <role>` | Owner | Removes the player's role and recalculates their effective Torch rank. |
| `!ova roles <player>` | Admin | Lists a player's directly assigned roles, inherited/effective roles, and effective rank. |
| `!ova role temporary <player> <role> <duration>` | Owner | Assigns a role until expiry. Use a duration such as `30m`, `12h`, `7d`, or `2w`. |
| `!ova event role <player> <role> <duration>` | Owner | Alias for assigning a temporary role to an event participant. |
| `!ova role temporarylist <player>` | Admin | Lists the player's temporary roles, expiry times, and assigners. |

### Grid tools and block limits

| Command | Minimum Torch rank | What it does |
|---|---|---|
| `!ova gridcheck [grid name or entity ID]` | Admin | Read-only grid health report: type/size, blocks, functional blocks, owners, motion, and mechanical-group size. Omit the grid to inspect the one under your crosshair. |
| `!ova gridlist <player>` | Admin | Lists grids attributed to the player's current identity. |
| `!ova fixship [grid name or entity ID]` | Admin | Captures and rebuilds a grid and its mechanically connected subgrids. A failed capture aborts before changing anything. |
| `!ova stop [grid name or entity ID]` | Admin | Clears motion on the selected grid. |
| `!ova gridtransfer <player> [grid]` | Admin | Previews transfer of the selected grid to the target player. It expires after 30 seconds; complete with `!ova confirm` or, when configured, a different admin uses `!ova approve <requesterSteamId>`. |
| `!ova confirm` | Admin | Applies your pending grid transfer preview when second-staff approval is disabled. |
| `!ova approve <requesterSteamId>` | Admin | Second-staff approval for a pending transfer when the server requires it. The approver must differ from the requester. |
| `!ova limits [player]` | Admin | Shows tracked per-player block-rule use. Without a target, shows your own use; admins may specify another player. |
| `!ova limit scan <player> [page]` | Admin | Performs a read-only live scan of an online player's major-owned grids for Player/Grid-scope rules. Pages contain 15 entries; it changes no blocks. |
| `!ova limit preview [grid name or entity ID]` | Admin | Previews configured grid-scoped rules and current counts for the selected grid. Omit the grid to use the one under your crosshair. |
| `!ova limit recount` | Admin | Queues a block-limit scan immediately. |
| `!ova limit exportcsv` | Owner | Queues a CSV export of registered cube-block definitions and live-world usage columns. The response gives the output path. |

Grid selection for staff commands can use the crosshair or a grid name/entity ID. Grid actions may be further restricted by configured custom permission nodes. Grid caps are scan-based warnings/enforcement; they do not intercept block placement.

### Rewards, events, and broadcasts

| Command | Minimum Torch rank | What it does |
|---|---|---|
| `!ova reward <player>` | Admin | Grants the configured daily reward bundle to a player who has an identity. The player must be online to receive items. |
| `!ova rewards list` | Admin | Lists named reward bundles from the reward catalog. |
| `!ova rewards preview <rewardId>` | Admin | Shows the contents of a named bundle without granting it. |
| `!ova rewards grant <player> <rewardId>` | Admin | Queues a named bundle for the player; pending items are delivered when they are online. |
| `!ova event reward <player>` | Owner | Grants the configured event reward bundle; the player must be online to receive it. |
| `!ova event announce <message>` | Owner | Broadcasts an `[EVENT]` message to game chat. |
| `!ova event checkin <player> <eventId>` | Owner | Records a player's check-in for an event ID up to 48 characters. |
| `!ova event attendees <eventId>` | Admin | Lists stored attendee SteamIDs for the event. |
| `!ova event motd <hours> <message>` | Owner | Sets a temporary event MOTD for 1–720 hours. |
| `!ova event motd clear` | Owner | Clears the temporary event MOTD. |
| `!ova event export <eventId>` | Owner | Exports attendee SteamIDs and recorded names to a CSV in the Overseer config exports folder. Event IDs must contain at least one letter or number. |
| `!ova broadcast <message>` | Admin | Sends a message to everyone in game chat. |
| `!ova motd` | Everyone | Same MOTD command as `!ov motd`; shows your configured message. |

Discord vote reservations are separate from these in-game command handlers: a linked Discord user can use `!reward` or `/adminoverseer reward` in the configured Monitor+/Rewards channel, then claim the pending item bundle in-game with `!ov claim`. Discord commands, channel access, and linking require their respective plugin configuration.

## Legacy command redirects

Older privileged spellings under `!ov` do not grant access. Where a legacy redirect exists—such as `!ov status`, `!ov reload`, `!ov perf`, `!ov save`, `!ov who`, `!ov lookup`, `!ov ban`, `!ov kick`, `!ov heal`, `!ov tp`, `!ov broadcast`, `!ov gridtransfer`, `!ov gridlist`, or `!ov reward`—it only points to the canonical `!ova` command. Run the `!ova` form and satisfy its permission checks.

