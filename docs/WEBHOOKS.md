# Discord webhooks

Webhooks are optional and disabled by default. Configure them in `TROA Admin Overseer Webhooks.cfg`.

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