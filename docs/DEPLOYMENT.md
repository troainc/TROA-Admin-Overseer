# Deployment verification

## Install or upgrade

1. Stop the Torch instance.
2. In the Torch plugin directory, remove every older TROA Admin Overseer ZIP.
3. Install exactly one current `TROA Admin Overseer v… .zip` release.
4. Start Torch.
5. Confirm the log loads **TROA Admin Overseer** without missing-assembly or dependency warnings.

## First acceptance test

- `!ov help` lists player-safe commands.
- A non-admin cannot use `!ova` administration commands.
- An admin can use `!ova status`.
- `!ov motd` and `!ov report` respond correctly.
- A player looking at a wholly major-owned small grid can use `!ov gridcheck`, `!ov stop`, and `!ov fixship`; another player and a mixed-ownership mechanical group or a group above the configured PCU cap are denied.
- `!ova fixship` with no argument requires a grid under the crosshair; from console, use an explicit target.
- `!ova gridtransfer <player> [grid]` previews only; `!ova confirm` applies it.
- After a Torch restart, verify JSON-backed roles, claims, bans, reports, notes, and audit history remain.

## Package verification

The project’s `pack.ps1` runs `verify-release.ps1`. A release fails validation unless:

- the ZIP contains only `Overseer.dll` and `manifest.xml`; and
- the manifest version matches the managed DLL version.

Runtime acceptance still requires a fresh Torch log and the functional test above.