# Permissions

Torch command permissions remain authoritative. `!ov` is the player-safe root; `!ova` is for staff/owners subject to each command's required rank.

Owners manage custom TROA roles, nodes, inheritance, temporary assignments, and Bifrost accounts. Inheritance cycles and invalid parents are rejected. `EnforceCustomPermissions` is opt-in and off by default; custom nodes do not automatically override Torch command ranks.

Bifrost uses individual accounts and role-based page/plugin/metric/command/settings visibility. The server checks authorization on every route. Core Controller operations are Owner-only. Discord role IDs are mappings only and do not synchronize permissions.
