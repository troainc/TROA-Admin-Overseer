# TROA Admin Overseer

The ultimate all-in-one Torch admin plugin for Space Engineers dedicated servers — built from the
ground up. One DLL, config-file driven, webhook-native. Replaces and enhances Admin Logger,
Connection Log, Ownership Logger, PCU Transferrer, ShipFixer, RespawnFix, BlockLimiter,
Auto Moderator, Essentials, and VoteRewards.

**Version 0.7.2** · [Changelog](CHANGELOG.md)

## Documentation
- [Commands](docs/COMMANDS.md) — full `!ov` command reference
- [Configuration](docs/CONFIGURATION.md) — every `.cfg` file and field
- [Webhooks](docs/WEBHOOKS.md) — Discord setup, routes, embeds
- [Architecture](docs/ARCHITECTURE.md) — how the plugin is built
- [Plan](docs/PLAN.md) — full design and phase roadmap
- [Contributing](CONTRIBUTING.md) — build and development notes

## Status
- **Phase 0 — Scaffold: complete.** Core plugin, module framework, event bus, webhook engine, config
  system, and core `!ov` commands.
- **Phase 1 — Audit, Connections & Webhooks: complete.** SQLite audit/connection store, Discord
  webhook engine (rich embeds, routes, rate limit/retry), chat-command & moderation auditing,
  join/leave + playtime + name/IP history, Steam-P2P IP capture, geo-IP, alt detection, watchlist,
  and the `!ov who / lookup / alts / history / flag` dossier commands.
- **Phase 2 — Player & Grid Tools + Moderation: complete.** Timed bans with reason + appeal id +
  auto-unban sweep, kick/mute, `!ov bans`; heal/feed/teleport/promote/demote; and grid tools —
  fixship (rebuilds the mechanical grid group so subgrids survive), stop, ownership transfer,
  grid list, and delete. All game-state changes run on the session thread; destructive ops are
  admin-gated and abort safely if grid data can't be captured.
- **Roles & administration: complete.** Role/permission system (roles bundle a Torch promote level
  plus custom permission nodes) with `!ov role assign/remove/create/grant/…` and `!ov roles`;
  Essentials-style `!ov setrank/rank/ranks`; read-only `!ov perf` server health; and a Harmony guard
  against the VRage `MyStringHash` collision crash.
- **Broadcast & MOTD: complete.** MOTD on join, rotating announcements, and `!ova broadcast` / `!ov motd`
  — sent to players or everyone, never intercepting player chat (safe alongside a Discord bridge).
- **Limits (BlockLimiter): complete.** Scan-based block limits by Player/Faction/Grid/Global with
  match-by-subtype/type, Alert or TurnOff punishment, and role/SteamID exemptions;
  `!ov limits [player]` / `!ov limit recount`. Disabled by default.
- **Rewards (VoteRewards): complete.** Item-bundle rewards — daily claim (`!ov daily`), optional
  auto playtime rewards, admin grant (`!ova reward`), and **space-engineers.com vote rewards**
  (`!ov claim`, `!ov vote`) via the site's API. Disabled by default.
- Performance/cleanup is intentionally minimal — **Cleaner+ owns that**. Overseer only reports.
- Next: economy/credit payouts, per-role chat prefixes/colors.

All ten legacy plugins are now replaced from scratch: Admin Logger, Connection Log, Ownership Logger,
PCU Transferrer, ShipFixer, RespawnFix, BlockLimiter, Auto Moderator (report-only; Cleaner+ enforces),
Essentials, and VoteRewards.

### Phase 1 notes
- **IP capture** uses Steam P2P session state (`m_nRemoteIP`). It works for direct P2P connections;
  when Steam routes a client through its relay/SDR no public IP exists, so geo/alt-detection stay
  idle for those sessions. Everything else works regardless.
- **Data** lives in `Instance/TROA Admin Overseer/Overseer.db` (SQLite). If SQLite can't load, the plugin keeps
  running (events still go to logs and webhooks) — the DB features just disable.

## Build
Requires the .NET SDK (8.x is fine — it builds `net48` via the reference-assemblies package; no Visual
Studio needed). Point `TorchBin` at your Torch install if it isn't the default path.

```bash
dotnet build -c Release
```
Override the Torch reference location:
```bash
dotnet build -c Release -p:TorchBin="C:\path\to\TorchBinaries"
```

Output lands in `bin/Release/`:
- `Overseer.dll`, `manifest.xml`
- `System.Data.SQLite.dll` + `x64/`, `x86/` native interop

Game and Torch assemblies are intentionally **not** copied — the server already provides them.

## Install
1. Build (or grab a release zip).
2. Copy the `bin/Release` contents into `Torch/Plugins/TROA Admin Overseer/`.
3. Start Torch. Overseer creates `Instance/TROA Admin Overseer.cfg and other TROA Admin Overseer config files` with defaults on first run.
4. Edit the `.cfg` files (add your Discord webhook URLs in `Webhooks.cfg`, set `Enabled` true).
5. In-game/console: `!ov reload` to apply config without a restart.

## Commands
Core: `!ov status` (admin) · `!ov modules` (owner) · `!ov reload` (owner) · `!ov help`
Intel: `!ov who` · `!ov lookup <player>` · `!ov alts <player>` · `!ov history <player>` ·
`!ov flag <player> [note]` · `!ov unflag <player>` (all admin)
Moderation: `!ov ban <player> <duration|perm> [reason]` · `!ov unban <player>` ·
`!ov kick <player> [reason]` · `!ov mute/unmute <player>` · `!ov bans` (all admin)
Player tools: `!ov heal [player]` · `!ov feed [player]` · `!ov tp <player>` · `!ov tphere <player>` ·
`!ov promote/demote <player>` (owner) (admin)
Grid tools: `!ov fixship <grid>` · `!ov stop <grid>` · `!ov gridtransfer <grid> <player>` ·
`!ova gridlist <player>` (admin; no grid deletion command)
Ranks & roles: `!ov setrank/rank/ranks` · `!ov role list/info/create/delete/grant/revoke/assign/remove` ·
`!ov roles <player>` (owner/admin)
Broadcast: `!ova broadcast <message>` (admin) · `!ov motd`
Limits: `!ov limits [player]` · `!ov limit recount` (admin)
Rewards: `!ov daily` · `!ov vote` · `!ov claim` · `!ova reward <player>` (admin)
Server: `!ov perf` (admin)


## Command safety
Players use `!ov`; administrative and owner workflows use `!ova`. Grid actions use the grid under an admin's crosshair when no explicit target is supplied. Ownership transfers always require `!ova confirm`; deletion, backup, restore, and storage remain with TROA GridVault and TROA-Hangar.

## Persistent data
TROA Admin Overseer writes managed JSON to `Instance/TROA Admin Overseer/Overseer.json`. Writes are debounced and occur off the game thread; keep this file with normal instance backups.

## Player reports and moderation
Players use `!ov report <player> <reason>`. Staff use `!ova reports`, `!ova resolvereport`, `!ova warn`, and `!ova note`. Warning escalation is disabled until an owner explicitly sets `WarningEscalationCount` in `Moderation.cfg`.

## Owner operations
`!ova save` requests a Torch game save. `!ova schedule start|stop|status` controls the configured rotating announcements and writes the choice to `Broadcast.cfg`. Restart and cleanup remain exclusively with TROA Cleaner+.

## Configuration naming
The master file is `TROA Admin Overseer.cfg`. Supplementary files use the same prefix, such as `TROA Admin Overseer Webhooks.cfg`. Existing unprefixed configs are copied to the new names once, without deleting the original.

## Audit history
Every emitted plugin event is retained in managed JSON (up to 5,000 recent entries). Admins can inspect it with `!ova audit [count]`.

## Player history
Admins can use `!ova gps <player>` for an online player location. Players can use `!ov rewards` to view their own recorded reward claims.
