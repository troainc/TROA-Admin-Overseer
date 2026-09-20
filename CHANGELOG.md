# Changelog

All notable changes to Overseer are documented here. The format follows
[Keep a Changelog](https://keepachangelog.com/en/1.1.0/), and the project aims to follow
[Semantic Versioning](https://semver.org/spec/v2.0.0.html). Dates are UTC.

## [Unreleased]
### Fixed
- Packaging now excludes native SQLite interop DLLs. Torch reflects every DLL in a plugin ZIP as managed code; including that native file caused a startup BadImageFormatException.

### Planned
- Economy/credit payouts for rewards.
- Chat prefixes/colors per role, and opt-in node-based gating on individual commands.

## [0.7.1] — 2026-09-20
### Added — space-engineers.com vote rewards
- `!ov claim` — claims a player's vote on **space-engineers.com** via its API
  (GET check → POST claim; only votes from the last 24h) and grants `VoteReward`. The reward is
  granted only when the site confirms the claim, so it can't be double-claimed.
- `Rewards.cfg`: `VoteSiteEnabled`, `SpaceEngineersComApiKey`, and a `VoteReward` bundle;
  `!ov vote` now points players to `!ov claim` when voting is enabled.

## [0.7.0] — 2026-09-20
### Added — Rewards (VoteRewards)
- **RewardsModule**: item-bundle rewards via `MyVisualScriptLogicProvider.AddToPlayersInventory`.
  - **Daily reward** (`!ov daily`) with a configurable cooldown, tracked per player in SQLite.
  - **Playtime reward** — optional auto-grant to online players on an interval.
  - **Admin grant** (`!ov reward <player>`) and **vote links** (`!ov vote`).
- `Rewards.cfg` with `RewardItem` bundles (TypeId/SubtypeId/Amount); disabled by default.
- SQLite `reward_claims` table for cooldown tracking.

### Notes
- Item bundles only for now (no economy/credits). Automated vote detection needs the site's API and
  is not wired yet — `!ov vote` shows links only. Recipients must be online to receive items.

## [0.6.0] — 2026-09-20
### Added — Limits (BlockLimiter)
- **LimitsModule**: scan-based block limits. On an interval it counts matching blocks in a single
  pass and enforces per rule. No placement hooks, so it can't break the build/place path.
  - Scopes: **Player**, **Faction**, **Grid**, **Global**.
  - Match by block SubtypeId, TypeId (short or full), or `*`.
  - Punishments: **Alert** (event/webhook) or **TurnOff** (disable the excess functional blocks).
  - Exemptions by role or SteamID (Player scope); per-scan alert cap with a summary line.
- **Commands**: `!ov limits [player]` (players see their own; others need Moderator+) and
  `!ov limit recount`.
- `Limits.cfg` — disabled by default so it never surprise-enforces until configured.

## [0.5.0] — 2026-09-20
### Added — Broadcast & MOTD
- **BroadcastModule**: MOTD shown on join (with `{player}`/`{server}` placeholders and a load
  delay), optional rotating announcements on a timer, and optional in-game join/leave lines.
- **Commands**: `!ov broadcast <message>` (to everyone) and `!ov motd` (show the MOTD).
- `Broadcast.cfg` with author, color, MOTD lines, announcement interval/list, and join/leave toggle.
- Sends to a specific player or to everyone via the chat manager — never intercepts or rewrites
  player chat, so it does not conflict with a Discord bridge or other chat plugins.

## [0.4.0] — 2026-09-20
### Added — Roles, Ranks & administration
- **Role & permission system** — roles bundle a Torch promote level (native enforcement) with
  custom Overseer permission nodes (wildcard support). Default ladder seeded on first run
  (member/scripter/moderator/spacemaster/admin/owner).
  - `!ov role list` / `role info` / `role create <name> [rank]` / `role delete`.
  - `!ov role grant <role> <node>` / `role revoke`.
  - `!ov role assign <player> <role>` / `role remove` — re-applies the player's effective promote
    level (add/remove admin, mod, etc.).
  - `!ov roles <player>` — a player's roles and effective rank.
  - `PermissionService` computes effective promote level and `HasPermission(node)`.
- **Ranks** (Essentials-style promote ladder): `!ov setrank <player> <rank>`, `!ov rank`, `!ov ranks`.
- **`!ov perf`** — read-only server health (sim speed / ~TPS, players, entities, uptime). No
  auto-moderation or cleanup: those are left to Cleaner+.
- **MyStringHash collision guard** (`StringHashCollisionPatch`) — Harmony finalizer that survives the
  VRage 32-bit hash collision which otherwise aborts definition loading with large mod sets. Installed
  early in `Init`; no-op on the normal path.

### Notes
- Performance is intentionally minimal — Cleaner+ owns cleanup/lag handling.

## [0.3.0] — 2026-09-19
### Added — Phase 2: Player & Grid Tools + Moderation
- **Moderation**
  - `!ov ban <player> <duration|perm> [reason]` — timed or permanent bans with a generated
    **appeal id** and an optional appeal link in the webhook embed.
  - `!ov unban`, `!ov kick [reason]`, `!ov mute`, `!ov unmute`, `!ov bans`.
  - Auto-unban sweep that lifts expired temporary bans on an interval (survives restarts).
  - SQLite `bans` table with `AddBan` / `LiftBan` / `GetActiveBans` / `GetExpiredBans`.
- **Player tools** (via `MyVisualScriptLogicProvider`): `!ov heal`, `!ov feed`, `!ov tp`,
  `!ov tphere`, `!ov promote`, `!ov demote`.
- **Grid tools**: `!ov fixship` (rebuilds the whole mechanical grid group so subgrids survive;
  captures object builders before closing and aborts safely on failure), `!ov stop`,
  `!ov gridtransfer`, `!ov gridlist`, `!ov griddelete`.
- `CommandHelpers`: shared player/grid resolution and duration parsing.

### Notes
- All game-state changes are marshalled onto the session thread. Destructive operations are
  admin-gated; `fixship` aborts without modifying the grid if data capture fails.
- Deferred (kept out to avoid shipping untested block manipulation): `depower`, per-player
  `gamemode`, and `respawnfix` refinement.

## [0.2.0] — 2026-09-19
### Added — Phase 1: Audit, Connections & Webhooks
- **SQLite store** (`Overseer.db`): audit log, sessions, player profiles, name/IP history, with
  an async write queue and graceful degrade if SQLite fails to initialize.
- **Discord webhook engine**: `EventBus` → rich embeds with severity colors, category→route
  mapping, rate limiting, retry/backoff, and role pings on critical events.
- **AuditModule**: chat-command auditing plus kick/ban/promote events.
- **ConnectionsModule**: join/leave, playtime, name/IP history, geo-IP (ip-api.com), alt-account
  detection by shared IP, and watchlist alerts.
- **Steam P2P IP capture** (`SteamGameServerNetworking.GetP2PSessionState` → `m_nRemoteIP`),
  relay-aware; `GeoIpService` and `IpResolver`.
- Intel commands: `!ov who`, `!ov lookup`, `!ov alts`, `!ov history`, `!ov flag`, `!ov unflag`.

## [0.1.0] — 2026-09-19
### Added — Phase 0: Scaffold
- Core plugin (`OverseerPlugin`), module framework (`IOverseerModule`, `ModuleManager`),
  `EventBus`, `WebhookDispatcher`, XML `ConfigService`, and the shared `OverseerContext`.
- Core commands: `!ov status`, `!ov modules`, `!ov reload`, `!ov help`.
- `net48` build via the .NET SDK (no Visual Studio required); packaging script.

[Unreleased]: https://github.com/troainc/TROA-Admin-Overseer/compare/main...HEAD
[0.3.0]: https://github.com/troainc/TROA-Admin-Overseer/releases/tag/v0.3.0
[0.2.0]: https://github.com/troainc/TROA-Admin-Overseer/releases/tag/v0.2.0
[0.1.0]: https://github.com/troainc/TROA-Admin-Overseer/releases/tag/v0.1.0
