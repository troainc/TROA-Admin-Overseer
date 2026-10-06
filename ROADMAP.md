# Admin Overseer Public Roadmap

This roadmap describes priorities for Admin Overseer. The current public documentation remains v0.8.56; private candidate work is not presented as released.

## Product ownership

Admin Overseer owns administration, moderation, player and admin command behavior, rewards and voting, configured webhook routes, audit records, and the save-confirmed `!ova restart` workflow. Monitor+ may transport authorized commands and replies, but does not own or re-post Overseer behavior. Econ+ owns balances and settlement. GridVault+ owns grid backup and recovery. Cleaner+ owns cleanup scheduling.

## Priorities

1. **Rewards release gate:** verify empty, populated, malformed, and repeat imports; complete a migrated pending claim; prevent duplicate grants; audit every grant; and keep CSV catalog edits recoverable.
2. **Restart recovery:** verify save-in-progress, save failure, timeout, cancellation, restart request, crash recovery, and next-start success confirmation on a dedicated server.
3. **Staff case workflow:** add bounded search/filter and read-only permission explanations while preserving audit history.
4. **Release quality:** align package version, manifest, configuration examples, commands, migration notes, and changelog before a candidate is described as released.

## Release boundary

Priorities are not promises. New behavior is part of a public release only after its versioned package, sample configuration, changelog, and required runtime acceptance are available.
