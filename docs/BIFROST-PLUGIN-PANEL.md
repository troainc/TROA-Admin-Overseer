# Bifrost Plugin Panel — operator quick connection guide

## Core Controller — v0.8.96

The Owner-only **Administration → Core controller** workspace maps every Linux-online logical CPU by physical core/socket when available, highlights CPUs allowed to Torch, and provides a selectable CPU map with preview/apply/restore. Hexadecimal masks are an advanced option. See [Core Controller](CORE-CONTROLLER.md).

Bifrost Plugin Panel is the web interface hosted by TROA Admin Overseer inside Torch. It discovers TROA plugins loaded by that Torch process. Availability depends on the installed Admin Overseer release; use a release that includes Bifrost Plugin Panel. Plugins do not connect back to a Panel URL, start a second web server, or create Panel accounts.

## Start using the Panel

1. Install the Admin Overseer ZIP and the TROA plugin ZIPs you want to operate into the same Torch `Plugins` folder. Restart Torch after package changes.
2. Beside Overseer’s other configuration files, copy the example supplied with the Admin Overseer release as `TROA Admin Overseer Webserver.cfg`. Set `Enabled=true`, a free `Port`, and `BindAddress`: `127.0.0.1` for local-only access, a specific server IPv4 to bind that interface, or `0.0.0.0` for all IPv4 interfaces. Set `PublicUrl` to the browser-facing IPv4 URL or domain. `PublicUrl` does not change the network bind.
3. Open the chosen port in the host firewall/router where needed. For remote access over an untrusted network, use an HTTPS reverse proxy in front of the built-in HTTP listener.
4. Start Torch; wait for the green log line **“Bifrost Webpanel is online and ready to use.”** Open `PublicUrl` in a browser.
5. For first-time setup, use the one-time code at `TROA Admin Overseer/BifrostPanel/OwnerSetupCode.txt` under the plugin storage path to create the owner login. Then sign in. The owner creates individual Admin and Moderator accounts in **Access & roles**.
6. Choose **Plugin systems**, find a loaded TROA plugin, and open its workspace. Refresh to request new state. Plugin pages are separate side-menu destinations; only the selected page should be visible.

## Read a plugin workspace

A workspace can combine plugin identity/version, registered commands, settings, live status, metric cards, charts, and recent events. It shows only values the loaded plugin has supplied. Data availability and save/reload controls vary by plugin and release:

- **Connected/editable:** settings can be reviewed, validated, saved, and reloaded through the owning plugin path.
- **Read-only settings:** view the supported settings/status but use that plugin’s own config/command instructions to make changes.
- **Integration needed:** the installed plugin build has not exposed a safe Panel operation for the requested capability.
- **Stale/unavailable metrics:** check the sample timestamp and the owner plugin log; the Panel does not synthesize missing values.

Use each plugin repository’s `docs/BIFROST-PLUGIN-PANEL.md` for workspace-specific expectations and its normal command/configuration guide for feature operation. Domain ownership stays with the plugin: Cleaner+ owns cleanup, Econ+ owns accounting, Hangar+ owns storage/market operations, GridVault+ owns backups, Profiler+ owns diagnostics, and Monitor+ owns Discord transport/monitoring. The Panel does not replace those plugins’ permission checks or operational safeguards.

## Accounts, access, and secrets

Owners create/remove accounts and configure role views in **Access & roles**. Admins can perform only actions granted to their role; Moderators are read-only. The plugin/metric visibility settings control what appears in navigation and dashboards, while command and config permissions separately control actions. Passwords and setup codes must not be shared. Plugin tokens, Discord webhook URLs, and API keys stay in plugin configuration; secret fields are masked in the Panel.

## Troubleshooting

- **Panel URL does not open:** verify Overseer loaded, `Enabled`, bind address, port, firewall, and `PublicUrl`; a domain belongs in `PublicUrl`, not `BindAddress`.
- **No plugin card:** verify the plugin is installed in the same Torch instance and check Torch startup logs for load errors. Refresh Plugin systems.
- **Card exists but workspace is read-only:** that build has not advertised a safe settings save/reload operation. Use plugin documentation and its own reload command.
- **Commands are missing or rejected:** only commands registered with Torch are eligible. Confirm plugin version, command syntax, account permissions, and plugin logs.
- **Charts are empty/stale:** check whether that plugin exposes timestamps/history and whether the server has collected a sample in the chosen time range.

See [Bifrost Plugin Panel integration contract](BIFROST-PLUGIN-PANEL-INTEGRATION.md) for developer ownership and adapter rules, and the [public roadmap](../ROADMAP.md) for current product ownership and release priorities. Build/package checks do not replace acceptance on the target Torch server.
