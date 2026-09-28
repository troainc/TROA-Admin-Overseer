# Discord webhooks

Webhook events are sent by the plugin that owns the event. Monitor+ may transport a Discord command and return its reply, but it does not proxy Admin Overseer's webhook events through Monitor-owned webhook URLs.

Webhooks are optional and disabled by default. Configure them in `TROA Admin Overseer Webhooks.cfg`.

Webhook routes are outbound event delivery. The optional inbound Discord bot used for vote reward
reservations is configured separately in `TROA Admin Overseer Rewards.cfg`; configuring a webhook
does not enable bot commands.

Use the [public Webhooks config example](../TROA%20Admin%20Overseer%20Webhooks.cfg.example) as a template. Edit the live file in the plugin `StoragePath` shown at startup. URLs with query parameters use `&amp;` separators in XML; v0.8.51 automatically repairs bare ampersands and preserves the route configuration. v0.8.52 gives direct route repair instructions for malformed XML.

## Safe setup

1. Create a Discord webhook in the target channel.
2. Set the master `Enabled` value to `true`.
3. Paste the URL into **one** route.
4. Set that route’s `Enabled` value to `true`.
5. Run `!ova reload`.
6. Trigger a low-risk event, such as an owner save or a staff note, and confirm delivery.

An empty URL is always normalized to disabled. Do not commit webhook URLs or vote API keys to Git.

## Routes

Routes are named `audit`, `moderation`, `joins`, `performance`, `rewards`, `limits`, `server`, and `critical`. Map each event category to only the routes you want. A blank mapping is muted.

Typical arrangement:

| Route | Good use |
|---|---|
| `moderation` | Warnings, bans, reports, notes |
| `audit` | Command/audit stream |
| `joins` | Join/leave information |
| `server` | Saves, session lifecycle, owner operations |
| `critical` | Important alerts with optional role mention |

Use `CriticalMentionRoleId` only for an actual Discord role ID and only on a route where a ping is wanted.
