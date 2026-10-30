# Bifrost product roadmap: sequential phase releases

## Release rule

Finish, review, and package each phase before starting the next. Phases 1–5 are complete in v0.8.100–v0.8.104, each with its own package.

## Phase 1 — Plugin capability and freshness — COMPLETE in v0.8.100

Plugin cards report config integration, metrics, timestamped history/events, loading/failure/empty states, source sample time, Bifrost check time, and stale/unknown status. Source sample and response/check timestamps are distinct.

## Phase 2 — Startup and incident diagnostics — COMPLETE in v0.8.101

The Operations timeline reports the measured interval from Overseer initialization to Torch's `Loaded` event only when that lifecycle event is observed. Late attachment reports present state and marks original load time unavailable. This does not measure AMP, Linux/Wine, world loading, storage, or full readiness. Profiler+ incidents remain source-attributed.

## Phase 3 — World visibility — COMPLETE in v0.8.102

Structured grid dossiers and Cleaner+ aggregate-only read-only cleanup preview via explicit owner-plugin API. Cleaner+ owns cleanup; GridVault owns backup/recovery. No cleanup is queued or executed from this panel.

## Phase 4 — Safer workflows — COMPLETE in v0.8.103

Redacted configuration change history, Admin/Moderator role-access preview, maintenance readiness, and Owner-confirmed restart preserving Cleaner+-first handoff. Secret values are not stored in history.

## Phase 5 — Operational insight — COMPLETE in v0.8.104

Profiler+ baseline comparisons, bounded incident replay, loaded-plugin/API capability inventory, and opt-in browser notifications with generic text and browser-local preferences. Activity/command search remains role-gated. Discord roster remains behind Analytics authorization; do not persist custom status text or message bodies; label approximate counts when intents are unavailable.
