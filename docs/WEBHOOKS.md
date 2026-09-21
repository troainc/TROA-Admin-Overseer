# Overseer Webhooks

Overseer routes every meaningful server event to Discord (or any webhook-compatible endpoint) as a
rich, color-coded embed. This is the plugin's headline feature and is shared by every module.

## How it works
1. A module raises an `OverseerEvent` (category, severity, title, message, key/value fields).
2. The `EventBus` fans it out to the audit database and the `WebhookDispatcher`.
3. The dispatcher looks up the **route** mapped to the event's **category**, renders an embed, and
   delivers it on a background worker with rate limiting and retry.

Delivery never blocks the game thread and never throws into game code; failures are logged and
dropped after retries.

## Setup
1. In Discord: **Server Settings → Integrations → Webhooks → New Webhook**, pick a channel, and
   **Copy Webhook URL**.
2. Open `Instance/TROA Admin Overseer/Webhooks.cfg`.
3. Set `Enabled` to `true`.
4. Paste the URL into a route's `Url`. Use several channels by giving different routes different
   URLs (e.g. a `#moderation` webhook for the `moderation` route, `#joins` for `joins`).
5. (Optional) Set a route's `CriticalMentionRoleId` to a Discord **role id** to ping on critical
   events (bans, watchlist hits, alerts).
6. Save and run `!ov reload`.

## Routes and categories
**Routes** (channels you deliver to): `audit`, `moderation`, `joins`, `performance`, `rewards`,
`limits`, `server`, `critical`.

**Categories** (kinds of events) map to routes in the `Mappings` section. Defaults:

| Category | Route | Example events |
|---|---|---|
| `Server` | `server` | session loaded/unloading |
| `Audit` | `audit` | command used |
| `Connections` | `joins` | connect/disconnect, location, alt detected, watchlist hit |
| `Moderation` | `moderation` | ban, unban, kick, mute, promotion |
| `PlayerTools` | `audit` | heal, feed, teleport |
| `GridTools` | `audit` | fixship, transfer, delete |
| `Limits` | `limits` | (Phase 3) |
| `Performance` | `performance` | (Phase 3) |
| `Rewards` | `rewards` | (Phase 4) |
| `Broadcast` | `server` | (Phase 4) |

Point any category at any route, or set its route to empty to mute it.

## Embed colors (severity)
| Severity | Color | Used for |
|---|---|---|
| Info | blue | routine activity |
| Success | green | completed actions (unban, fixship, connect) |
| Warning | orange | kicks, mutes, alt detection |
| Critical | red | bans, watchlist hits, alerts (role ping eligible) |

## Rate limiting & reliability
- The worker paces sends to stay under Discord's ~30 requests/min per webhook.
- HTTP 429 backs off using the attempt count; 5xx retries; messages are dropped after ~4 attempts.
- Role mentions are restricted to roles (`allowed_mentions`), so embeds can never `@everyone`.

## Non-Discord endpoints
Routes POST a standard JSON payload with an `embeds` array, so any endpoint that accepts a
Discord-style webhook body (custom bots, relays, `webhook.site` for testing) will work.
