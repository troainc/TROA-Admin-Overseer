## November 24, 2026 — Complete README refresh

Product: TROA Admin Overseer / Bifrost. Replaced the stale release-history README with a current product, feature, setup and documentation guide. Documented the current menu families, 47-dataset Server Monitor explorer, live/Observe inspection, grid/conveyor diagnostics, World Radar/toolkit, integrated Monitor+, independent rewards, limits, plugin ownership, roles, responsive appearance and source limitations. Clearly separated private v0.8.268 from the public v0.8.148 artifact and live installation status. Updated linked deployment/release guidance and marked historical previews/versioned guides accurately.

Documentation-only change; no plugin version bump, rebuilt artifact, runtime behavior or live-server update. Local links, version references and existing package hashes were checked. Runtime test totals quoted are the existing v0.8.268 release results, not new tests run for prose edits.

# Implementation history reconciliation — November 24, 2026

Documents recorded implementation through v0.8.269. Historical notes describe the state at that release; later notes may supersede earlier flows. These notes do not publish additional binaries, certify deployment, prove production performance, or establish legal enforceability. The previous public binary remains v0.8.148 unless a separate verified artifact is published. Versions without a supported recorded release entry are not invented. Private implementation and server data remain private.

## README refresh commit references

- Private release-branch documentation: `f1159de` — rewrite current product README and linked setup/release guides.
- Private default-branch documentation: `e1bc7a6` — refresh the repository front page with explicit links to the current release branch; no runtime merge.
- Previous public documentation: `13eadcb` — v0.8.268 dataset explorer and validation notes.

## v0.8.269 — Red fault explanations

Added a Why this block is red panel with exact snapshot/capture triggers, supported impact, cause-known-so-far, next checks, cell identity and timestamp. The grid banner separates measured performance findings from additional health/construction-only red blocks. Grouped reason filters, contributor review, previous/next-red navigation, occupied-cell hover/perspective selection and privileged fault-evidence JSON make the markers actionable.

Incomplete construction is distinguished from damage; missing build-integrity evidence remains uncertain. Red health flags, conveyor loops and shared SimSpeed do not become unsupported lag accusations. New supported captures retain at most four validated exception type names per block while counting additional/unclassified faults. Messages, stacks and script text are excluded; original exceptions are rethrown.

191 browser regressions and 340 backend checks passed, with a zero-warning release build and verified two-file private package. Local synthetic Docker checks covered reasons, exact threshold evidence, filtering/navigation, perspective cell selection and phone/tablet bounds. No live private-server deployment, native capture or diagnosis of the pictured ship is claimed. Geometry/transforms are unchanged.

Implementation `100988b`; verified package `99a025e`; current release documentation `c0522c6`. The public committed binary remains v0.8.148.

## v0.8.268 — Interactive dataset explorer

Server Monitor now opens one searchable investigation workspace, replacing the default stack of chart cards. The catalog exposes 47 existing-source datasets across simulation, host resources, OS threads, world construction/ownership, players, network outcomes and recorded profiling. Saved boards retains existing personal multi-panel layouts as an optional view.

Owners can choose line, area, bars, compact heatmap, sample-frequency pie/donut, source table or current reading where supported. Grouped sources offer bars, pie, donut and table. Inspect includes independent visualization, density, group-count and heatmap-row controls. Numeric slices filter actual retained measurements; interactive legends preserve same-name entity identities. Missing samples and long gaps break both line and area plots.

Player datasets include roster, factions, individual ping, observed session duration, recorded completed playtime/session counts, and optional existing country/sector observations. Grid datasets include blocks, PCU, linear/angular motion, size, static/mobile status, concealment flags, definitions and owner/faction footprint. Profiler views add measured owner, faction, entity and network-handler groupings. No Discord message/status/presence data or new IP lookups are collected by this feature. Existing administrative authorization remains enforced.

Local Docker validation used a private recorded server export with 18 grids and 15,505 blocks: all 47 dataset Inspect actions opened, interactive legend totals changed and reset correctly, and phone/tablet layouts stayed within the viewport. The recording had zero online players and no profiler capture/OS-thread detail; populated roster and optional source mappings were verified with explicit fixtures. 178 browser tests and 335 backend checks passed; Release compilation had zero warnings/errors. The standard two-file Torch package was verified privately. This update was not deployed to the live server; no captures or server settings changes were made.

## v0.8.267 — Verified session reconnection and actual-data validation

Added explicit reconnection for a changed server instance, verified account/role synchronization after access failures, and trusted login metadata before redirecting an existing session. Received inspection data remains available; administrative commands are never automatically replayed. Proxy or unrelated-service responses cannot masquerade as successful authentication.

Actual authenticated development-panel reads on the existing v0.8.266 deployment were verified: all 55 Inspect actions across six layouts, runtime detail, chart legend filtering/reset, sample selection, trend zoom/reset and fresh Live polling. The v0.8.267 recovery UI is a separate packaged update and was not deployed during those checks. Existing profiler/frame graphs still require recorded evidence; no captures were started to fill missing data.

Corrected independent legend filtering for same-name grids and owners using their identifiers, and corrected world-composition source timestamps. Local Docker supports a read-only replay of a private real monitor export without substituting fixtures or publishing its data. 155 browser regressions passed and the final two-file release build had zero warnings/errors. Initial unpublished v0.8.267 package candidates were superseded by the final verified artifact.

## v0.8.266 — Interactive visual dashboards and source recovery

Added an editable Visual systems overview with pie/donut slices, bar breakdowns, sample heatmaps, gauges and time series. Legend toggles change visible totals; selecting slices opens related-entity investigation or a grid, and heatmap selection opens the exact recorded sample. World and profile source semantics remain explicit, including bounded subsets and overlapping inclusive timings.

Reproduced and fixed regional timestamp loss in numeric history, preserving UTC timestamps across tested US, British, German and French cultures. Unauthenticated Operations routes now return sign-in-required responses before feature permissions. Failed data requests no longer silently show empty measurements/default configuration; unsupported fields have concise source disclosures. No missing telemetry is invented.

Added a loopback-only local Docker panel with sample data and optional saved-export replay. Verified 55 Inspect buttons across six layouts, slice filtering/drill-through, sample selection, responsive layouts, 281 backend checks and 148 browser regression tests. No deployment or actual-server performance claim is made. The private and public changelogs now reconcile recorded releases and all pre-reconciliation reachable commits. New public binaries are not implied by these documentation updates.

## v0.8.265 — Interactive Monitor Drilldown

Made Inspect open a responsive six-section investigation dialog with current/history separation, interactive zoom/readouts, sortable/searchable related entities, grid links, profiler evidence and bounded SE/Torch runtime detail.

## v0.8.264 — Live Observe Dashboards

Added five editable native dashboard presets, saved personal layouts, shared time/refresh controls, thresholds and Live/Observe modes. Only retained numeric history can be scrubbed.

## v0.8.263 — World Radar Auto Load

Renamed visible FAULT navigation to World Radar, loaded current-world observations automatically and recovered stale or timed-out polling.

## v0.8.262 — Server Monitor

Added the full Server Monitor: resources, world, ownership, players, network, profiler groupings, frame recorder, collection settings and exports.

## v0.8.261 — Simulation Chronicle

Added bounded frame recordings, interactive frame/range selection, comparison and measured phase/physics lanes. Shared physics timings are not per-grid native CPU costs.

## v0.8.260 — Operations Toolkit Integration

Integrated eleven operational tools and corrected workspace spacing.

## v0.8.259 — Sanitized Support Bundles

Added explicit sanitized support evidence exports with scope controls.

## v0.8.258 — Operational Job Center

Added a view of operations reported by existing plugin/job sources.

## v0.8.257 — Plugin and Mod Compatibility

Compared installed plugin/mod metadata, duplicate identities and declared dependencies; version presence is not proof of compatibility.

## v0.8.256 — Backup File Verification

Verified existing backup files, checksums and supported content without restoring them.

## v0.8.255 — Guided Troubleshooting

Added evidence-led troubleshooting checklists without automatic destructive repairs.

## v0.8.254 — Player Investigation

Connected player sessions and current grid ownership evidence.

## v0.8.253 — Observed Grid History

Recorded observed differences between complete grid inspections; this is not an exhaustive construction audit.

## v0.8.252 — Before and After Diagnostics

Compared matching completed diagnostic captures before and after a change.

## v0.8.251 — Incident Investigation

Correlated recorded incident evidence and linked related grids.

## v0.8.250 — Server Flight Recorder

Added a bounded opt-in history of actual world observations.

## v0.8.249 — FAULT World Radar

Introduced World Radar observations and related-grid investigation; initially displayed with a FAULT label.

## v0.8.248 — Grid diagnostic capture and red 3D findings

Added explicit measured selected-grid diagnostic captures and red 3D findings linked to observed callbacks. Native per-body Havok attribution is unavailable.

## v0.8.247 — Monitor+ Discord recovery and Reload bot

Repaired Discord heartbeat/reconnect lifecycle and added a Reload bot failsafe.

## v0.8.246 — Discord Monitor administrator-link save

Persisted linked administrators with inline confirmation and immediate runtime command access.

## v0.8.245 — Rewards & Voting workspace redesign

Replaced stacked Rewards cards with a searchable scoped table and a selected-reward editor.

## v0.8.244 — Monitor+ owner workspace and independent rewards

Rebuilt the integrated Discord Monitor owner workspace, linked-admin editor and save/reload workflow. Removed Monitor-owned reward processing.

## v0.8.243 — Large-grid capture and session recovery

Added bounded asynchronous large-grid capture and distinguished backend failures from actual session expiration.

## v0.8.242 — Grid Inspector workflow and conveyor construction review

Refined inspection workflow, conveyor map filtering and construction/topology review. Loops alone do not establish lag causation.

## v0.8.241 — Grid Inspector: stop inspection while choosing a grid

Cancelled current-grid polling and asset work as soon as Change grid opens the directory.

## v0.8.240 — Overseer panel connection recovery

Recovered interrupted listener/bind activity and retained active listener sessions during routine reload.

## v0.8.238 — Consistent navigation and global panel search

Unified Operations/Plugins/Administration menus and added global player/grid/tool search.

## v0.8.237 — Command Center and Control room refresh

Improved Command Center destination menus and plugin inventory.

## v0.8.236 — Restore Grid Inspector rendering

Restored WebGL buffer uploads after the preceding rendering regression.

## v0.8.235 — Faster Grid Inspector loading

Prioritized frequently used geometry, streamed material channels independently and bounded shared DDS loading.

## v0.8.234 — Readable conveyor inspection maps

Removed overlapping conveyor labels and added hover/selection, projection and deck filtering.

## v0.8.233 — Optional image and Nordic icon backdrops; final legal presentation

Restored Nordic icon and image backdrops plus a None option, and revised legal document presentation. Presentation changes do not establish legal enforceability.

## v0.8.232 — Responsive Command Center

Added Players & sessions, readiness, active jobs, My workspace and Operator briefing, with automatic device appearance.

## v0.8.231 — In-panel legal document popups

Opened Terms and Privacy in themed in-panel dialogs.

## v0.8.230 — Dashboard, themes, profiles, and access control

Rebuilt Control room, themes, profile and access-control workflows with role defaults and responsive navigation.

## v0.8.229 — Bifrost panel foundation rebuild

Rebuilt the panel foundation, navigation and workspace layout.

## v0.8.228 — Inspection across different grids

Scoped inspection revision/selection state to each grid, preserving generic multi-grid navigation.

## v0.8.227 — Dedicated Grid Inspector operations workspace

Added the dedicated Operations Grid Inspector directory, authorization entry and full-width inspection workspace.

## v0.8.226 — Current material maps take precedence over legacy aliases

Preferred current material channels over obsolete aliases while retaining failures of selected required maps.

## v0.8.225 — Grid Inspector texture prefetch diagnostics

Reported failed prefetch references and corrected a stale UI binding.

## v0.8.224 — Large DDS/model response transport

Repaired large model/DDS socket transfers with bounded idle and total deadlines.

## v0.8.223 — Private LAN texture hook

Added a controlled private installed-DDS source and direct configured asset roots with bounded caching.

## v0.8.222 — On-demand game texture source

Introduced an on-demand installed texture fallback; the earlier browser-directory flow was superseded by the private source.

## v0.8.221 — Grid asset preloading

Added bounded texture preloading, shared requests and private asset caching.

## v0.8.220 — Grid Inspector texture and conveyor repair

Repaired texture/conveyor handling and actionable asset errors.

## v0.8.219 — Grid Inspector active mod asset roots

Resolved approved active-mod asset roots and isolated rejected model references.

## v0.8.218 — Warfare 3 and current TorchAPI compatibility

Updated Warfare 3 block classification and checked installed TorchAPI contracts. This does not guarantee future release compatibility.

## v0.8.217 — Grid Inspector Space Engineers texture pipeline

Repaired DDS resolution/decoding and supported game material translation without changing geometry.

## v0.8.216 — Persistent Grid Inspector and truthful asset diagnostics

Introduced a persistent Grid Inspector workspace and separate asset stage diagnostics.

## v0.8.215 — Conveyor network visualization

Added network colors, disconnected/damaged port indicators, cross-grid-capable markers and inventory markers. Derived physical topology does not prove item transfer.

## v0.8.214 — Grid conveyor layout and load progress

Added a spatial conveyor map and staged loading feedback.

## v0.8.213 — Installed game models, textures and conveyor ports

Added installed model geometry, supported materials and game conveyor ports; available assets determine visual coverage.

## v0.8.212 — Stable interactive Gridwatch inspection

Added interactive grid selection/inspection and stabilized refresh lifecycle behavior.

## v0.8.211 — Preserve exact Gridwatch entity IDs

Preserved exact grid entity identifiers without JavaScript numeric rounding.

## v0.8.210 — Live solid ship renderer

Added shaded block geometry, orbit/zoom and live grid refresh.

## v0.8.209 — Reward catalog groups and live grid inspection

Separated custom reward groups and added live grid inspection.

## v0.8.208 — Gridwatch spacing and metric formatting

Separated Gridwatch metric labels and values with improved spacing.

## v0.8.207 — GridVault breadcrumbs and page visibility fix

Preserved GridVault breadcrumbs and corrected page visibility.

## v0.8.206 — Footer build identification

Displayed installed version and commit information in the footer.

## v0.8.205 — GridVault file manager

Added a searchable GridVault file manager with folders, breadcrumbs and sorting.

## v0.8.204 — Unified navigation, command launcher and themes

Unified navigation, command search and theme surfaces.

## v0.8.203 — Grid workspaces, themes and host telemetry

Added focused Gridwatch/GridVault tabs, maintenance shortcuts and host telemetry.

## v0.8.202 — Single Discord connection

Avoided competing Discord gateway connections; later independent reward ownership supersedes the historical bridge.

## v0.8.201 — Rewards & Voting ownership

Moved voting configuration into Rewards & Voting.

## v0.8.200 — Remove Monitor+ legacy conflict routing

Removed legacy conflict routing and used Overseer-owned Monitor configuration.

## v0.8.199 — Unblock Monitor+ saves during legacy conflict

Avoided stalled saves during legacy Monitor coexistence; superseded by the consolidated integration.

## v0.8.198 — Fix Monitor+ setting control selection

Read settings from their actual form controls rather than duplicate field labels.

## v0.8.197 — Protect pending Monitor+ saves

Prevented refresh from discarding pending Monitor edits.

## v0.8.196 — Monitor+ automatic settings save

Added debounced settings saves and immediate switch/select saves.

## v0.8.195 — Monitor+ channel ID save fix

Corrected Discord channel-ID settings saves while retaining secret-field handling.

## v0.8.194 — Monitor+ toggle rendering fix

Repaired accessible Monitor toggle rendering.

## v0.8.193 — Monitor+ save feedback and interactive controls

Corrected unsaved-state detection and improved save/discard feedback.

## v0.8.192 — Monitor+ config loading and workspace

Repaired Discord Monitor configuration loading and exposed the current configuration.

## v0.8.191 — Daily, streak, and playtime pack setup

Clarified Daily, streak and playtime pack setup.

## v0.8.190 — Remove reward packs and automatic assignments

Added removal/restoration of claim packs and cleanup of automatic assignments.

## v0.8.189 — Complete reward item catalog browsing

Removed truncated reward item browsing and added category/search/sort controls.

## v0.8.188 — Live configured reward pack editing

Added editing for configured reward pack contents.

## v0.8.187 — Rewards summary and tab alignment

Improved reward summaries and tab alignment.

## v0.8.186 — Rewards bundles and one-off tabs

Separated named bundles from one-off reward controls.

## v0.8.185 — Rewards claim pack visibility

Made configured automatic reward claim packs visible.

## v0.8.184 — Workspace navigation and density audit

Audited workspace navigation and information density.

## v0.8.183 — Rewards control tabs

Organized reward grants, progression, delivery/votes, history and settings into focused tabs.

## v0.8.182 — Gridwatch review card cleanup

Separated Gridwatch identity and metric fields into readable layouts.

## v0.8.181 — Torch startup monitoring

Recorded Torch startup lifecycle stages; this does not measure the entire external hosting lifecycle.

## v0.8.180 — Fixship targeting and safe recovery

Improved fixship targeting and aliases without deleting the grid.

## v0.8.179 — Safe grid recovery preparation

Prepared non-destructive grid recovery workflows.

## v0.8.178 — One-off reward audit and live server bundle preview

Added grant audit evidence and a live bundle preview.

## v0.8.177 — One-off player rewards

Added one-off player reward grants with existing authorization.

## v0.8.176 — Cleaner Rewards settings layout

Reduced density in Rewards settings.

## v0.8.175 — Grid Maintenance row layout

Reformatted Grid Maintenance rows and actions.

## v0.8.174 — Cleaner Gridwatch review cards

Improved Gridwatch candidate readability.

## v0.8.173 — Unified Grid Maintenance inventory and actions

Unified stored and live grid maintenance inventory and existing backup/hangar actions.

## v0.8.165 — Configurable Grid Caps and Menu Grouping

Added configurable grid caps and reorganized related menus.

## v0.8.164 — Top menu layout repair

Repaired the top navigation layout.

## v0.8.163 — Offline-safe panel startup

Kept panel startup usable while backend sources are offline.

## v0.8.162 — Panel view and menu repair

Repaired panel view switching and menu behavior.

## v0.8.161 — Scheduled reports, backup readiness, and change history

Added scheduled reporting, backup readiness and administrative change history.

## v0.8.160 — Workspace rail navigation

Introduced workspace navigation for panel tools.

## v0.8.159 — Administration Updater and Visual Reports

Added Administration updater access and visual reports.

## v0.8.158 — Responsive category navigation

Adapted grouped category navigation to smaller screens.

## v0.8.157 — Plugin Startup Toggles

Added plugin startup enable/disable controls.

## v0.8.156 — Discord Monitor Merge

Integrated Discord monitoring into Overseer.

## v0.8.155 — Full Operations Reports

Expanded selectable server operations reports.

## v0.8.154 — World Save Repair Actions

Added explicit world-save repair workflows with the existing administrative checks.

## v0.8.153 — Plugin Source Freshness

Added plugin source freshness information; freshness is separate from compatibility.

## v0.8.152 — Login Client IP Audit

Added login client-address auditing under the existing access controls.

## v0.8.151 — Plugin Systems Loading Fix

Corrected Plugin Systems loading and presentation.

## v0.8.150 — UI Audit

Audited panel navigation, controls and layout consistency.

## v0.8.149 — Private TROA Login and Session Security

Updated the private operator sign-in experience and session protections.

## Earlier published release notes

## v0.8.148 — Gridwatch Full-Width Queue Redesign

Gridwatch review and alert dossiers now use a readable full-width queue. Responsive filters and sort controls use the panel width; grid identity, score, health, pressure, system counts, and details no longer collapse into narrow columns. Telemetry, scoring, and automatic warning behavior are unchanged.

ZIP: [TROA Admin Overseer v0.8.148 - Gridwatch Full-Width Queue Redesign.zip](../releases/TROA%20Admin%20Overseer%20v0.8.148%20-%20Gridwatch%20Full-Width%20Queue%20Redesign.zip)
Size: 423214 bytes
SHA-256: `10BFECA2B7B077C15014B2E16351E6E3940D365FCB58091C83841C3A2EAF159C`
## v0.8.147 — Gridwatch Style and Preview Fix

Moved Gridwatch dossier and Configs dialog overrides into the main stylesheet, and rebuilt the standalone queue preview using the complete panel CSS. This corrects the previous preview where layout overrides were omitted. No telemetry, score, command, or grid-action behavior changed.

ZIP: [TROA Admin Overseer v0.8.147 - Gridwatch Style and Preview Fix.zip](../releases/TROA%20Admin%20Overseer%20v0.8.147%20-%20Gridwatch%20Style%20and%20Preview%20Fix.zip)
Size: 422774 bytes
SHA-256: `B276EFDC72AC3B77F27654450469A604875EB7CD11C733F538B8B38CC3B0BAB4`
## v0.8.146 — Gridwatch Grid Dossier Redesign

Redesigned Gridwatch candidate cards around grid identity, owner, health/risk, block/PCU/Profiler+ pressure metrics, score composition, and connector/conveyor/mechanical/projector summaries. Missing detailed Profiler+ telemetry is labeled Not sampled. Expanded evidence remains available in each card.

ZIP: [TROA Admin Overseer v0.8.146 - Gridwatch Grid Dossier Redesign.zip](../releases/TROA%20Admin%20Overseer%20v0.8.146%20-%20Gridwatch%20Grid%20Dossier%20Redesign.zip)
Size: 422780 bytes
SHA-256: `2231E0E16D35024499B10B8424E9F786722B7AB7253178706A670C74C927D9F5`
## v0.8.145 — Gridwatch Queue Card Layout Fix

Fixed the Gridwatch candidate/alert cards: score and health badges no longer overlap, score detail and long IDs use the card's full readable width, and the queue uses two columns on wide layouts and one column on narrow screens.

ZIP: [TROA Admin Overseer v0.8.145 - Gridwatch Queue Card Layout Fix.zip](../releases/TROA%20Admin%20Overseer%20v0.8.145%20-%20Gridwatch%20Queue%20Card%20Layout%20Fix.zip)
Size: 420896 bytes
SHA-256: `20DC7BF807ECCC1940E49BCB45B335D14CC2E183E5F5B6C5884609A168B5181A`
## v0.8.144 — Polished Config Dialog and Themed Scrollbars

Polished the plugin Configs popup with more balanced spacing, content-sized setting cards, an improved responsive layout, and slim Bifrost-themed scrollbars on the dialog and JSON fields. Configuration behavior and permissions are unchanged.

ZIP: [TROA Admin Overseer v0.8.144 - Polished Config Dialog and Themed Scrollbars.zip](../releases/TROA%20Admin%20Overseer%20v0.8.144%20-%20Polished%20Config%20Dialog%20and%20Themed%20Scrollbars.zip)
Size: 420624 bytes
SHA-256: `BEE8B8A762133E40410685E838597F5B8FBEABE0834D44D69E22882F8BAE2D19`
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

## Complete commit index

Snapshot of all commits reachable from the private implementation branch and public documentation main before this reconciliation commit. Source hashes identify changes; private source URLs and implementation diffs are intentionally omitted from this public index. Documentation commits created after the cutoff are tracked by Git history, avoiding an impossible self-referencing commit hash.

| History | Commit | Date | Change |
| --- | --- | --- | --- |
| Private implementation | `78d0d2edd78b2a36017a7220fa9778a121194133` | 2026-09-19 | Overseer v0.1.0 — Phase 0 scaffold |
| Private implementation | `e05b2b1c92cccf1ebf52030f61cbf31cfd778772` | 2026-09-19 | Phase 1 — Audit, Connections & Webhooks |
| Private implementation | `fc5de8fd668f6740b7484ee9f10707310e463922` | 2026-09-19 | Phase 2 — Player & Grid Tools + Moderation |
| Private implementation | `8cd47fb58e95ad2ce9c2e469742deb215a68b88c` | 2026-09-19 | docs: changelog + full documentation set; bump to v0.3.0 |
| Private implementation | `25a520a0109d519034623072d0fd1a8efccd0997` | 2026-09-19 | feat(ranks): Essentials-style setrank/rank/ranks over the promote ladder |
| Private implementation | `58a8e7b67e834717c0ca54dca98ab4c375a9772f` | 2026-09-20 | feat(roles): role & permission system + perf status; wire StringHash patch (v0.4.0) |
| Private implementation | `5c6959799f1ceedfbb8caf642d064b41e68d5a55` | 2026-09-20 | feat(broadcast): MOTD, rotating announcements, broadcast command (v0.5.0) |
| Private implementation | `da55dce7a02c27513a61437ffab2e3ba94fbebb4` | 2026-09-20 | feat(limits): scan-based block limits (BlockLimiter) v0.6.0 |
| Private implementation | `327709d5ffa64ae1d7be72550672a648f835279d` | 2026-09-20 | feat(rewards): daily/playtime/admin item rewards + vote links (v0.7.0) |
| Private implementation | `2f6e824227df1c800c02bc87278d5cd9d22cd2ca` | 2026-09-20 | feat(rewards): space-engineers.com vote rewards via !ov claim (v0.7.1) |
| Private implementation | `8b71869ce675ff6d0157b95ae042e69a577eb0cb` | 2026-09-20 | fix: package only managed Torch plugin assemblies |
| Private implementation | `b8a4791158c8902bd0f1eab0e6985926bbd3dddf` | 2026-09-20 | docs: track versioned release archives |
| Private implementation | `678439e957fb5f9a1ad573b1597859ff3f506d63` | 2026-09-20 | chore: keep release index with public artifacts |
| Private implementation | `31a40d7812abe938a882d3532b189759c962086b` | 2026-09-20 | fix: remove unavailable Harmony runtime dependency |
| Private implementation | `d236e08267acb07caaae0ef17f5c71fc6b1e0399` | 2026-09-20 | fix: package managed SQLite dependency |
| Private implementation | `dbb356549de013156e0c81daceb635a01590c013` | 2026-09-20 | fix: remove SQLite runtime dependency |
| Private implementation | `62cd15a3ea89c73dd5414129fa88a1af9f0da3da` | 2026-09-20 | feat: standardize TROA Admin Overseer data naming |
| Private implementation | `f0f4230765ead6ad2e88e26b250ac9d91e04b2dd` | 2026-09-20 | feat: simplify config defaults and master config |
| Private implementation | `a50e383636b0da4142d2fa5df616225d65d1073b` | 2026-09-20 | feat: split public and admin command roots |
| Private implementation | `f552a2056a2e7fdeb044d2bca17f477a2493ca07` | 2026-09-20 | feat: add safe look-at grid workflows |
| Private implementation | `62cf55653d6ebff9cf679308ab9b9aaa69bb270e` | 2026-09-20 | feat: persist overseer data as managed json |
| Private implementation | `e638266ea3f163fa16bb8ec81059c9ace4015c16` | 2026-09-20 | feat: add durable report and warning workflows |
| Private implementation | `7717fdd056082a1cb40a23d03c11d9714c6f0f02` | 2026-09-20 | feat: add owner save and scheduler controls |
| Private implementation | `494d76a980ec8039d448c57df2d4f846d999c17c` | 2026-09-20 | feat: standardize troa config names with migration |
| Private implementation | `98950ad5199fa187af1be2b0b335c2a57ac7c37c` | 2026-09-20 | fix: complete public command registration |
| Private implementation | `f5ba5c5b19d00a100bee86d17ca5903de23ba8c5` | 2026-09-20 | feat: persist audit event history |
| Private implementation | `d21b565e1cfb0e7c9a995501cc30186d0a0b08b0` | 2026-09-20 | feat: add player gps and reward history |
| Private implementation | `f14242f7f923ccea79d87683b76260da1205229c` | 2026-09-20 | feat: add safe legacy admin command redirects |
| Private implementation | `a960e1930a632396b6719af4eb16575a9b019fab` | 2026-09-20 | docs: add owner deployment guides and release validation |
| Private implementation | `545dc88f5037b1d4c4de4ea5a550f38f003df045` | 2026-09-20 | feat: add configurable ticket portal |
| Private implementation | `4855e4fc9236a143d7f2a0597ac9e5f2003fefae` | 2026-09-20 | feat: add daily streaks and near limit status |
| Private implementation | `0e7d330d1d9c21561bb6d550df1cd80a75b3b04c` | 2026-09-21 | feat: add configuration doctor |
| Private implementation | `5072b789e40b9bc15f8311a85a5624034a0a7336` | 2026-09-21 | feat: add read-only grid health scanner |
| Private implementation | `42948101af4876cd7d141df0eb5a877bdbb7c49c` | 2026-09-21 | feat: add staff case summary |
| Private implementation | `787f06779e8c2413fd4e4a30a7dba22d9b53067d` | 2026-09-21 | feat: add player audit trail |
| Private implementation | `bb3a719ccfb551685943d2a0afbd00e9251f85e5` | 2026-09-21 | feat: correlate moderation audit events |
| Private implementation | `113581517acf93283cc31b6d32575f3bd5f45e52` | 2026-09-21 | feat: correlate resolved report audit events |
| Private implementation | `eba575c53e046cea47501012f5f354168f367af3` | 2026-09-21 | feat: add player owned grid recovery |
| Private implementation | `88d66a72bb82365e82c79b5f6fd03c5f5dd867ec` | 2026-09-21 | feat: make player grid PCU cap configurable |
| Private implementation | `f81eb89a55214ba6d3e5a93fce4c095762ed25ce` | 2026-09-21 | feat: add inherited custom roles and permission inspection |
| Private implementation | `f86f990f1c022ed6a684affa5bfd333e9dab49d6` | 2026-09-21 | feat: add durable temporary role grants |
| Private implementation | `a1463db5163da7bbe6aec50390db7028f863082e` | 2026-09-21 | Release v0.8.24 Discord role mappings |
| Private implementation | `177fe64e608bebf68a73909b517aee42fc8820e9` | 2026-09-21 | Release v0.8.25 context-aware block limits |
| Private implementation | `6c4bd7a884bb682328315ed28ee03f2fe5e8af33` | 2026-09-21 | Release v0.8.26 live limit preview |
| Private implementation | `d5afea48bfd025c7f95172bb3c42f59665c7836e` | 2026-09-21 | Restore changelog heading |
| Private implementation | `e6d9a3ce30c6e6effc350085dca7852fd169ab26` | 2026-09-21 | Release v0.8.27 complete block catalog export |
| Private implementation | `29af6e321dc9182e2782604e968f86b816fe3c9c` | 2026-09-21 | Release v0.8.28 standard role templates |
| Private implementation | `9a2196212046ce09a3d0e2146398c5bf0cab412f` | 2026-09-21 | Release v0.8.29 scoped role permissions |
| Private implementation | `8ddc1bda37d5f2aa0bff031ba655a1749f35db88` | 2026-09-21 | Release v0.8.30 policy enforcement |
| Private implementation | `fa330961dc81bea1121fc4e583494ffbfea9ce01` | 2026-09-21 | Correct policy gate command mappings |
| Private implementation | `f1183e10563438ce4f7be0d9612a34b08c512192` | 2026-09-21 | Keep grid list outside policy gate |
| Private implementation | `d1abfe3b7dbf8a20c99e954cd8ed15c4acd506ea` | 2026-09-21 | Release v0.8.31 two-staff transfer approval |
| Private implementation | `fa5a34922836bd01873822421ab569c12c382823` | 2026-09-21 | fix: enforce two-staff transfer approval |
| Private implementation | `d02c3219fda09f5cf3b0cb42062124dd914e9b5c` | 2026-09-21 | feat: add staff case workflow |
| Private implementation | `7dc6d53019a01e8df3b50528aa33a1942f13c7d6` | 2026-09-21 | feat: add staff case queue |
| Private implementation | `1d8c45f2ff4a459ffca9f55d0a18e8358e05d08a` | 2026-09-21 | feat: expand opt-in policy enforcement |
| Private implementation | `edb66bc78c8bc18907ca05335152bbeb56eb206d` | 2026-09-21 | feat: add role comparison |
| Private implementation | `971e9a32f2a273198f26464be4c286fa3362c615` | 2026-09-21 | feat: add operations summary |
| Private implementation | `d1b7bcf3cdf0af1aa24984bef1bdeb4c6487f065` | 2026-09-21 | feat: add faction dossier |
| Private implementation | `e2414c03364467056f51f32e5dcf75a0c5ffb31a` | 2026-09-21 | feat: add faction roster |
| Private implementation | `9aa952191bbd24c6f6ebe91c9c3039d1053b86c2` | 2026-09-21 | feat: add event role command |
| Private implementation | `9bfc0079f95a3fc4c23f900d35672850d47851f9` | 2026-09-21 | feat: add event announcements |
| Private implementation | `ee2d6d501ae7add4395e97a18260f714e92c2bde` | 2026-09-21 | feat: add event participant tracking |
| Private implementation | `a2f2481cfe7221d58ce0c09c4db81be78aac6f92` | 2026-09-21 | feat: add event reward command |
| Private implementation | `f748090f2e6b75465dbd0a9868475e57dfd6a85a` | 2026-09-21 | feat: add expiring event motd |
| Private implementation | `4c5d4c3612a00aeeaef3a8b3c70ada4f7473a0ed` | 2026-09-21 | feat: add maintenance mode |
| Private implementation | `7281ccbf5ecdbd3102293c728af0427137015088` | 2026-09-21 | feat: add scheduled operations summaries |
| Private implementation | `fb1298a67e79944f43b6d55bebf2eea01d625a12` | 2026-09-21 | feat: export event attendees |
| Private implementation | `f86905d1d881b94386c9ddfc0a02dc17129e9bac` | 2026-09-21 | feat: export block catalog on startup |
| Private implementation | `ff86f4e7bcf6bc12417f94fead4ec6f5bd0dd8e1` | 2026-09-21 | docs: describe automatic block catalog |
| Private implementation | `ad8be4cf7898fc20d21067888494f22748ea26e8` | 2026-09-21 | fix: export block catalog to plugin data folder |
| Private implementation | `87d7882563b8c3c2143f472f39963dd4dacc89c0` | 2026-09-21 | docs: fix catalogue formatting |
| Private implementation | `2f52d4023b08d18d35a5b5bf6040b992177a9b2f` | 2026-09-21 | docs: align block catalog owner guidance |
| Private implementation | `72c2e703648a887c77689dc725102ce12ad355ba` | 2026-10-29 | Add Overseer restart coordination candidate |
| Private implementation | `246c4c038ec69867979eab1ccdcb10dcccbdd081` | 2026-10-29 | Release Overseer v0.8.93 from aligned source |
| Private implementation | `f7237d7bb303a70dfe07936bbebf35c8c0fedecb` | 2026-10-29 | Add default block limit baseline |
| Private implementation | `a6193b5c26ee356c5f75456e95635e2187bdf1c5` | 2026-10-29 | Harden and modularize Bifrost Panel |
| Private implementation | `487e31fb846eee38d5a160abbcfdba3864a5aa58` | 2026-11-01 | Release v0.8.143 plugin configs workspace |
| Private implementation | `0bdff071c551e53c6ec610962c0c37241ae857d4` | 2026-11-01 | Release v0.8.144 polished config dialog |
| Private implementation | `09d826babb2a3a377323f14a2289b4f3f5426e26` | 2026-11-01 | Release v0.8.145 Gridwatch card layout fix |
| Private implementation | `2ab4b44625e8aff42960fd7add5e09bc92444ef3` | 2026-11-01 | Release v0.8.146 Gridwatch dossier redesign |
| Private implementation | `a02729138dc0e7c7ea7bfdb3908ef639e4d567df` | 2026-11-01 | Release v0.8.147 Gridwatch stylesheet and preview fix |
| Private implementation | `14887a3ca6f338efd8d708a69761842f2b9a0f8d` | 2026-11-02 | Release v0.8.148 Gridwatch full-width queue redesign |
| Private implementation | `4eb057d59dbd67111d642c004e493b76a0f5ff2b` | 2026-11-14 | Document every Overseer command and permission |
| Private implementation | `5b448be049151a6272c7e487af6af9de47b4c80d` | 2026-11-14 | Release v0.8.177 one-off player rewards and Grid Maintenance |
| Private implementation | `5d045e4f07c0f87de956c84fbf63e0fb6104e75e` | 2026-11-14 | Release v0.8.178 reward audit and live bundle preview |
| Private implementation | `6e81e081506de42a42585a705744d8cea05cf76c` | 2026-11-14 | Make fixship recovery non-destructive |
| Private implementation | `f9b773f19c0514f1bbdd1cc4933f49c05bb05aff` | 2026-11-14 | Improve fixship targeting and aliases |
| Private implementation | `9518c56ac30052289cf7dbcb9f1bc9ed64be4aba` | 2026-11-14 | Add Torch startup lifecycle monitoring |
| Private implementation | `9d5a520f1d67a7402340b4b580fde9206f47099c` | 2026-11-14 | Fix Gridwatch review card layout |
| Private implementation | `dade609eed8628f6e652dd78e156932a67fa2a11` | 2026-11-14 | Rework rewards workspace into tabs |
| Private implementation | `d025eafd2051dff84853eed5c3b214814e1e4ec0` | 2026-11-14 | Improve Overseer workspace navigation UX |
| Private implementation | `a7ded189297c8325eb8446bd1efbaa06d90d9eb7` | 2026-11-14 | Show configured reward claim packs in panel |
| Private implementation | `b7897a3e47f3e216d7f4a2341ee8e75afc74435e` | 2026-11-14 | Separate reward bundles and one-off controls |
| Private implementation | `87a83bdc51dc2a22593d711168375ef7af140bbe` | 2026-11-14 | Clean up rewards summary and tab layout |
| Private implementation | `b231037757e6332377385e55de5cc6ed25c77177` | 2026-11-14 | Add live editing for configured reward packs |
| Private implementation | `a3c7f862398c32cf65ca51d6e834ad80084d9080` | 2026-11-14 | Improve reward item catalog browsing |
| Private implementation | `f9c997a6d3abed7d0698e513464b0dc48d47365b` | 2026-11-14 | Remove reward packs and automatic assignments |
| Private implementation | `a2897d907a616aec10b80ce241d1ea7c1190aa1b` | 2026-11-14 | Clarify daily and playtime reward pack setup |
| Private implementation | `1b08768f250cd0bc34bb23c5632be512f0f4f6a5` | 2026-11-14 | Fix Monitor+ config loading in Bifrost |
| Private implementation | `d336feaf943a5689d981d0b48362220968b95d33` | 2026-11-14 | Improve Monitor+ save interaction |
| Private implementation | `688295add8e76202312fee160584de84ac7ec431` | 2026-11-14 | Fix Monitor+ toggle rendering |
| Private implementation | `6489e849d0de65d8d11bfbb3534be97d8e54e49c` | 2026-11-15 | Fix Monitor+ channel ID settings save |
| Private implementation | `15685c144ef81f96cc3758e6a39cc97827dfc0c0` | 2026-11-15 | Auto-save Monitor+ settings |
| Private implementation | `313ed5ae74da56b44c1ff228927b09dd9cc21092` | 2026-11-15 | Fix Monitor+ refresh save race |
| Private implementation | `89b12c62247abc295bd9f29689ae3b3642205f87` | 2026-11-15 | Fix Monitor+ settings value reads |
| Private implementation | `1c76fcd360c33c887ead56da3a4d7db118270cde` | 2026-11-15 | Unblock Monitor+ legacy config saves |
| Private implementation | `8dd47466ec0c63c6f94ce3ba80b7b880c3ad9cb3` | 2026-11-15 | Remove Monitor+ legacy conflict path |
| Private implementation | `84451bc92287b665e456143d9ceb32b137d2335a` | 2026-11-15 | Move voting controls to Rewards |
| Private implementation | `65a6a8a2cf9beefe60547ebf0d7ba4651dcb1f76` | 2026-11-15 | Use one Discord gateway for rewards |
| Private implementation | `c085f3743670bc72f55db027a454c8efaf4a1cc3` | 2026-11-15 | Improve grid workspaces themes and host telemetry |
| Private implementation | `214129dd7274c2aadf6ff9f0bdf2c25da351a6b4` | 2026-11-15 | Require changelog updates for every change |
| Private implementation | `d0ec21bde847337d015006acb73f8f7dbc27cf51` | 2026-11-15 | Unify navigation and theme surfaces |
| Private implementation | `ca4bd5b4dd5858122c9b9ba81aa6a608c3864a3b` | 2026-11-15 | Add GridVault file manager tab |
| Private implementation | `53accab5de04c25355b2fef07c0a984f3c8f3b5a` | 2026-11-15 | Show installed version and commit in panel footer |
| Private implementation | `e5c31a01f2713df8f635c9fd4f4c6460034694c7` | 2026-11-15 | Package footer build identification release |
| Private implementation | `17573efabb1e6565d757ca00444a17e80df93eeb` | 2026-11-15 | Preserve vault breadcrumbs and page visibility |
| Private implementation | `3393652a3f3ccc6ca9a290504e1f8552d1970ce5` | 2026-11-15 | Package GridVault navigation correction |
| Private implementation | `d593c6abce67d1d0ada7a8938569a2a2f2821739` | 2026-11-15 | Improve Gridwatch spacing and metric layout |
| Private implementation | `ddf53271d8ebf7a8efabe402b49a5e08e6914b80` | 2026-11-15 | Package Gridwatch formatting update |
| Private implementation | `dca9e44001c724b83a847807625d341f79c76fa6` | 2026-11-15 | Add reward catalog groups and live block inspection |
| Private implementation | `0dad71e69586c41222c992da25d546c82d4d093a` | 2026-11-15 | Render live solid grid geometry |
| Private implementation | `87eee9d3401a9ce31d6ea8f07e2a7e4023728f6c` | 2026-11-15 | Preserve exact entity IDs in Gridwatch actions |
| Private implementation | `adb0d04b2d93a84fcc138352284b7b57d7d1fe18` | 2026-11-15 | Package exact grid ID correction |
| Private implementation | `aab5ca8dd006aad1a183031d9c27eb7f95cd81fe` | 2026-11-16 | Add interactive Gridwatch inspection and stabilize refresh |
| Private implementation | `c54a3568899e2c4ed27f0bb2f26e125fb9b1103b` | 2026-11-16 | Package Overseer v0.8.212 Gridwatch inspection |
| Private implementation | `70d015e744e2a15ed7acd69b2dd6a9dc73273cd8` | 2026-11-16 | Render installed ship models and textures with game conveyor ports |
| Private implementation | `25b150df188063ed29babc67f42e4684c3e361ad` | 2026-11-16 | Support installed archive assets and record conveyor render checks |
| Private implementation | `4d27ae0c2e60f35167700b9027868d19838692c1` | 2026-11-16 | Package Overseer v0.8.213 textured grid inspection |
| Private implementation | `dd26c2e26c65a7ba7f760201daf6e85febf66412` | 2026-11-16 | Add grid conveyor map and load progress |
| Private implementation | `46629dd1911ec8c56d7f1d1dce5ce685dff690e1` | 2026-11-16 | Package Overseer v0.8.214 grid inspection improvements |
| Private implementation | `4ba372353302eb6edff780a80fd884fbd39b2258` | 2026-11-16 | Add live ConveyorVis network diagnostics |
| Private implementation | `62765d5db9f5cb96cdfaec4206ff59cad0186081` | 2026-11-16 | Package Overseer v0.8.215 ConveyorVis |
| Private implementation | `e048983a635b9d4428604967eb15ce8767660c68` | 2026-11-16 | Add persistent grid inspector diagnostics |
| Private implementation | `a48a057bd2d1bc712cc3292607bed4bbb3a80668` | 2026-11-16 | Fix Grid Inspector DDS texture pipeline |
| Private implementation | `db5a7534dbcefc00ec0f40df460bf7600765fdfa` | 2026-11-16 | Update Overseer for Warfare 3 and TorchAPI 1.3.1.351 |
| Private implementation | `fa09a19873459dd34fe0c40fa7663403ad870e7f` | 2026-11-17 | Fix Grid Inspector active mod asset roots and isolate rejected models |
| Private implementation | `583963bd26acaf091e166edd756a26997f711144` | 2026-11-17 | Repair texture root lookup and DDS decoding; diagnose missing server textures |
| Private implementation | `f2534ea433895b04411c3f196cc95d519e593f40` | 2026-11-17 | Preload discovered grid textures and enable private DDS caching |
| Private implementation | `2a9bd52f44850af2a43f1bab1ea15cae926ee774` | 2026-11-17 | Add on-demand installed game texture source for missing server assets |
| Private implementation | `5a50e71678cdc1cba16b4e7a1c43ebe9b8124e56` | 2026-11-17 | Add private LAN texture hook with server streaming and bounded disk cache |
| Private implementation | `60860fc3a10ba66506c0150b509441065dc7be74` | 2026-11-17 | Update private texture firewall binding when the source interface changes |
| Private implementation | `3d229b398aa53d0269e003e9aba7b30b224fd0dd` | 2026-11-17 | Fix DDS transfers and redesign the Grid Inspector workspace |
| Private implementation | `7bc963506dc4712bb5163b27e45cf935bd053746` | 2026-11-17 | Scope grid inspection state and revisions to each selected entity |
| Private implementation | `dd4011dc2bd9c54367ca407943bee0c43985a79a` | 2026-11-17 | Rebuild Bifrost workspaces, scenic themes, profiles and role hierarchy |
| Private implementation | `0efe36674274a2b18f268eceb058ba3730c77bd1` | 2026-11-17 | Package verified Bifrost v0.8.230 dashboard and access release |
| Private implementation | `4709574f3f20fafbe2020336ab2c22a83e486158` | 2026-11-17 | Open legal documents in themed in-panel popups |
| Private implementation | `167a4aa29db27ebf48596f3c91a0aafc4c59ab4a` | 2026-11-17 | Package verified v0.8.231 legal document popups |
| Private implementation | `343df0c53fad990a42c31b7e1ec1858ba9b4a6f7` | 2026-11-17 | Fix preview backdrop routing and reject HTML asset fallbacks |
| Private implementation | `ea817389ec5b3aef982814b44224a570e0a2af95` | 2026-11-17 | Add responsive Command Center workspaces and automatic device appearance |
| Private implementation | `71ec22ac072e4789bc92d0e7421dfb80306b0229` | 2026-11-17 | Package verified v0.8.232 responsive Command Center release |
| Private implementation | `1cbb1a1bf5666aa6f5bd036b93cc9302a16d9f9f` | 2026-11-17 | Restore Nordic icons and optional backdrops; finalize legal document presentation |
| Private implementation | `43cec2a48e1151075334fd641b079b613e78ad3d` | 2026-11-17 | Package verified v0.8.233 optional backdrop release |
| Private implementation | `63c209c052d43f270503bc42a975dbe213a4a71d` | 2026-11-18 | Fix dense conveyor map readability and interactive selection |
| Private implementation | `fcec1af441e343b1137651991e9783c28c5b1fca` | 2026-11-18 | Package verified v0.8.234 conveyor map fix |
| Private implementation | `5de53c597f4ddb90d937eba5b9d05c3321cb736b` | 2026-11-18 | Render grid geometry while DDS materials stream |
| Private implementation | `23638443af27d12b6054388bcb978d581658939e` | 2026-11-18 | Package v0.8.235 faster Grid Inspector |
| Private implementation | `799a0090e45a4de5fddcd4bd6c580fad841b2a12` | 2026-11-18 | Restore WebGL buffer uploads in Grid Inspector |
| Private implementation | `72a94ddb03a0c34491deefe1ea8060ff6d45ef9b` | 2026-11-18 | Package v0.8.236 Grid Renderer hotfix |
| Private implementation | `eb36b1338157953a3ced2fb01cdfcecbe6ec804f` | 2026-11-18 | Refresh Bifrost Command Center and plugin inventory |
| Private implementation | `5c2d849e3b4a33028189d657a64be97cf9853043` | 2026-11-18 | Package v0.8.237 Command Center refresh |
| Private implementation | `58ecc2eb4d440111cd579e94d79089f269580b60` | 2026-11-18 | Unify Bifrost menus and add global panel search |
| Private implementation | `804b7bc80f0010bd9e87ea718449a5c3078f50e2` | 2026-11-18 | Package v0.8.238 global search and navigation |
| Private implementation | `bf02d1ee03ac7921aef5cf998473a4c018681212` | 2026-11-21 | Release v0.8.242 Grid Inspector review workspace and conveyor maps |
| Private implementation | `ce42c7f63365d8f91e33f73023c805d7419033b5` | 2026-11-21 | Record verified v0.8.242 release package and checksum |
| Private implementation | `e4d12295746a5b8e71337cd5ba04a9e161ef3ac0` | 2026-11-21 | Fix large-grid capture stalls and false panel sign-outs in v0.8.243 |
| Private implementation | `9af18f4006f3c03bf81cb3cf1be326ed51d50ffd` | 2026-11-21 | Record verified v0.8.243 hotfix package and checksum |
| Private implementation | `29862994859a42308c842702c8c31d08279b2de1` | 2026-11-21 | Rebuild Monitor+ owner workspace and separate rewards in v0.8.244 |
| Private implementation | `293eff261a42e938a802b985cba40182852dd5c2` | 2026-11-21 | Package verified Monitor Plus v0.8.244 release |
| Private implementation | `0ddc9aee2cad026b7867bb31e53cf9025ec12c3e` | 2026-11-21 | Rebuild Rewards and Voting around focused workflows in v0.8.245 |
| Private implementation | `8fd3111bb70b1d0d729a8a65b977a405ba6989d8` | 2026-11-21 | Package verified Rewards workspace v0.8.245 release |
| Private implementation | `7aff9ee7c51092d3f6545b1a239e80e936f41e41` | 2026-11-21 | Fix Monitor administrator link persistence and inline confirmation |
| Private implementation | `2d34dc5ad87c3249c8348da34c796bd3aa901052` | 2026-11-21 | Package verified Overseer v0.8.246 administrator link fix |
| Private implementation | `b1d00a921808f46670237ac1541e1d52f6373821` | 2026-11-21 | Verify administrator command access activates immediately after Add |
| Private implementation | `6e113fc9fb2d686b11b0767cb10405c665931240` | 2026-11-23 | Fix Monitor Discord heartbeat recovery and add bot reload failsafe |
| Private implementation | `b8ffb3e90ee00ab1602fb7c9468203f9cebe887a` | 2026-11-23 | Package verified Overseer v0.8.247 Discord recovery release |
| Private implementation | `f88e461a4fa5dcacefb1a164593f3118716619bb` | 2026-11-24 | Add measured grid diagnostic capture and red 3D fault overlays |
| Private implementation | `696c9b2176b0da0b3ed191fb41c5807feaeb32bf` | 2026-11-24 | Package verified Overseer v0.8.248 diagnostic capture release |
| Private implementation | `df1b1f624405db81b39df579e6cbc26582d061bd` | 2026-11-24 | Merge private main documentation preserving current recovery behavior |
| Private implementation | `5eb9211052b9dd91138460e575ad51d883a0145d` | 2026-11-24 | Add Overseer v0.8.249 FAULT World Radar |
| Private implementation | `d2739a3160b8b898ed36fb56cf2c548cafeba902` | 2026-11-24 | Package verified Overseer v0.8.249 FAULT World Radar |
| Private implementation | `ff111b7f7a92cb4eaae7df5fdba8cd058a9b5961` | 2026-11-24 | Add Overseer v0.8.250 Server Flight Recorder |
| Private implementation | `eb0e93677bb31d827fdb3c4f0f68130f6d31ad2b` | 2026-11-24 | Package verified Overseer v0.8.250 Server Flight Recorder |
| Private implementation | `a166726acf493b1397c728e9bc0fcf66108d34ce` | 2026-11-24 | Add Overseer v0.8.251 Incident Investigation |
| Private implementation | `2796009b1821fcf4db9a6cd8ec8790c5b8fdc046` | 2026-11-24 | Package verified Overseer v0.8.251 Incident Investigation |
| Private implementation | `8ef793050359f8050b594b14e3473986287ccc6a` | 2026-11-24 | Add Overseer v0.8.252 Before and After Diagnostics |
| Private implementation | `7aded7d7aa0739bac29dbdfefd2eeb56e95fdfdd` | 2026-11-24 | Package verified Overseer v0.8.252 Before and After Diagnostics |
| Private implementation | `aeee72aa61b756d2dc24e5b728e32d3655573e36` | 2026-11-24 | Add Overseer v0.8.253 Observed Grid History |
| Private implementation | `aa8c1dfead994b4263372cfe3e5c827c8a054d9d` | 2026-11-24 | Package verified Overseer v0.8.253 Observed Grid History |
| Private implementation | `cb82a04dbfc4012bbffe2ec7e4bf5856799e5b7f` | 2026-11-24 | Add Overseer v0.8.254 Player Investigation |
| Private implementation | `ef952418ca037f359d1fa440d66c5f6732621d61` | 2026-11-24 | Package verified Overseer v0.8.254 Player Investigation |
| Private implementation | `0b857143b1089246c10c331c1bd93718b1427747` | 2026-11-24 | Add Overseer v0.8.255 Guided Troubleshooting |
| Private implementation | `44d8dbaac5481e2943efdbaba58897d5e090d827` | 2026-11-24 | Package verified Overseer v0.8.255 Guided Troubleshooting |
| Private implementation | `740802afabc04879868ac0eb13e5881c555f80e1` | 2026-11-24 | Add Overseer v0.8.256 Backup File Verification |
| Private implementation | `25d7dd29f54702e033f17cb97c89abcd88d213b6` | 2026-11-24 | Package verified Overseer v0.8.256 Backup File Verification |
| Private implementation | `94577dc607417f6a8afc61374baa3ebc135e64ba` | 2026-11-24 | Add Overseer v0.8.257 Plugin and Mod Compatibility |
| Private implementation | `a7474be4950cdcbd3f70ffb78b72044b63aaa626` | 2026-11-24 | Package verified Overseer v0.8.257 Plugin and Mod Compatibility |
| Private implementation | `1c2443081da80f5149e3324f42f3683397b05d34` | 2026-11-24 | Add Overseer v0.8.258 Operational Job Center |
| Private implementation | `e57b25a74782598ad11e6d69caba2335b768da79` | 2026-11-24 | Package verified Overseer v0.8.258 Operational Job Center |
| Private implementation | `a4472929cc938e9b75d82a8c7607323e22d788db` | 2026-11-24 | Add Overseer v0.8.259 Sanitized Support Bundles |
| Private implementation | `219fe7f27b532c19d92e626f9e97a324a1716904` | 2026-11-24 | Package verified Overseer v0.8.259 Sanitized Support Bundles |
| Private implementation | `4dfd017f7a617dd326196823b7dec8a2e1bdf5e4` | 2026-11-24 | Index all eleven verified operations toolkit feature ZIPs |
| Private implementation | `ffd29bd178faa62350763724844274fa64ea0d22` | 2026-11-24 | Add Overseer v0.8.260 Operations Toolkit Integration |
| Private implementation | `48360f08dd4e8755434216aa3f65ee3ccad09d08` | 2026-11-24 | Package verified Overseer v0.8.260 Operations Toolkit Integration |
| Private implementation | `cf13c3727c0c86da8a52a09cd15645118abf26a0` | 2026-11-24 | Index cumulative v0.8.260 toolkit delivery bundle |
| Private implementation | `abdf13ecc789e6d35436733474e2231affbd3506` | 2026-11-24 | Add Overseer v0.8.261 Simulation Chronicle |
| Private implementation | `0ef5b4e727605b592fa35dff0df5091ad80c5f7a` | 2026-11-24 | Package verified Overseer v0.8.261 Simulation Chronicle |
| Private implementation | `47da180a1832e70301cdc554abd3ffcebfc856b5` | 2026-11-24 | Add Overseer v0.8.262 Server Monitor |
| Private implementation | `1046f91a6e8a62793ac66092c86192a1de70f006` | 2026-11-24 | Package verified Overseer v0.8.262 Server Monitor |
| Private implementation | `150a126233fa307abe483b481c8d8b2212be9f79` | 2026-11-24 | Add Overseer v0.8.263 World Radar Auto Load |
| Private implementation | `6cc8800e8657339486418042d15f191ec72cf6f6` | 2026-11-24 | Package verified Overseer v0.8.263 World Radar Auto Load |
| Private implementation | `983e37e839277c57ec94c7c96ee4cc69da0f2e6b` | 2026-11-24 | Add Overseer v0.8.264 Live Observe Dashboards |
| Private implementation | `a4409c9de4efdb60fb3bc52b7031afede112942d` | 2026-11-24 | Package verified Overseer v0.8.264 Live Observe Dashboards |
| Private implementation | `d1f945a459ea259bdbf9b45705c8da2799811008` | 2026-11-24 | Add Overseer v0.8.265 Interactive Monitor Drilldown |
| Private implementation | `de99453b4f3e8d16e3d912d6dafcf17f64982f2c` | 2026-11-24 | Package verified Overseer v0.8.265 Interactive Monitor Drilldown |
| Public documentation | `dec7af8d3828777816483be6c2161eb15087846d` | 2026-09-20 | docs: public documentation for TROA Admin+ (Overseer) |
| Public documentation | `382e2d8d5470f35f8658a5b4325e874a0c4c4515` | 2026-09-20 | docs: point changelog links to the public repo |
| Public documentation | `a0443acb5a264e9f5c491c48dc64ee096ed84b8f` | 2026-09-20 | docs: document safe Torch plugin packaging |
| Public documentation | `36f19abc7b6e5872192516588c09e7bd548ed9b4` | 2026-09-20 | docs: add versioned release archive index |
| Public documentation | `a09437bceac9551ad792d28756b97ec365ba33e5` | 2026-09-20 | docs: publish v0.7.2 startup dependency fix |
| Public documentation | `1eafe1e33a964ec135870e2113c7549edc5b5a22` | 2026-09-20 | docs: publish v0.7.3 release index |
| Public documentation | `e297cb5ba275a684517f2b9731a96efe72c8ba05` | 2026-09-20 | docs: publish v0.7.4 single DLL release |
| Public documentation | `9e55dbfd4a46f675d0d526de9352df8a4c7f1add` | 2026-09-20 | docs: use TROA Admin Overseer data folder naming |
| Public documentation | `a318732f712fb8f89dbef320d2305bda45c629d8` | 2026-09-20 | docs: document simple webhook defaults |
| Public documentation | `627d22d3a349ff9c3e30bdc2f44d869b5f9d3f59` | 2026-09-20 | docs: publish v0.8.0 command root split |
| Public documentation | `a7a04fc3340cd04e9bcf62fad33c4e34f7ea2603` | 2026-09-20 | docs: publish v0.8.1 safe grid workflow |
| Public documentation | `fd94d5507622c1a2ddb4ebc64039a0497e84c8a8` | 2026-09-20 | docs: publish v0.8.2 managed persistence |
| Public documentation | `b64ee1c9bb389eb553c72bdd441450b5ba9c6889` | 2026-09-20 | docs: publish v0.8.3 moderation workflows |
| Public documentation | `078de1309d1526e4667a73ba5f0e8e0b3c2a211d` | 2026-09-20 | docs: publish v0.8.4 owner operations |
| Public documentation | `51a8739fc5620db69881fdecc7133273254a91cf` | 2026-09-20 | docs: publish v0.8.5 config migration |
| Public documentation | `57a27d5321e5cb65e869c099eb358f46ae5303e8` | 2026-09-20 | docs: publish v0.8.6 command contract |
| Public documentation | `32c9d644eb6cd2586b9f106a84386f98029ef496` | 2026-09-20 | docs: publish v0.8.7 audit history |
| Public documentation | `7fa389d49704d9c29e323da077c469bfe963ec39` | 2026-09-20 | docs: publish v0.8.8 player history |
| Public documentation | `7ed494af156cd51bb98b6da555bc02fd84c720f9` | 2026-09-20 | docs: publish v0.8.9 command migration |
| Public documentation | `5bf009953081128d0dd2e4a9ebe15f9615d4258c` | 2026-09-20 | docs: publish complete server owner guide |
| Public documentation | `d06e0e1c187073c46a79267ca0c34b61f3d8aecb` | 2026-09-20 | docs: publish v0.8.12 ticket portal |
| Public documentation | `c59a2209894a20723e2506d6f167a5bc77a345d3` | 2026-09-20 | docs: publish v0.8.13 rewards and limits |
| Public documentation | `9983234069d30905ba754e41136411d18cebca83` | 2026-09-20 | Revise CHANGELOG.md for clarity and updates |
| Public documentation | `4ea226f42f7153cd992e41d084cfda54091e72a0` | 2026-09-20 | Revise changelog header and structure |
| Public documentation | `99f2340fe55395dae760fbabd12d5f9a84ad6722` | 2026-09-21 | docs: publish v0.8.14 configuration doctor |
| Public documentation | `34a7825ada4682541a89a66c1cd8687537dbe9e7` | 2026-09-21 | docs: publish v0.8.15 grid health scanner |
| Public documentation | `a758a347c58250472f6ba51d77a444b22bbe6623` | 2026-09-21 | docs: publish v0.8.16 staff case summary |
| Public documentation | `6885c81c4230d4e80c3347e8054ec8a3bb701495` | 2026-09-21 | docs: publish v0.8.17 player audit trail |
| Public documentation | `04100c3d851ada7b08e3da7077fd64672a9078c1` | 2026-09-21 | Update CHANGELOG.md |
| Public documentation | `b37e3f642b863b519cb863ed112c82fdafe1370a` | 2026-09-21 | docs: publish v0.8.18 correlated moderation audit |
| Public documentation | `cba2d6b437c433adbe65f4c6da19ac6cf4767c57` | 2026-09-21 | docs: publish v0.8.19 resolved report audit |
| Public documentation | `4b8c7854eebfc7cc9ac5c8cbdece459d9c208dac` | 2026-09-21 | docs: publish v0.8.20 player grid recovery |
| Public documentation | `4cb402454294a7ce3577cec82a3ff436ce7b64c5` | 2026-09-21 | Revise CHANGELOG.md for recent updates |
| Public documentation | `81ae00231bd0a3f675de91eecc0ff8ccbf7886b9` | 2026-09-21 | docs: publish v0.8.21 configurable PCU cap |
| Public documentation | `0210e4255b01db8c65cbeb1ccae5692ebcd104a0` | 2026-09-21 | docs: publish v0.8.22 advanced role inheritance |
| Public documentation | `fb90076156424fa4f1ef99f11ac583d210b43267` | 2026-09-21 | Update CHANGELOG.md |
| Public documentation | `7c8622327a6f3b5136f6c3d0402f20e86d93dc4a` | 2026-09-21 | docs: publish v0.8.23 temporary role grants |
| Public documentation | `4a1c07dc22dc0a586a735f6bfc934b20f5a3c0bd` | 2026-09-21 | Document v0.8.24 Discord role mappings |
| Public documentation | `415597c001347771d07c2d2e4749b52089c8a8b0` | 2026-09-21 | Index v0.8.24 public release |
| Public documentation | `d82f9522a55f40bd286d068fc9ddde07a59930ae` | 2026-09-21 | Document v0.8.25 context-aware limits |
| Public documentation | `c1ef4c3115e499e6536dde23c0370c1d5c4015fb` | 2026-09-21 | Update CHANGELOG.md |
| Public documentation | `fdcd9501b230a7bdb13d87f9e0c211748a7af9de` | 2026-09-21 | Document v0.8.26 live limit preview |
| Public documentation | `c61d4d72d1c3f678f3a4487a0bf683ab891a851b` | 2026-09-21 | Preserve changelog heading |
| Public documentation | `b4c1f3843ef5d21092acd2ccbc48987ad3ed76d4` | 2026-09-21 | Document v0.8.27 complete block catalog |
| Public documentation | `03436d5a44650c1bbd2c2a31e531e5d88a36e919` | 2026-09-21 | Document v0.8.28 role templates |
| Public documentation | `2233e0f336f7c22ca5c91e03af832b0dac454162` | 2026-09-21 | Document v0.8.29 scoped permissions |
| Public documentation | `da42ec140777b35aacb1a4c452f09314a59ac6bb` | 2026-09-21 | Update CHANGELOG.md |
| Public documentation | `356535aa8383827e1a0ece52627ae7a2ed8f0590` | 2026-09-21 | Document v0.8.30 policy enforcement |
| Public documentation | `31c741e9f81a2f728861cef7cd509dc688d62dcc` | 2026-09-21 | Update README.md |
| Public documentation | `a2d18883fb70ccf94f2b810c090c0f2dc85ee5d3` | 2026-09-21 | Update README title for testing group clarification |
| Public documentation | `1a1652def79705cd6882f57e72e6adc8bdc64e25` | 2026-09-21 | docs: publish two-staff transfer approval guidance |
| Public documentation | `9fa2f54a8b7c7a8fe73e5e564d61ddb7a36c5687` | 2026-09-21 | docs: publish staff case workflow |
| Public documentation | `478b17da96fc7f36e6e0fc526f9004d0a08cf4e4` | 2026-09-21 | docs: publish staff case queue |
| Public documentation | `8a494c493d6b710f435ad0685f07b7062971c0fc` | 2026-09-21 | docs: publish expanded policy enforcement |
| Public documentation | `144292c1321aea7de182f7264bb9e6e4993b8fa7` | 2026-09-21 | docs: publish role comparison |
| Public documentation | `2b86cf7c0651c934ae81f75eabaeb9a75b2493b5` | 2026-09-21 | docs: publish operations summary |
| Public documentation | `c40d4ef0b2dfcf793d10fb87094e970376d71d4f` | 2026-09-21 | docs: publish faction dossier |
| Public documentation | `9068bfab36be3991ad4ce7da37e65453a6608a72` | 2026-09-21 | docs: publish faction roster |
| Public documentation | `7af542652272eb169c162d7627d311d3e7726130` | 2026-09-21 | docs: publish event operations |
| Public documentation | `a98e79f65834e77af30a1b3ca4e2860e8d9638ff` | 2026-09-21 | docs: publish event participants |
| Public documentation | `51dbcb1d37d2dbe2a78566a4a36e249128acdc7f` | 2026-09-21 | docs: publish event motd and rewards |
| Public documentation | `2337d4fe22e65aae50ceb5c4a8af24fa9bdb2f42` | 2026-09-21 | docs: publish maintenance mode |
| Public documentation | `d167cfe9bf5b3cfc1758ba17b294dd45c64cb4f4` | 2026-09-21 | docs: publish scheduled operations summaries |
| Public documentation | `99694d01aa64cf8c29a5c0ffcf8c1148a7a185e4` | 2026-09-21 | docs: consolidate release index |
| Public documentation | `6eec9efdbaffc60c7aef574a1804b1e344073964` | 2026-09-21 | docs: publish event attendee export |
| Public documentation | `aaf1faa925719aae3c13ab55d00422520723645d` | 2026-09-21 | docs: rewrite owner how-to and consolidate daily changelog |
| Public documentation | `ee6b0ab39ca887f055f139fd697015a7cb81c54c` | 2026-09-21 | docs: document automatic block catalog |
| Public documentation | `5643be2de1abf8e794673c4d4d999db83ca7c3a8` | 2026-09-21 | docs: correct block catalog data path |
| Public documentation | `724480a095797e4aebfd0a268510587b4ef31b7b` | 2026-09-21 | docs: fix catalogue formatting |
| Public documentation | `3f59175b5b0968e8c3310892725450ee393389b1` | 2026-09-21 | docs: complete v0.8.49 owner guidance |
| Public documentation | `812b604e01ebba45e5606a1875d54106606cb714` | 2026-09-21 | docs: index v0.8.49 release |
| Public documentation | `87d56e7e1b5504331cd5cc778fb4487968377017` | 2026-09-24 | Harden public repository privacy boundary |
| Public documentation | `db67abaa84ff624e98d496c623ffa601deb30314` | 2026-09-28 | docs: publish TROA Admin Overseer v0.8.51 notes |
| Public documentation | `42b4e7cf534e74d4306eeff6850914c7118e6836` | 2026-09-28 | docs: clarify plugin ownership and Discord passthrough |
| Public documentation | `bf230714f682f0bd3cf7acb0fc1cf862d7d01a61` | 2026-09-28 | docs: explain webhook config recovery in v0.8.52 |
| Public documentation | `46cfb1873152c7a3bd11692219f0959509d697f6` | 2026-09-28 | docs: add safe webhook config example |
| Public documentation | `4cf384ec7e841c962f6bb0ff4bef978119ac22d0` | 2026-09-28 | docs: publish complete v0.8.52 config examples |
| Public documentation | `dc62130fd6bd1d3362e1ddf029f254f12dc8f265` | 2026-09-28 | docs: document save-confirmed admin restart |
| Public documentation | `1c39c79712ffbbea7fc844dbef4c47f61c9f9ce1` | 2026-09-28 | Document v0.8.54 restart confirmation |
| Public documentation | `4644a2b5cc368e41bbdc4bf6d6bff05194d81337` | 2026-09-28 | Correct v0.8.54 package hash |
| Public documentation | `fc0edf8f3ce94effe63c9d81187f08084b60ee79` | 2026-09-29 | docs: document v0.8.55 restart countdown |
| Public documentation | `f7acb1f4061fc2c94a686d0797e47fb700be550a` | 2026-09-30 | docs: update Admin Overseer v0.8.56 rewards |
| Public documentation | `22ab3ae84f2e2c3862854ab5e39ce7a0ee6c74da` | 2026-10-03 | Link Overseer README to manuals |
| Public documentation | `8a4afd3370570b32e6bdca333614f4c476a702e0` | 2026-10-06 | docs: add detailed plugin operator guides |
| Public documentation | `fe2b025bc52f845cca29accd5acdcf9d4c844b33` | 2026-10-08 | docs: document Bifrost Panel candidate |
| Public documentation | `8066c73bd4bb076ae67e29ff2b6244b20f26a812` | 2026-10-08 | Document Bifrost panel access and webserver config |
| Public documentation | `b1218ef743378e9a3a7891a59ed84b84897dcf37` | 2026-10-08 | Document Bifrost plugin workspaces and command console |
| Public documentation | `d2c4bf84d6ba3c378ddb65151c888a4d6e1543fd` | 2026-10-08 | docs: publish Bifrost dashboard changelog |
| Public documentation | `69f25f41281e986fd8792217673d4567a602136a` | 2026-10-09 | docs: add Bifrost Plugin Panel guide |
| Public documentation | `eaac5b2b1f027bb6e2d73dddabe6ea8c3ab3f044` | 2026-10-09 | docs: publish Bifrost Plugin Panel contract |
| Public documentation | `79a67d70c7f783d39151f8951464d1a7177bc907` | 2026-10-09 | docs: add Bifrost Plugin Panel connection guide |
| Public documentation | `f58036529209b75d2af812894b375dc11038b643` | 2026-10-09 | docs: document Bifrost Plugin Panel guidance |
| Public documentation | `1a5808b60ac5da3576752b6d440543105aed1c6d` | 2026-10-09 | docs: link Bifrost Plugin Panel guide |
| Public documentation | `fccdd61347f98c3afc559ff601cc565186309b35` | 2026-10-10 | docs: add Bifrost legal information drafts |
| Public documentation | `07ac8b1ecd32e3ec4878b337bb917b9cab4e30b5` | 2026-10-10 | docs: add Bifrost legal information drafts |
| Public documentation | `3220ce3d6443aae3f756f223a08e7dafcf47176c` | 2026-10-10 | docs: add Bifrost Panel terms draft |
| Public documentation | `9031e13dd80f60f79942591de21eb66e096e76f6` | 2026-10-10 | docs: add Bifrost Panel privacy draft |
| Public documentation | `fa0427dc6aecf4c409627874123d7583c6af6bbc` | 2026-10-10 | docs: add Bifrost legal info candidate changelog |
| Public documentation | `15f575c99c9e38e1f5306206e5a0c54622e0967f` | 2026-10-10 | docs: add repository context and work log |
| Public documentation | `dabb0d118072338c72c5d0ec0dba45293392b7d5` | 2026-10-10 | docs: add repository context and work log |
| Public documentation | `e426af0e8cf2513e135691e9166a987b0e6e76cb` | 2026-10-10 | docs: add repository context and work log |
| Public documentation | `d54bedf18b5804bf737de315f9c5224b8f130ad8` | 2026-10-29 | docs: note pending restart coordination candidate |
| Public documentation | `b8231be648ff1244bc775e3304d02d994d8b5b97` | 2026-10-29 | docs: record built restart candidate and Linux Wine caveat |
| Public documentation | `7356e49d1950d969157e962b2714e8c80cbb524f` | 2026-10-29 | docs: document aligned Overseer v0.8.93 candidate |
| Public documentation | `319da1d03256a875e491aeff0aacc08a1a5e3e32` | 2026-10-29 | docs: record private v0.8.93 mirror sync |
| Public documentation | `d02131f767b17073f03826b4999109ec489e62f3` | 2026-10-29 | docs: clarify public restart coordination candidate |
| Public documentation | `1d32fc3fd3d24bb2bbae94e962400caea1628922` | 2026-10-29 | docs: keep private prototype details out of public notes |
| Public documentation | `26091f9ee18ef65fba93cdba5e2fc04e28280216` | 2026-10-29 | Document Admin Overseer v0.8.93 release |
| Public documentation | `11b7b2a3d259fa98b619aac74e5442a250966113` | 2026-10-29 | Update CHANGELOG for v0.8.93 enhancements |
| Public documentation | `66a751d3b5bcc48c639dc670c16c2fb1086b9e07` | 2026-10-29 | Expand block limits starter policy |
| Public documentation | `8345c09467b3d76f8e628055f18ba240e9de71a8` | 2026-10-29 | docs: add Bifrost v0.8.94 public candidate notes |
| Public documentation | `c625fe26c33eed8de7653ac3ee78ccbc75e5eb74` | 2026-10-29 | Update CHANGELOG.md |
| Public documentation | `de4fe625642f7342edef25dd7745e3bed976c757` | 2026-10-29 | Document v0.8.95 Core Controller release |
| Public documentation | `a455c50a50dc0f3b168958821f409b755480c300` | 2026-10-29 | Merge remote release notes with v0.8.95 docs |
| Public documentation | `fa313e7256ad772997aee4e52a718ecff395d0c4` | 2026-10-29 | Update CHANGELOG for v0.8.95 release |
| Public documentation | `84a43aa19278a3c705af1e2aa3e58859400161a8` | 2026-10-29 | Document v0.8.96 CPU topology map |
| Public documentation | `58d00b07f23108c21882852c58d02991193c7905` | 2026-10-29 | Merge public v0.8.95 changelog update with v0.8.96 docs |
| Public documentation | `aa475cab6d70723704c8a2e98f0e464b26057688` | 2026-10-29 | Refresh v0.8.96 package fingerprint |
| Public documentation | `ede552edafcd8e670f61d1440beddf1011822a41` | 2026-10-30 | Document v0.8.97 Core Controller request fix |
| Public documentation | `f512f9e6fb878e899f880eecca45e5da9d30099f` | 2026-10-30 | Document Core Controller on-off controls in v0.8.98 |
| Public documentation | `38f5cfe15d36ee2476f875b40ae9cd18a2b1bee0` | 2026-10-30 | Document Bifrost v0.8.99 operations timeline |
| Public documentation | `2cd483a7de6a49bc02a4a47267239e43397e9fd3` | 2026-10-30 | Publish Bifrost phases 1-5 and release packages |
| Public documentation | `c25b01017087f06222358796f47ca9ae22ff3715` | 2026-10-30 | Refresh Bifrost public preview gallery |
| Public documentation | `80935a5e4a6427d38b601756023037f21fc32aa0` | 2026-11-01 | Release Overseer v0.8.140 block limits activation fix |
| Public documentation | `6276464cf9205d6f44b2792d4883c2c333584fec` | 2026-11-01 | Publish v0.8.141 Gridwatch telemetry release |
| Public documentation | `fbb7772691fa189728cec5d6539ff1e548034ab2` | 2026-11-01 | Publish v0.8.142 Gridwatch pressure triage |
| Public documentation | `176876e972dd0d99bb44b183d913eb26e615c43f` | 2026-11-01 | Publish v0.8.143 plugin configs workspace |
| Public documentation | `06876fe5566fa697bebfaf87e9708bebbc475651` | 2026-11-01 | Publish v0.8.144 config dialog polish |
| Public documentation | `426e64747356ba03d74af4eab822e71cd2c2464c` | 2026-11-01 | Publish v0.8.145 Gridwatch card layout fix |
| Public documentation | `2c2687d94222e0596e2748edcae41e43efe2b247` | 2026-11-01 | Publish v0.8.146 Gridwatch dossier redesign |
| Public documentation | `715a632fad62f3f71a9c3057ed2a71c9f583e438` | 2026-11-01 | Publish v0.8.147 Gridwatch style preview fix |
| Public documentation | `3c199c3a12ea10759d79fe164dc8ae72f286a977` | 2026-11-02 | Document Overseer v0.8.148 Gridwatch queue redesign |
| Public documentation | `449b08c0bbed3cd7d2f678a68302c1b01486528f` | 2026-11-14 | Document every Overseer command and permission |
| Private implementation | `cc17afaaa5ed62929679b7a71890b0a088c6d89d` | 2026-11-24 | Add Overseer v0.8.266 Interactive Visual Dashboards |
| Private implementation | `3a8898ce5c57e4da52e70d2056bff8f497012779` | 2026-11-24 | Package verified Overseer v0.8.266 Interactive Visual Dashboards |
| Private implementation | `bb1e08a80d96f3bf066e4735eb01291c2b06351c` | 2026-11-24 | Record local Docker dashboard delivery and release commit index |

## Latest implementation commit index

| History | Commit | Date | Change |
| --- | --- | --- | --- |
| Private implementation | `1610f2fa1bced1e2dd5ba5a77e19a95d43970933` | 2026-11-24 | Add Overseer v0.8.267 Verified Session Reconnection |
| Private implementation | `ce4ec26db7f57763b416d21d6d1d53c83d8836e8` | 2026-11-24 | Package verified Overseer v0.8.267 Verified Session Reconnection |
| Private implementation | `c7c03f3c741a3ba21c19941fa27a3b4b80fa2d60` | 2026-11-24 | Add Overseer v0.8.267 Verified Session Reconnection |
| Private implementation | `1fd3088f7e44c4bc57999216d68159c5667d9594` | 2026-11-24 | Package verified Overseer v0.8.267 Verified Session Reconnection |

## v0.8.268 implementation commit index

Index is through the listed predecessor commits; the current public documentation commit cannot include its own hash.

| History | Commit | Date | Change |
| --- | --- | --- | --- |
| Private implementation | `a89e353d48f32af59d083fcb278cefd1fc969405` | 2026-11-24 | Record v0.8.268 dataset explorer validation and release index |
| Private implementation | `b5b4de2fd0005aae388b408214695999e734cd44` | 2026-11-24 | Package verified Overseer v0.8.268 Interactive Dataset Explorer |
| Private implementation | `87a5deef73b2e49daf1d3d05c4fefd641ca59057` | 2026-11-24 | Add Overseer v0.8.268 Interactive Dataset Explorer |
| Private implementation | `ea57b42a17440186f051ce35c5b2ca210fa8fc14` | 2026-11-24 | Record actual-server monitor validation and recovery package history |
| Public documentation | `1b5dc3e` | 2026-11-24 | Document verified session recovery and real-data monitor checks |
