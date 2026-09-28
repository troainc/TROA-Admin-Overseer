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
- `!ova gridtransfer <player> [grid]` previews only. With default settings, `!ova confirm` applies it; with two-staff approval enabled, a different admin must use `!ova approve <requesterSteamId>`.
- After a Torch restart, verify JSON-backed roles, claims, bans, reports, notes, and audit history remain.

## Rewards and Monitor+ migration

- Configure Discord-to-Steam mappings and the reward bot channel; verify `!reward` and
  `/adminoverseer reward` reserve a vote for the linked account, then confirm that account can
  complete it with `!ov claim`.
- Verify `!ov topvoters` and `!ov rewards` show persisted vote history and claims.
- For migration, create the Overseer Rewards config once, stop Torch, set
  `LegacyMonitorStorageDirectory` to the Monitor+ plugin storage folder, and review `VoteReward`.
  Start a game session with the old data present, confirm the import log, then remove Monitor+.
- Confirm imported pending claims use the intended Overseer item bundle. A successful build and ZIP
  check do not replace dedicated-server gameplay or live Discord acceptance.

## Package verification

The project’s `pack.ps1` runs `verify-release.ps1`. A release fails validation unless:

- the ZIP contains only `Overseer.dll` and `manifest.xml`; and
- the manifest version matches the managed DLL version.

Runtime acceptance still requires a fresh Torch log and the functional test above.
