# Admin Overseer Public Roadmap

This roadmap describes priorities for Admin Overseer. The current public documentation describes release v0.8.95.

## Product ownership

Admin Overseer owns administration, moderation, player and admin command behavior, rewards and voting, configured webhook routes, audit records, and the save-confirmed `!ova restart` workflow. Monitor+ may transport authorized commands and replies, but does not own or re-post Overseer behavior. Econ+ owns balances and settlement. GridVault+ owns grid backup and recovery. Cleaner+ owns cleanup scheduling.

## Delivered in v0.8.95

Owner-only CPU affinity controls with cgroup-bounded masks, physical/logical topology reporting, preview/apply/rollback, and Bifrost controls. Validate on Linux/Wine and compare Profiler+ samples before making performance claims.

## Priorities

1. **Rewards release gate:** verify empty, populated, malformed, and repeat imports; complete a migrated pending claim; prevent duplicate grants; audit every grant; and keep CSV catalog edits recoverable.
2. **Restart recovery:** verify save-in-progress, save failure, timeout, cancellation, restart request, crash recovery, and next-start success confirmation on a dedicated server.
   Validate the Cleaner+ pre-restart cleanup handoff and timeout behavior on the actual AMP/Linux/Wine host as part of deployment verification.
   Cleaner+ v1.12.6 release notes: [deep asteroid cleanup and player clearance](https://github.com/troainc/TROA-Cleaner-Plus/blob/main/releases/v1.12.6.md).
3. **Staff case workflow:** add bounded search/filter and read-only permission explanations while preserving audit history.
4. **Release quality:** align package version, manifest, configuration examples, commands, migration notes, and changelog before a release is described as released.

## Release boundary

Priorities are not promises. New behavior is part of a public release only after its versioned package, sample configuration, changelog, and required runtime acceptance are available.

## Bifrost Panel ecosystem settings

- Build an Owner/Admin-only configuration workspace with accessible navigation, search, plain-language field help, unsaved-change warnings, validation results, and per-plugin Save and Reload status.
- Add a versioned adapter contract to each TROA Torch plugin. Each plugin must declare editable settings, redact secrets, validate changes, save atomically, and reload through its own lifecycle/API. Bifrost must not write plugin files directly.
- Keep Moderator access read-only by default. Owners provision accounts and control role assignment. Audit account changes and config edits through Admin Overseer's event/webhook pipeline.
- The v0.8.58 account and status foundations do not provide ecosystem-wide config editing; do not claim ecosystem-wide config editing until every supported plugin adapter is implemented and runtime-verified.
# Bifrost Panel ecosystem config editing

- Add Owner/Admin-only settings screens with search, plain-language field help, validation feedback, unsaved-change prompts, and explicit per-plugin Save and Reload status.
- Every supported TROA plugin must own a versioned adapter that declares editable fields, redacts secrets, validates values, saves atomically, and reloads through that plugin's own lifecycle. Bifrost must not write another plugin's files directly.
- Keep Moderator access read-only by default. Audit account changes and configuration updates through the Overseer event pipeline.
- Do not claim ecosystem-wide config editing until adapters are implemented and runtime-verified for every supported plugin.
