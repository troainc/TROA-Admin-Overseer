# Bifrost service

Bifrost is hosted by Admin Overseer inside Torch. Default listener is loopback port 18750; configure `TROA Admin Overseer Webserver.cfg`. Use HTTPS reverse proxy and network restrictions for remote access; do not expose plain HTTP publicly.

The Owner bootstraps once using a one-time setup code from Torch logs, then creates individual Admin/Moderator accounts. Passwords are salted PBKDF2 hashes; sessions are in memory and bounded.

The panel discovers loaded TROA plugins and uses supported owner-plugin APIs for settings, metrics, and actions. Unsupported capabilities are read-only/unavailable. Server routes enforce roles; client-side visibility is not security enforcement.

Do not persist custom Discord status text or message bodies. Keep presence roster behind Analytics authorization; label approximate counts when required Discord intents are unavailable.
# Operations timeline

The v0.8.104 Operations page shows source-attributed lifecycle and incident events, Profiler+ baseline comparisons, bounded replay samples, and opt-in generic browser notifications. Notifications are browser-local and poll only while Operations is open and enabled. A startup interval appears only when this plugin observes Torch's session `Loaded` event and is measured from Overseer initialization. If the plugin attaches after load, the page shows current session state and explicitly marks the original load time unavailable. This measurement does not cover AMP, Linux/Wine, world loading, storage, or full server readiness.
