# TROA Admin Overseer

> A single-DLL Torch administration plugin for Space Engineers dedicated servers.

TROA Admin Overseer gives server owners a clean, organized set of player support, moderation, grid safety, rewards, audit, webhook, and owner-operation tools—without taking over grid archival, cleanup, or restart automation from the TROA plugins that own those jobs.

| What it does | What it deliberately does not do |
|---|---|
| Moderation, staff notes, reports, roles, player tools, safe grid tools, announcements, rewards, audit history | Grid deletion, GridVault/Hangar backup or restore, Cleaner+ cleanup or restart automation |

## Start here

1. Download the newest `TROA Admin Overseer v… .zip` from the release folder.
2. Stop Torch and remove older TROA Admin Overseer ZIPs from its plugin directory.
3. Install **one** current ZIP. It contains exactly `Overseer.dll` and `manifest.xml`.
4. Start Torch once. It creates the master config and supporting TROA-prefixed config files.
5. Set your `ServerName`, review the defaults, then use `!ova reload` after editing configs.
6. Run `!ova status` as an admin. Players can use `!ov help`.

For the complete live-server test, follow [Deployment verification](docs/DEPLOYMENT.md).

## Command roots

| Root | Audience | Examples |
|---|---|---|
| `!ov` | Players | `!ov help`, `!ov motd`, `!ov ticket`, `!ov daily`, `!ov claim`, `!ov rewards`, `!ov report` |
| `!ova` | Admins and owners | `!ova ban`, `!ova fixship`, `!ova save`, `!ova audit` |

`!ov` never runs an admin command. If a server owner or player uses an old `!ov` admin spelling such as `!ov ban`, the plugin only replies with the canonical `!ova ban` form.

## Owner quick guide

### First configuration

The master file is `TROA Admin Overseer.cfg`, next to your other server `.cfg` files. Supporting files use the same naming pattern:

- `TROA Admin Overseer Webhooks.cfg`
- `TROA Admin Overseer Moderation.cfg`
- `TROA Admin Overseer Broadcast.cfg`
- `TROA Admin Overseer Rewards.cfg`
- `TROA Admin Overseer Limits.cfg`
- `TROA Admin Overseer Connections.cfg`
- `TROA Admin Overseer Audit.cfg`

Older generic filenames are copied once to their new prefixed names, so existing settings are retained. Edit the prefixed file thereafter.

### Safe defaults

Webhook routes, rewards, limits, rotating announcements, vote integration, and warning escalation are off until you explicitly enable and configure them. This prevents surprise enforcement or unwanted external posts.

### Support portal

Set `TicketPortalUrlTemplate` in `TROA Admin Overseer.cfg`, then players can use `!ov ticket`. Supported placeholders are `{player}`, `{steamid}`, and `{server}`. This is a safe portal link; direct ticket creation requires your website API endpoint and authentication specification.

### Everyday commands

- `!ova status` — plugin and module status.
- `!ova save` — request a Torch save.
- `!ova schedule start|stop|status` — persistently control rotating announcements.
- `!ova audit [count]` — review the newest emitted events.
- `!ova reload` — reload owner configuration after edits.

### Data and backups

Persistent data is managed JSON at `Instance/TROA Admin Overseer/Overseer.json`. Include it in normal instance backups. It stores player records, sessions, roles, bans, notes, reports, reward claims, and recent audit events.

## Feature map

| Area | Highlights |
|---|---|
| Player support | MOTD, vote links, daily rewards, reward history, player reports |
| Moderation | Warn, note, report review/resolution, ban, kick, mute, temporary-ban expiry |
| Staff tools | Player dossier, alt/session history, heal, feed, teleport, online GPS, ranks and roles |
| Grid safety | Look-at `fixship`, `stop`, confirmed ownership transfer; no deletion command |
| Owner controls | Save, announcement scheduler, configuration reload, module status |
| Operations | Webhooks, connections/player history, limits, persisted audit history |

## Grid safety

`!ova fixship` and `!ova stop` can target the grid directly under an admin’s crosshair. Console callers must provide a grid name or entity ID. `!ova gridtransfer <player> [grid]` always creates a preview; run `!ova confirm` within 30 seconds to apply it.

Grid deletion, backup, restore, and hangar storage are not TROA Admin Overseer features. Use TROA GridVault and TROA-Hangar for those workflows.

## Documentation

- [Commands](docs/COMMANDS.md) — every current player, admin, and owner command.
- [Configuration](docs/CONFIGURATION.md) — each config file, default, and safe enablement path.
- [Webhooks](docs/WEBHOOKS.md) — Discord route setup and testing.
- [Deployment](docs/DEPLOYMENT.md) — installation and live validation.
- [Roadmap](docs/ROADMAP.md) — completed work, boundaries, and remaining API-dependent items.
- [Releases](docs/RELEASES.md) — deployable release history.
- [Changelog](CHANGELOG.md) — current version highlights.

## Support boundaries

TROA Admin Overseer is intentionally a single managed DLL. It does not bundle native SQLite or third-party plugin DLLs. Performance cleanup and restart automation remain owned by TROA Cleaner+. Archive/storage workflows remain owned by TROA GridVault and TROA-Hangar.