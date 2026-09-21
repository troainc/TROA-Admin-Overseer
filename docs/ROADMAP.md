# Roadmap and boundaries

## Delivered

- Two-tier command contract: player `!ov`, privileged `!ova`.
- Configurable ticket portal links through `!ov ticket`.
- Opt-in daily streak milestones and configurable player near-limit display.
- Owner configuration doctor and consistent !ova access guard.
- Read-only look-at grid health scanner.
- Single-DLL packaging with release validation.
- Safe look-at grid repair/stop and confirmed ownership transfer.
- Managed JSON persistence for operational records.
- Reports, warnings, notes, durable audit history, Discord webhook routing.
- Owner save and announcement-schedule controls.
- Config naming migration and safe closed-by-default integrations.

## Intentionally outside this plugin

- Grid deletion, archival, restore, hangar storage — TROA GridVault / TROA-Hangar.
- Cleanup and restart automation — TROA Cleaner+.

## API-dependent future work

The installed Torch API reference does not expose a safe supported surface for whitelist enforcement, PCU transfer, inventory clearing, or respawn repair. These remain deferred until a supported, testable API is available. They will not be implemented by guessed reflection or destructive workarounds.

## Release discipline

Every deployable phase builds with zero warnings, packages only the managed DLL and manifest, updates private source/public docs, and requires a fresh Torch log and functional server test for runtime acceptance.
- Delivered staff case summary for safe, read-only moderation review.

- Delivered player-specific audit-trail review for staff cases.

- Delivered stable SteamID correlation for core moderation audit events.

- Delivered complete SteamID correlation across player-report submission and resolution events.
