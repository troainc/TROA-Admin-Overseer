Latest build: v0.8.143 — Plugin Configs Modal and Settings Access. Bifrost plugin workspaces have a Configs dialog beside Reload plugin. It hosts plugin-exposed settings, search/groups, load, review/validation, save/apply, and default restore where supported; existing plugin-owned APIs and role restrictions govern edits. Empty config integrations display the needed action clearly.

# Repository context

Latest build: v0.8.142 — Gridwatch Pressure Triage and Reliable Saves. Gridwatch response JSON now matches the panel contract; monitoring saves are confirmed and auto-save. The redesigned panel explains the normalized Profiler+ pressure profile, separates shared serverwide SimSpeed (0–35 points) from grid-specific signals (0–65), and prioritizes adjacent-sample pressure rises coincident with SimSpeed drops as leads for operator review. The coincidence does not prove causation or per-grid tick attribution. Conveyor values are block counts, not network throughput.


Latest build: v0.8.141 — Expanded Gridwatch Per-Grid Telemetry. Gridwatch exposes sampled per-grid systems, mechanical/conveyor block counts, automation/tools/production, projector state, motion, mass, position, ownership IDs, and Profiler+ pressure components. Conveyor counts do not represent links/throughput; both pressure and risk are estimates. Phases 1–5 remain packaged as v0.8.100–v0.8.104. The Operations timeline measures only the observed Overseer-init to Torch-Loaded interval; late attachment means load time unavailable.

The public repository contains public-safe documentation, release notes, and illustrative panel previews. Cleaner+ owns cleanup; its Bifrost integration is aggregate-only and read-only. GridVault owns backup/recovery; Hangar owns storage. Overseer does not infer AMP/world-load timing or claim complete readiness duration. Runtime acceptance on Linux/Wine remains an operator check.
