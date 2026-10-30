# Bifrost service

Bifrost is hosted by Admin Overseer inside Torch. Default listener is loopback port 18750; configure `TROA Admin Overseer Webserver.cfg`. Use HTTPS reverse proxy and network restrictions for remote access; do not expose plain HTTP publicly.

The Owner bootstraps once using a one-time setup code from Torch logs, then creates individual Admin/Moderator accounts. Passwords are salted PBKDF2 hashes; sessions are in memory and bounded.

The panel discovers loaded TROA plugins and uses supported owner-plugin APIs for settings, metrics, and actions. Unsupported capabilities are read-only/unavailable. Server routes enforce roles; client-side visibility is not security enforcement.

Do not persist custom Discord status text or message bodies. Keep presence roster behind Analytics authorization; label approximate counts when required Discord intents are unavailable.
