# Roles and permissions

TROA Admin Overseer combines Torch promote levels with custom TROA permission nodes. Torch promote levels remain the enforcement authority for existing Torch command permissions; custom nodes are available to TROA features that opt into granular checks.

## Role model

A role has a name, optional chat presentation settings, a Torch promote level, direct permission nodes, and optional parent roles. Assign a player only the role they should directly hold. The plugin resolves parent roles automatically.

- The effective Torch rank is the highest rank across direct and inherited roles.
- Direct permission nodes and inherited permission nodes are both effective.
- `*` grants every custom TROA node; `area.*` grants nodes below that area.
- Inheritance cycles are rejected. A role cannot inherit itself, a missing role, a duplicate parent, or a role that already depends on it.
- Removing a role removes it from player assignments and every child role's inherited-parent list.

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