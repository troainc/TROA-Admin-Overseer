## v0.8.143 — Plugin Configs Modal and Settings Access

Added a **Configs** button beside **Reload plugin** in every Bifrost plugin workspace. The dialog contains each plugin's exposed settings, search and groups, load, review/validation, save/apply, and default restore when supported. Existing role permissions and plugin-owned config APIs remain authoritative. Plugins that expose no fields receive an explicit integration message.

ZIP: [TROA Admin Overseer v0.8.143 - Plugin Configs Modal and Settings Access.zip](../releases/TROA%20Admin%20Overseer%20v0.8.143%20-%20Plugin%20Configs%20Modal%20and%20Settings%20Access.zip)
Size: 419821 bytes
SHA-256: `DEFB8E2249019A12D9D8970F4BF08F366BDD7A175E9231D04163C1E8CA06D5C3`
## v0.8.142 — Gridwatch Pressure Triage and Reliable Saves

- Fixed Gridwatch JSON casing for monitoring configuration, grid telemetry, and alerts; added confirmed save state and automatic persistence for the monitoring switch.
- Separated Discord route save status from telemetry refresh, so a successful save no longer disappears when data reloads.
- Reworked Gridwatch around an estimated Profiler+ pressure profile, explanatory score breakdown, triage summary, and sortable grid review candidates.
- Split shared server SimSpeed points (0–35) from per-grid signal points (0–65). Flags adjacent fresh samples with a ≥10-point per-grid pressure increase and ≥0.03× server SimSpeed drop as correlation for investigation only.
- Pressure components are normalized estimates, not milliseconds or per-grid tick counters; correlation does not prove grid causality.
- Package: TROA Admin Overseer v0.8.142 - Gridwatch Pressure Triage and Reliable Saves.zip; 418402 bytes; SHA-256 `C7A85B131A32F702D66922BAFC69802549B1170469FA69662A39FF46FEBBE1F1`.
## v0.8.141 — Expanded Gridwatch Per-Grid Telemetry

- Expanded per-grid and alert details with sampled functional/powered blocks, mechanical and conveyor inventory, automation, tools, production, projectors, motion, mass, position, and owner IDs.
- Exposed Profiler+ pressure estimate components alongside the separate Gridwatch risk score and sample time.
- Added broad telemetry search and clear explanations of sampled data, conveyor count limits, and estimated values.
- Package: TROA Admin Overseer v0.8.141 - Expanded Gridwatch Per-Grid Telemetry.zip; 409803 bytes; SHA-256 `70ECAB729372479CE09D9BB75A3476171DE04BA710FA4EE8853B6B1D02444449`.
## v0.8.140 - Block Limits Enforcement Activation Fix

- Duplicate rule labels no longer reject saving existing limit policies; each rule remains independently evaluated.
- Enabling a valid policy queues the first scan immediately and continues at the configured interval.
- Bifrost shows pending-save state before persistence and confirms actual enforcement state after read-back.
- Clarified that scans do not prevent placement: Alert reports violations; TurnOff disables excess functional blocks on scan.
- Package: TROA Admin Overseer v0.8.140 - Block Limits Enforcement Activation Fix.zip; 400423 bytes; SHA-256 `D97CEB0ECCD943A8AD14E96BC113A27A9EFD8492A5D764A6EA4C37B870C91483`.

# Changelog

## v0.8.104 — Operational Insight and Incident Replay (Phase 5)

- Added Profiler+ baseline comparisons, bounded incident-adjacent replay samples, an expandable chart, and loaded-plugin/API capability inventory.
- Added opt-in browser notifications using generic text only; preference remains local to the browser/account and polling runs only while Operations is open and notifications are enabled.
- Existing activity and command search remains role-gated. Discord presence privacy rules remain in force.
- Package: `TROA Admin Overseer v0.8.104 - Operational Insight and Incident Replay - Phase 5.zip`; 280,791 bytes; SHA-256 `6B5624009AEF63F19081EB2B92204691863019E3F48078AF0374DCB22375A191`.
- Release build completed with zero warnings/errors; verifier and inline JavaScript parse passed. Linux/Wine runtime acceptance remains operator-side.

## v0.8.103 — Safer Configuration and Maintenance Workflows (Phase 4)

- Added redacted configuration change history, Admin/Moderator role-access preview, maintenance readiness, and Owner-confirmed restart while preserving Cleaner+-first handoff.
- Package: `TROA Admin Overseer v0.8.103 - Safer Config and Maintenance Workflows - Phase 4.zip`; 275,865 bytes; SHA-256 `BFE7246C521B181F656517E50673E4C129DD64A1C78A3328564CA7C7CE86F073`.

## v0.8.102 — World Dossiers and Cleaner+ Preview (Phase 3)

- Added grid dossiers and Cleaner+ aggregate-only read-only cleanup preview through the owning plugin API; no cleanup is queued or executed.
- Package: `TROA Admin Overseer v0.8.102 - World Dossiers and Cleaner Preview - Phase 3.zip`; 271,931 bytes; SHA-256 `6A5C15BE9CBDED4BB5AE169D3C70806A170239EFBB37637529076FE9849734DE`.
- Cleaner+ dependency: v1.12.7, package 102,927 bytes, SHA-256 `B56EECEA6A983CC0C4BFB15EADB7839AB0E9CE28A896E3509B26FC8A7FD07FA8`.

## v0.8.101 — Torch Lifecycle and Incident Diagnostics (Phase 2)

- Operations timeline reports the observed interval from Overseer initialization to Torch's `Loaded` event.
- Late attachment shows current session state and explicitly marks the original load timestamp unavailable.
- The timing is scoped to Torch lifecycle only; it does not claim AMP, world-load, Linux/Wine, storage, or full server readiness durations.
- Profiler+ incidents remain source-attributed and unavailable when the integration exposes no incident records.
- Package: `TROA Admin Overseer v0.8.101 - Torch Lifecycle and Incident Diagnostics - Phase 2.zip`; 268,248 bytes; SHA-256 `7B0ED0F380AA4A654B7BAE91822669571BFA8593358B40C75ED31B5B4C80D41F`.
- Private Release build had zero warnings/errors and `verify-release.ps1` passed. Runtime acceptance on Linux/Wine remains an operator check.

## v0.8.100 — Plugin Capability and Source Freshness (Phase 1)

- Bifrost cards report config integration, metrics, timestamped history/events, and clear loading, failure, empty, stale, and unknown states.
- Distinguishes the plugin's source sample timestamp from Bifrost's last checked time; the panel uses the server-adjusted clock.
- Phase 1 was packaged separately as v0.8.100; phases 2–5 were subsequently completed and packaged as v0.8.101–v0.8.104.
- Package: `TROA Admin Overseer v0.8.100 - Plugin Capability and Source Freshness - Phase 1.zip`; 267,348 bytes; SHA-256 `51990D471575D32938EFB01E918672562FFE5C2FD15A27A1F1C6BB62AD36308E`.
- Release build completed with zero warnings/errors; `verify-release.ps1` passed. Linux/Wine runtime acceptance remains an operator check.

## v0.8.99 — Bifrost Operations Timeline and Incident View

- Added role-gated source-attributed plugin/audit/Profiler+ incident timeline.
- Package: TROA Admin Overseer v0.8.99 - Bifrost Operations Timeline and Incident View.zip; 267,282 bytes; SHA-256 D2BB45BE99E9D4EF4BA4B834A5FE647FE9B26AA716FC1D295107957AB96B2E15.
