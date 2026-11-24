# TROA Admin Overseer + Bifrost

The Realms of Asgard's server operations and diagnostics platform for Space Engineers running on Torch.

Overseer brings server administration, player support, grid inspection, monitoring, Discord integration, rewards and supported plugin operations into **Bifrost**, a browser panel hosted inside the server's Overseer plugin.

**Public documentation and release repository**

Documentation reviewed November 24, 2026.

[Public download](releases/TROA%20Admin%20Overseer%20v0.8.148%20-%20Gridwatch%20Full-Width%20Queue%20Redesign.zip) · [Changelog](CHANGELOG.md) · [Install guide](docs/DEPLOYMENT.md) · [Command reference](docs/COMMANDS.md) · [Documentation index](docs/README.md)

## Which version is available?

| Track | Status |
| --- | --- |
| Latest binary committed to this public repository | **v0.8.148 — Gridwatch Full-Width Queue Redesign** |
| Current documented private implementation | **v0.8.268 — Interactive Dataset Explorer** |
| Private v0.8.268 package | Built and verified separately; not included in this repository |
| Live server deployment | Depends on the operator's installed package; documentation does not update a server |

**The feature map below describes the current v0.8.268 implementation. The older public v0.8.148 download does not include all of these features.** Check your installed build in the panel footer or `!ova status`, and use the [changelog](CHANGELOG.md) to identify when a capability was added. The [public command reference](docs/COMMANDS.md) is explicitly scoped to v0.8.148.

## Explore the platform

### Command Center — understand the server

- **Control room:** current server health, available telemetry and operational entry points.
- **Players & sessions / Player investigation:** received roster, session records, supported ownership links and related evidence.
- **Server readiness:** observed world/session readiness and available plugin inventory.
- **Active jobs:** supported operations and diagnostic jobs, with real progress where the owning service supplies it.
- **My workspace / Operator briefing:** browser-local tool pins, recent grids and authorized activity review.

### Operations — monitor, investigate and manage

| Area | Tools and purpose |
| --- | --- |
| Monitor | Server Monitor, World Radar, SimSpeed incidents and opt-in server flight recorder |
| Investigate | Activity, incident investigation, Before & after, observed grid history, guided troubleshooting and startup diagnosis |
| Manage | Grid Inspector, Grid Maintenance, world/save views and backup-file verification |
| Records & commands | Reports, activity/operation records and authorized command tools |

Available destinations follow the signed-in role and underlying feature permissions.

### Server Monitor — interactive evidence

The current **Explore** workspace has one investigation canvas and a searchable catalog of **47 datasets**. Saved boards remains available for owners who want personal multi-panel layouts.

| Dataset family | Examples |
| --- | --- |
| Simulation and host | SimSpeed, CPU capacity/core usage, working/private/managed memory, process thread count |
| World and grids | Loaded entities, grid blocks/PCU, motion, size, static/mobile status, concealment flags, definitions and ownership |
| Players | Roster, faction distribution, replication ping, observed session time, completed recorded playtime and session counts |
| Runtime and network | OS thread state/lifetime CPU, client latency, optional host probe and retained connection outcomes |
| Recorded profiler | Grid callbacks, block types, scripts, components, owners, factions, entity types and network handlers |

Choose a supported visualization: **line, area, bars, compact heatmap, pie, donut, table or current reading**. Change the visualization inside Inspect too. Filter interactive legends, select slices or samples, zoom time ranges, review source rows and follow related grid evidence.

**Live** follows incoming measurements. **Observe** freezes received evidence. Numeric pies show sample frequencies, not elapsed time or exclusive CPU usage. World/player breakdowns retain their snapshot timestamps; missing telemetry is not invented. Optional country/sector data requires the relevant collection settings and sources. Profiler charts require recorded measurements.

The panel uses its own integrated UI; Grafana is not required or bundled.

### Grid Inspector — construction and systems

The dedicated inspector keeps the selected grid in a persistent workspace with **Inspect, Networks, Systems and Review** views.

- Explore actual block positions, rotations and scale through orbit, pan, zoom, fit and cutaway controls.
- Select blocks and inspect supported weapons, power, propulsion, production, inventory and operational data.
- Review conveyor components, ports, physical connections, isolated sections, branches, paths and loops in a dedicated visual map.
- Use available installed models/materials and actual paint values; unresolved or unsupported assets remain visible in diagnostics.
- Review reported faults and explicit supported timing captures, construction comparisons, saved views and exports.
- Change grids without allowing obsolete inspection work to reopen the previous selection.

Rendering depends on authorized game/mod assets accessible to the server. Game assets are not included in the plugin ZIP. Complete in-game visual parity remains dependent on supported materials, assets and target-server validation.

**A conveyor loop does not prove lag.** Derived physical connections do not prove item-transfer availability. GridWatch risk estimates and shared SimSpeed are investigation context, not measured per-block CPU attribution. Native per-grid Havok solver costs are not fabricated.

### World Radar and diagnostics

World Radar loads current-world observations automatically and exposes supported motion/identity evidence for grids and NPC entities. The flight recorder can retain a bounded observation history when enabled. Incident review, measured before/after comparisons, construction history and guided troubleshooting help owners follow evidence rather than guess at a cause.

Backup verification checks approved files, supported structure and available hashes; it is not a restore test. Compatibility center reviews installed declarations and observable mismatches, not a guarantee that every Workshop mod is compatible or current. Support bundles export selected, sanitized diagnostic evidence for deliberate sharing.

### Discord Monitor — integrated Monitor+

In current builds, Discord Monitor is an **Overseer-owned Monitor+ workspace**, with bot setup, channels, command access, linked Discord:Steam administrators, automation, warnings and message templates.

Supported saves apply at runtime. Administrator-link changes take effect immediately. Connection evidence and **Reload bot** provide recovery controls. A separately installed legacy Monitor+ instance must be retired to avoid competing connections.

Rewards and voting are **independent of Monitor+** in current builds; Monitor+ does not carry reward delivery or vote credentials.

### Rewards, voting, limits and GridWatch

- **Rewards & Voting:** searchable catalog, named bundles and claim packs, player progress, progression, grants, deliveries, voting and settings.
- **Block Limits / Grid Cap:** scope-based rules, caps, exemptions and supported scan-based enforcement actions.
- **GridWatch:** available Profiler+ pressure estimates, staged warnings, related construction evidence and recorded trends.
- **Plugin systems:** supported metrics, settings, registered commands and actions from loaded TROA plugins.

Cleaner+ owns cleanup, GridVault owns backup/recovery, and Hangar owns hangar storage. Overseer coordinates their supported APIs; a plugin name alone does not establish an editable integration. Unsupported capabilities stay unavailable or read-only.

### Administration and personal workspace

Current builds include individual accounts, role policies, applicable update tools, Compatibility center and sanitized support exports. Global panel search finds authorized pages, plugins, commands, players and active grids.

Profile and Appearance offer automatic, separate phone/tablet/desktop theme profiles. Choose scenic backdrop images, Nordic icons or no backdrop. Appearance preferences are account-local in the browser. Terms and Privacy open as panel dialogs in supporting builds.

## Install and start

1. Select an artifact that actually exists in [releases/](releases/) or a separately authorized release channel. Confirm its version and associated notes.
2. Back up the existing plugin ZIP and the Overseer configuration/data directory reported by Torch.
3. Stop Torch. Remove duplicate older Overseer packages from the active plugin directory, then install exactly one verified ZIP containing `Overseer.dll` and `manifest.xml`.
4. Start Torch and confirm the loaded version, module status and Bifrost listener readiness. Run `!ova status` and `!ova doctor` as an authorized operator.
5. Open the configured panel address. Complete the first-account setup using the one-time setup information reported by the installed build, then create individual staff accounts and review access.
6. Exercise configured features in a safe test window, including any owning-plugin handoffs and save confirmation used by restart workflows.

The default Bifrost listener is **127.0.0.1:18750**. Use the generated webserver configuration and an HTTPS reverse proxy with appropriate network restrictions for remote access. Setting a public URL does not create DNS, TLS or a proxy.

`!ova reload` reloads supported configuration; it does not replace a loaded DLL. Binary upgrades require the normal restart. Keep the previous working package and backed-up configuration available for rollback.

See [deployment](docs/DEPLOYMENT.md), [configuration](docs/CONFIGURATION.md), [user guide](docs/USER_GUIDE.md) and [Bifrost operator guide](docs/BIFROST-PLUGIN-PANEL.md). Older guides describe their labeled release; use the current implementation notes in [CHANGELOG.md](CHANGELOG.md) for newer behavior.

## Permissions and data

Current panel roles are **Global Admin, Server Admin, Admin and Mod**, with delegated policies and global-only boundaries. Earlier binaries may expose older role labels or fewer controls. Backend authorization and Torch command ranks remain authoritative; hiding or showing a menu is not a permission grant.

Use `!ov help` for player-safe commands and `!ova help` for the staff commands installed on your server. Review the versioned [command reference](docs/COMMANDS.md) and [permissions guide](docs/PERMISSIONS.md).

Treat player/grid identities, inventories and diagnostic exports as administrative data. Keep credentials, game assets and raw private exports out of public issues and commits. Discord presence rosters require Analytics authorization; custom status text and message bodies must not be persisted. Counts must be labeled approximate when required Presence and Server Members intents are unavailable.

## Verification and known limits

The private v0.8.268 package passed a zero-warning Release build, **178 browser tests and 335 backend checks**. Local Docker UI validation replayed a real private server export with 18 grids and 15,505 blocks. All 47 dataset Inspect actions opened; legend filtering/reset and phone/tablet layouts were checked.

That export had zero online players and no profiler capture/OS-thread detail. Populated roster and optional-source mappings were checked with explicit test fixtures. These checks did not deploy the release, start server captures or establish production profiling overhead, native per-grid physics attribution or complete ship-texture parity.

A previous authenticated check on an existing v0.8.266 server verified actual received telemetry and runtime Inspect responses. It does not mean v0.8.268 is installed on that server.

## Documentation and historical previews

| Read | Purpose |
| --- | --- |
| [Changelog and commit index](CHANGELOG.md) | Current implementation history, release-specific behavior and validation limits |
| [Release index](docs/RELEASES.md) / [packages](releases/) | Existing public artifacts; historical version details |
| [Commands](docs/COMMANDS.md) | Public v0.8.148 command reference |
| [Configuration](docs/CONFIGURATION.md) / [deployment](docs/DEPLOYMENT.md) | Setup, storage and rollout guidance |
| [User guide](docs/USER_GUIDE.md) / [Bifrost guide](docs/BIFROST-PLUGIN-PANEL.md) | Versioned operator documentation |
| [Plugin integration contract](docs/BIFROST-PLUGIN-PANEL-INTEGRATION.md) | Supported owning-plugin integration boundaries |
| [Core Controller](docs/CORE-CONTROLLER.md) | Optional, host-bounded affinity controls; no guarantee of improved SimSpeed |

The existing [panel illustrations](docs/images/) are **historical synthetic previews**, not current screenshots, live server evidence or proof that a newer feature is in the public v0.8.148 ZIP. Private source, server exports and game assets are not published here.
