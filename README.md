# TROA Admin+ (Overseer)

The all-in-one Torch admin plugin for Space Engineers dedicated servers — one plugin, config-file
driven, webhook-native. Built from the ground up to replace and enhance a whole shelf of separate
plugins (admin logging, connection logs, ownership logging, PCU transfer, ship fixer, respawn fix,
block limiter, auto-moderation, essentials, and vote rewards) with one cohesive tool.

> 🚧 **Status: in testing — public release coming soon.**
> This repository hosts the public documentation. The build will be published here when it's ready.
> Docs may change before release.

## What it does
- **Audit & webhooks** — every meaningful event (admin commands, moderation, connections) as rich,
  color-coded Discord embeds, with per-category routing, rate limiting, and role pings on alerts.
- **Player intel** — a full dossier per player: playtime, sessions, name/IP history, country,
  alt-account detection (shared IP), and a watchlist.
- **Moderation** — timed bans with reason + appeal id + auto-unban, kick, mute, ban list.
- **Player & grid tools** — heal, feed, teleport, promote/demote; fixship (rebuilds a ship and its
  subgrids to fix desync), stop, ownership transfer, grid list, delete.
- **Ranks & roles** — a role/permission system (roles carry a Torch promote level plus custom
  permission nodes) and Essentials-style rank commands.
- **Broadcast & MOTD** — message of the day, rotating announcements, and a broadcast command.
- **Block limits** — per player / faction / grid / global, with alert or turn-off enforcement and
  role/SteamID exemptions.
- **Rewards** — daily and playtime rewards, plus **space-engineers.com** vote rewards.

## Documentation
- [Commands](docs/COMMANDS.md) — the full `!ov` command reference
- [Configuration](docs/CONFIGURATION.md) — every config file and field
- [Webhooks](docs/WEBHOOKS.md) — Discord setup, routes, and embeds
- [Changelog](CHANGELOG.md)

## Command overview
Everything lives under the `!ov` root, for example:

```
!ov help                     Show command help
!ov who / lookup <player>    Online players / player dossier
!ov ban <player> <time> ...  Moderation (ban/kick/mute)
!ov fixship <grid>           Rebuild a ship to fix desync
!ov role assign <p> <role>   Roles & permissions
!ov limits [player]          Block-limit usage
!ov daily / vote / claim     Rewards (incl. space-engineers.com voting)
```

See [docs/COMMANDS.md](docs/COMMANDS.md) for the complete list and permissions.

## Install (coming soon)
1. Download the release from this repository (published at launch).
2. Drop the release ZIP into `Torch/Plugins/`. Do not unpack or add native DLLs: Torch treats every DLL in a package as managed code; the release ZIP contains only `Overseer.dll` and `manifest.xml`.
3. Start Torch — config files are created with defaults on first run under `Instance/`.
4. Edit the config (add your Discord webhook URLs, etc.) and run `!ov reload`.

## Support
Questions and issues: open an issue on this repository. A Discord link will be added at release.
