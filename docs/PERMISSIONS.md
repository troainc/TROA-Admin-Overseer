# Roles and permissions

TROA Admin Overseer combines Torch promote levels with custom TROA permission nodes. Torch promote levels remain the enforcement authority for existing Torch command permissions; custom nodes are available to TROA features that opt into granular checks.

## Role model

A role has a name, optional chat presentation settings, a Torch promote level, direct permission nodes, and optional parent roles. Assign a player only the role they should directly hold. The plugin resolves parent roles automatically.

- The effective Torch rank is the highest rank across direct and inherited roles.
- Direct permission nodes and inherited permission nodes are both effective.
- `*` grants every custom TROA node; `area.*` grants nodes below that area.
- Inheritance cycles are rejected. A role cannot inherit itself, a missing role, a duplicate parent, or a role that already depends on it.
- Removing a role removes it from player assignments and every child role's inherited-parent list.
- A role may carry a display prefix/color label and one or more Discord role IDs. IDs are durable mappings, not Discord credentials.

## Owner workflow

Create a base role, grant its common nodes, then create a more specific role and inherit the base role:

```text
!ova role create helper none
!ova role grant helper player.help
!ova role grant helper moderation.note
!ova role create seniorhelper moderator
!ova role inherit seniorhelper helper
!ova role grant seniorhelper moderation.warn
!ova role assign PlayerName seniorhelper
```

Use `!ova role info seniorhelper` to inspect direct nodes and parents. Use `!ova roles PlayerName` to see direct roles, resolved effective roles, and the resulting Torch rank.

## Permission inspection

`!ova perms check <player> <node>` is read-only. It reports whether a custom TROA node is granted and names the effective role and matching node that granted it. This makes inheritance and wildcard decisions explainable before staff make changes.

## Current limits

A custom node does not automatically override a Torch command's native `[Permission]` attribute. Existing commands continue to use their documented Torch rank. Future TROA features can opt into specific nodes; this prevents accidental privilege expansion during the migration to granular permissions.
## Temporary roles

Owners can grant a direct role for a positive duration:

```text
!ova role temporary PlayerName eventhost 4h
```

Accepted durations use `s`, `m`, `h`, `d`, or `w`, such as `30m`, `12h`, `7d`, or `2w`. Permanent durations are rejected for this command; use `!ova role assign` for a normal permanent grant.

Temporary grants persist through restarts. The roles module checks every 30 seconds, removes expired grants, recalculates the player’s effective native Torch rank, and emits a moderation audit/webhook event. Use `!ova role temporarylist <player>` to view the expiry and assigning staff member.

A temporary role cannot be added when the player already has that same role directly. If a normal role is later assigned, it is treated as a permanent conversion and the temporary expiry record is removed.
## Role presentation and Discord mappings

Owners can give a rank an operator-facing presentation label:

```text
!ova role style eventhost [EVENT] purple
!ova role style eventhost clear
```

Presentation data is retained with the custom role so future chat/bridge surfaces can render it consistently. It does not modify native Torch permissions or game chat by itself.

Discord role IDs can be recorded against a TROA role without giving the plugin a Discord bot token:

```text
!ova role discord add eventhost 123456789012345678
!ova role discord list eventhost
!ova role discord remove eventhost 123456789012345678
```

Use the numeric Discord role ID (Developer Mode -> Copy Role ID), not `@RoleName`. Mappings are owner-only, stored in `Overseer.json`, and audited. They are safe to prepare now for a future authenticated TROA Discord bridge; this outbound-webhook-only plugin does **not** poll Discord or automatically grant in-game access from a role ID. Automatic synchronization needs a separately configured, authenticated bridge and an explicit player identity link, so a Discord display name can never become an access key.
## Standard role templates

Owners can create a safe starting role with `!ova role template apply <template> [newRoleName]`. Templates never overwrite an existing role. Inspect the result before assigning it:

```text
!ova role template list
!ova role template preview senior-moderator
!ova role template apply senior-moderator senior-staff
!ova role info senior-staff
```

Available templates are `helper`, `moderator`, `senior-moderator`, `builder`, `event-host`, `administrator`, and `owner`. A senior moderator inherits `moderator` when that parent role exists. If you use a different moderator role name, add the parent explicitly with `!ova role inherit` after applying the template.