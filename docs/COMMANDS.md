# Command reference

Use `!ov` for player-safe commands and `!ova` for staff/owner operations. Check `!ov help` and `!ova help` on the installed build for exact syntax and Torch rank requirements.

## Player commands
`help`, `motd`, `ticket`, `report <player> <reason>`, `vote`, `claim`, `daily`, `rewards [progress]`, `topvoters`, `limits`, `gridcheck`, `limitcheck`, `stop`, `fixship [grid]`.

Grid actions require eligible ownership/mechanical-group checks and obey configured caps/cooldowns.

## Staff/owner groups
- Server: `status`, `perf`, `doctor`, `modules`, `reload`, `audit`, `save`, `restart status|now|cancel`, `schedule`, `maintenance`, `opssummary`.
- CPU: Owner-only `core status|preview <mask>|enable <mask>|disable`.
- Moderation/support: bans, kick, mute, warn, notes, reports/cases, player lookup/history/flags.
- Roles/permissions: role create/assign/temporary/inherit/templates; `perms check`.
- Grids/limits: gridcheck/fixship/stop/transfer/confirm/approve; limits preview/recount/export.
- Rewards/events: bundle list/preview/grant; event announce/check-in/attendees/export/reward.

Legacy `!ov` admin spellings redirect and do not grant privileges. Monitor+ may transport authorized commands; Overseer remains the command owner.
