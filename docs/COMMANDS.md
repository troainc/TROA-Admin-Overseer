# Command reference

Use exactly one command root. Arguments in `< >` are required; `[ ]` arguments are optional.

## Player commands — `!ov`

| Command | What it does |
|---|---|
| `!ov help` | Show player-safe commands. |
| `!ov motd` | Show the configured message of the day. |
| `!ov vote` | Show configured voting links. |
| `!ov claim` | Claim a configured space-engineers.com vote reward. |
| `!ov daily` | Claim the configured daily reward; optional milestone streak bonuses are owner-configured. |
| `!ov rewards` | Show your recorded reward claims. |
| `!ov limits` | Show your own tracked block-limit use. |
| `!ov ticket` | Show the configured support ticket portal link. |
| `!ov report <player> <reason>` | Submit a report to staff. |
| `!ov gridcheck` | Read health details for the wholly major-owned grid group under your crosshair. |
| `!ov limitcheck` | Show active grid-scoped limits and near/over feedback for the owned grid under your crosshair. |
| `!ov stop` | Stop motion on the wholly major-owned grid group under your crosshair; cooldown applies. |
| `!ov fixship` | Rebuild the wholly major-owned grid group under your crosshair; cooldown and owner-configured PCU cap apply. |

## Administration — `!ova`

### Server and owner operations

| Command | Minimum permission |
|---|---|
| `!ova status` | Admin |
| `!ova perf` | Admin |
| `!ova audit [count]` | Admin |
| `!ova doctor` | Owner | Read-only check for webhook, rewards, limits, ticket, and legacy-config issues. |
| `!ova modules` | Owner |
| `!ova reload` | Owner |
| `!ova save` | Owner |
| `!ova schedule status|start|stop` | Owner |

### Moderation and reports

| Command | Minimum permission |
|---|---|
| `!ova ban <player> <duration|perm> [reason]` | Admin |
| `!ova unban <player>` · `!ova bans` | Admin |
| `!ova kick <player> [reason]` · `!ova mute <player>` · `!ova unmute <player>` | Admin |
| `!ova warn <player> <reason>` | Admin |
| `!ova note <player> <text>` · `!ova notes <player>` | Admin |
| `!ova case <player>` | Admin |
| `!ova caseevents <player> [count]` | Admin |
| `!ova reports` · `!ova resolvereport <id> [resolution]` | Admin |

### Player and staff tools

| Command | Minimum permission |
|---|---|
| `!ova who` · `!ova lookup <player>` · `!ova alts <player>` · `!ova history <player>` | Admin |
| `!ova flag <player> [note]` · `!ova unflag <player>` | Admin |
| `!ova heal [player]` · `!ova feed [player]` | Admin |
| `!ova tp <player>` · `!ova tphere <player>` · `!ova gps <player>` | Admin |
| `!ova promote <player>` · `!ova demote <player>` | Owner |
| `!ova setrank <player> <rank>` | Owner |
| `!ova rank <player>` · `!ova ranks` | Admin |
| `!ova role list|info|create|delete|grant|revoke|inherit|uninherit|assign|remove|temporary|temporarylist|style` · `!ova role discord add|remove|list` · `!ova roles <player>` | Admin/Owner as shown in command help |
| `!ova perms check <player> <node>` | Admin | Explain whether a custom TROA permission is granted and which effective role grants it. |

### Grid tools

| Command | Minimum permission |
|---|---|
| `!ova gridcheck [grid]` | Admin | Read identity, block, owner, motion, and mechanical-group health without changing a grid. |
| `!ova fixship [grid]` | Admin |
| `!ova stop [grid]` | Admin |
| `!ova gridtransfer <player> [grid]` | Admin |
| `!ova confirm` | Admin |
| `!ova gridlist <player>` | Admin |

### Broadcast, limits, and rewards

| Command | Minimum permission |
|---|---|
| `!ova broadcast <message>` | Admin |
| `!ova limits [player]` · `!ova limit recount` · `!ova limit preview [grid]` · `!ova limit exportcsv` (Owner) | Admin/Moderator as shown in command help |
| `!ova reward <player>` | Admin |

## Legacy migration

Old `!ov` admin spellings are redirect-only. They cannot trigger privileged behavior; use the matching `!ova` command instead.
