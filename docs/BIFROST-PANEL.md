# Bifrost Panel - SE Torch

## Core Controller — v0.8.96

Owners can see all Linux-online logical CPUs, grouped under physical cores/sockets when available, and distinguish the Torch-allowed set. Choose allowed CPU tiles, preview, and confirm to apply affinity; current/startup/saved masks remain visible and hexadecimal masks are under Advanced. Server-side controls remain Owner-only. See [Core Controller](CORE-CONTROLLER.md).

## Legal information pages in the v0.8.89 release

The release build adds public `/terms` and `/privacy` pages and footer/sign-in links. The matching [Terms of Service](TERMS-OF-SERVICE.md) and [Privacy & GDPR Notice](PRIVACY-GDPR.md) are deployment templates based on the release source. They are deployment templates, not legal advice, and do not certify GDPR compliance. The Panel does not add a terms-acceptance checkbox.

Bifrost Panel runs inside TROA Admin Overseer and reads the active plugin list from Torch. The panel lists plugins whose registered plugin name identifies them as TROA. AMPUtilities and other non-TROA plugins do not appear.

## Setup

1. Install the Admin Overseer release ZIP. The ZIP contains `Overseer.dll` and `manifest.xml` only.
2. Copy `TROA Admin Overseer Webserver.cfg.example` to `TROA Admin Overseer Webserver.cfg` beside the other Admin Overseer config files.
3. Set `BindAddress` to `127.0.0.1` for local-only use, the server IPv4 address to bind one interface, or `0.0.0.0` to listen on all IPv4 interfaces. Set an unused `Port`. `PublicUrl` is the browser-facing URL/domain and is not the bind address.
4. Configure DNS/firewall as needed. Use an HTTPS reverse proxy when exposing the panel outside a trusted network; the built-in listener is HTTP.
5. Start Torch and wait for the green log line **“Bifrost Webpanel is online and ready to use”**. Sign in with the owner account. On first startup, use the one-time code in `TROA Admin Overseer/BifrostPanel/OwnerSetupCode.txt` under the plugin configuration/storage path to create the owner.
6. Use the owner account page to create individual Admin and Moderator accounts. Do not share accounts.

## TROA command console

The command console lists the commands registered by loaded TROA plugins, with the owning plugin, description, syntax, and Torch minimum promotion level. Search the catalog or select a command to put it into the input box, add its arguments, then submit. The server submits one command at a time through Torch's server command manager after checking the command metadata against the panel account role. The response appears in the panel. Non-TROA commands are rejected.

Only Owner and Admin accounts can submit commands. Commands marked Owner-level require the panel Owner account; Moderators can browse but cannot execute. Every accepted command is attributed to the panel username, role, and plugin/command in the Torch log. Some commands require an in-game player and will return the plugin's normal error response when run from the server console.


## Plugin workspaces

Select **Open live workspace** on a detected plugin card. A connected workspace separates live information from configuration settings. Settings are edited in the panel, saved through the owning plugin's recognized config save path, then applied with **Reload plugin** when that plugin supports live reload. The panel does not replace another plugin's config file directly. Save and reload are separate steps so an operator can review changes before applying them.

- **Owner**: manages accounts and can edit all exposed settings.
- **Admin**: can edit settings except values marked Owner-only.
- **Moderator**: read-only panel access.
- Secret fields are never returned to the browser. A blank secret field preserves the current saved secret.
- High-impact cleanup/deletion settings are Owner-only. List settings use JSON and must remain valid JSON to save.
- **Profiler+**: performance snapshot/history charts when its data store exposes them.
- **Cleaner+**: pending cleanup and recent cleanup activity when scheduler/history data is available.
- **GridVault**: backup queue and operation activity when its live state is available.
- Other metrics appear only when the owning plugin exposes a compatible live data point. The panel does not create estimated values.
- AIO Updater config changes are saved for its next scan; reload does not start an update scan immediately.
- A card marked **Integration needed** means the plugin is detected but its config or safe Save/Reload path was not recognized. The normal plugin config and commands remain authoritative.

## Troubleshooting and boundaries

If the panel is not reachable, confirm the startup online message, `Enabled`, bind address, port, firewall, and advertised URL. A domain belongs in `PublicUrl`, not `BindAddress`. After changing the webserver config, run `!ova reload` to restart the listener.

Bifrost does not take ownership of plugin features or commands. Each plugin remains the authority for its configuration and live data. The panel provides a central interface to supported owner-plugin paths. Build and package validation do not replace dedicated Torch runtime validation; confirm each plugin's save/reload behavior on a test server before relying on it operationally.
