## v0.8.140 - Block Limits Enforcement Activation Fix

Fixed the duplicate-rule-label save rejection that kept Enabled from persisting. Enabling a valid policy queues an immediate first scan, then scans at the configured interval. Bifrost distinguishes unsaved pending settings from persisted enforcement state. This is scan-based enforcement, not build placement prevention: Alert reports; TurnOff disables excess functional blocks on scan.

ZIP: [TROA Admin Overseer v0.8.140 - Block Limits Enforcement Activation Fix.zip](../releases/TROA%20Admin%20Overseer%20v0.8.140%20-%20Block%20Limits%20Enforcement%20Activation%20Fix.zip)
Size: 400423 bytes
SHA-256: `D97CEB0ECCD943A8AD14E96BC113A27A9EFD8492A5D764A6EA4C37B870C91483` 

# Release index

## v0.8.104 — Operational Insight and Incident Replay (Phase 5)

Profiler+ baseline comparisons, bounded incident-adjacent replay samples, loaded-plugin/API capability inventory, and opt-in generic browser notifications. Search remains role-gated; no custom Discord presence text or message bodies are persisted.

ZIP: [TROA Admin Overseer v0.8.104 - Operational Insight and Incident Replay - Phase 5.zip](../releases/TROA%20Admin%20Overseer%20v0.8.104%20-%20Operational%20Insight%20and%20Incident%20Replay%20-%20Phase%205.zip)
Size: 280,791 bytes
SHA-256: `6B5624009AEF63F19081EB2B92204691863019E3F48078AF0374DCB22375A191`

## v0.8.103 — Safer Configuration and Maintenance Workflows (Phase 4)

Redacted configuration change history, role-access preview, maintenance readiness, and Owner-confirmed restart preserving Cleaner+-first handoff.

ZIP: [TROA Admin Overseer v0.8.103 - Safer Config and Maintenance Workflows - Phase 4.zip](../releases/TROA%20Admin%20Overseer%20v0.8.103%20-%20Safer%20Config%20and%20Maintenance%20Workflows%20-%20Phase%204.zip)
Size: 275,865 bytes
SHA-256: `BFE7246C521B181F656517E50673E4C129DD64A1C78A3328564CA7C7CE86F073`

## v0.8.102 — World Dossiers and Cleaner+ Preview (Phase 3)

Structured grid dossiers and aggregate-only, read-only Cleaner+ cleanup preview. No cleanup is queued or executed from Bifrost.

ZIP: [TROA Admin Overseer v0.8.102 - World Dossiers and Cleaner Preview - Phase 3.zip](../releases/TROA%20Admin%20Overseer%20v0.8.102%20-%20World%20Dossiers%20and%20Cleaner%20Preview%20-%20Phase%203.zip)
Size: 271,931 bytes
SHA-256: `6A5C15BE9CBDED4BB5AE169D3C70806A170239EFBB37637529076FE9849734DE`

Cleaner+ dependency: v1.12.7; 102,927 bytes; SHA-256 `B56EECEA6A983CC0C4BFB15EADB7839AB0E9CE28A896E3509B26FC8A7FD07FA8`.

## v0.8.101 — Torch Lifecycle and Incident Diagnostics (Phase 2)

Operations reports observed Overseer initialization to Torch `Loaded` timing. When attached after load, it reports present state while original load timing is unavailable. It does not represent AMP, world loading, Linux/Wine, storage, or full readiness timing.

ZIP: [TROA Admin Overseer v0.8.101 - Torch Lifecycle and Incident Diagnostics - Phase 2.zip](../releases/TROA%20Admin%20Overseer%20v0.8.101%20-%20Torch%20Lifecycle%20and%20Incident%20Diagnostics%20-%20Phase%202.zip)
Size: 268,248 bytes
SHA-256: `7B0ED0F380AA4A654B7BAE91822669571BFA8593358B40C75ED31B5B4C80D41F`

## v0.8.100 — Plugin Capability and Source Freshness (Phase 1)

Bifrost cards report config integration, metrics, timestamped history/events, distinguish source sample time from last checked time, and show unavailable/stale/loading/failed/empty states.

ZIP: [TROA Admin Overseer v0.8.100 - Plugin Capability and Source Freshness - Phase 1.zip](../releases/TROA%20Admin%20Overseer%20v0.8.100%20-%20Plugin%20Capability%20and%20Source%20Freshness%20-%20Phase%201.zip)
Size: 267,348 bytes
SHA-256: `51990D471575D32938EFB01E918672562FFE5C2FD15A27A1F1C6BB62AD36308E`

## v0.8.99 — Bifrost Operations Timeline and Incident View

Role-gated source-attributed plugin/audit/Profiler+ incident timeline.

ZIP: TROA Admin Overseer v0.8.99 - Bifrost Operations Timeline and Incident View.zip
Size: 267,282 bytes
SHA-256: D2BB45BE99E9D4EF4BA4B834A5FE647FE9B26AA716FC1D295107957AB96B2E15

Phases 1–5 each received their own verified package before the next phase began. Package verification does not establish Linux/Wine runtime acceptance.
