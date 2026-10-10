# Work log
## 2026-10-10 — Bifrost legal information drafts and v0.8.89 candidate

- Added public deployment-template Terms and Privacy & GDPR documents; linked them from the operator guide and root README.
- Documented the candidate's unauthenticated legal routes and sign-in/footer links; current public binary does not include this UI behavior.
- Clearly marked the documents as deployment/counsel review drafts and avoided a compliance claim. No candidate binary or private source was added to the public repository.

## 2026-10-08 — Bifrost v0.8.60 local candidate
- Built Admin Overseer Release with 0 warnings and 0 errors. Package verification confirmed version 0.8.60 and exactly `Overseer.dll` plus `manifest.xml`.
- Copied package and `TROA Admin Overseer Webserver.cfg.example` to the local release folder. Package SHA-256: `C3EB4BBD1630A17CD4B048DB2B2F8AE6DCAC1AEB0A21778133A678D1F9F24AA6`.
- Added TROA-only config workspaces and a searchable command console using Torch command registration/execution; Admin/Owner access is role-gated and each run is attributed in the Torch log. Updated public candidate documentation, role access, masked secrets, and live metrics.
- GitHub release publication and dedicated Torch runtime acceptance remain pending.

## 2026-10-06 — Public ownership and roadmap correction

- Clarified the restart boundary: Admin Overseer runs its own save-confirmed restart; Monitor+ provides optional authorized command transport; Cleaner+ owns cleanup scheduling.
- Updated public roadmap and README without presenting private v0.8.57 work as released. Public release documentation remains v0.8.56.
- No source or package changed; dedicated-server runtime acceptance remains separate.

## 2026-09-28 — v0.8.54 restart confirmation
- Built v0.8.54 with 0 warnings and 0 errors; package passed `verify-release.ps1` and contains only `Overseer.dll` and `manifest.xml`.
- Copied `TROA Admin Overseer v0.8.54 - Restart and Save Confirmation.zip` to the local release folder; SHA-256 `4606ABF906D072187A1D560F0607F67AAE02F3D6BFD7A9EC54A77E5BBCEA3E6A`.
- Torch-console ANSI rendering and Discord webhook delivery require dedicated-server runtime acceptance.

- 2026-09-28: Updated the public ownership contract for Monitor+ command transport and plugin-owned command/webhook delivery.
- 2026-09-28: Rebuilt v0.8.51 with 0 warnings and verified the single-DLL package; SHA-256 CE11629550CCA0E9CF462A39582A63A4E57B8A2703D7CC47731C1155D28BF6FC. Dedicated-server runtime acceptance remains separate.

- 2026-09-28: Published public-safe v0.8.51 configuration guidance. Local package `TROA Admin Overseer v0.8.51 - XML Configuration Repair.zip` passed validation with only `Overseer.dll` and `manifest.xml`; SHA-256 `CE11629550CCA0E9CF462A39582A63A4E57B8A2703D7CC47731C1155D28BF6FC`.
- Config smoke checks passed for empty defaults, populated/repaired Rewards and Webhooks files, list replacement, and repeat loads. Build had two NU1900 warnings because NuGet's vulnerability feed was unreachable; dedicated-server runtime acceptance remains pending.

- 2026-09-27: Updated public v0.8.50 reward, Discord, command, configuration, deployment, permissions, and release-index guidance for the Monitor+ rewards migration. The single-DLL package passed ZIP validation; dedicated-server runtime acceptance remains pending.

- 2026-09-20: Established single-DLL release validation and paired private/public publication workflow.
- 2026-09-20: Published v0.8.11: access correction, documentation refresh, and validated release workflow.
## v0.8.16 — Staff case summary
- Added !ova case <player> backed by persisted moderation records.
- Removed the obsolete SQLite package reference; release remains one managed DLL plus manifest.

## v0.8.17 — Player audit trail
- Added !ova caseevents <player> [count], capped at 25 SteamID-matched persisted events.

## v0.8.18 — Correlated moderation audit
- Added target SteamID fields to mute, unmute, staff-note, and player-report events.

## v0.8.19 — Resolved report audit link
- Report resolution now returns the resolved record internally and emits its target SteamID.

## v0.8.20 — Player grid recovery
- Added owned-grid !ov fixship, !ov stop, and !ov gridcheck with major-owner, cooldown, block-cap, and audit safeguards.

## v0.8.21 — Configurable player PCU cap
- Replaced the recovery block cap with `PlayerGridToolsMaxPcu`; gridcheck now reports group PCU.
## v0.8.22 — Advanced role inheritance
- Added parent-role persistence, effective role resolution, cycle protection, and permission inspection.
## v0.8.23 — Temporary role grants
- Added durable timed role assignment, automatic expiry, rank recalculation, and audit trail.
## v0.8.24 — Role presentation and Discord mappings
- Added durable prefix/color role presentation plus audited Discord role-ID mapping commands; no Discord credential or automatic access grant is introduced.
## v0.8.25 — Context-aware block limits
- Added per-rule grid kind/size filters, current-world CSV subtype export, and player NEAR/OVER context feedback.
## v0.8.26 — Live limit preview
- Added read-only administrator and player grid-limit feedback commands.
## v0.8.27 — Complete block catalog export
- Exported all registered cube-block definitions with live usage columns for limits planning.
## v0.8.28 — Standard role templates
- Added non-overwriting helper/staff/builder/event/admin/owner role-template workflow.
## v0.8.29 — Scoped role permissions
- Added durable scoped grants and simulator commands.
## v0.8.31-v0.8.32 — Two-staff transfer approval
- Published public-safe command, configuration, deployment, changelog, and release-index guidance for the enforced optional approval workflow.

## v0.8.33 — Staff case workflow
- Published public-safe staff case command and release guidance.
## 2026-09-21 — Public documentation consolidation
- Rewrote README as owner how-to and grouped release changes by date.

## 2026-09-21 — v0.8.49 automatic block catalogue
Public owner documentation now records the startup/restart export location and manual refresh command for the complete vanilla-and-mod block catalogue.

- 2026-09-28: Documented v0.8.53 save-confirmed delayed restart. Build completed with 0 warnings/errors using NuGet audit disabled due offline vulnerability-feed access; ZIP validation passed. Runtime acceptance remains pending.


## 2026-10-06 public user guide

Added docs/USER_GUIDE.md; connected it to the documentation index and README; recorded setup, feature use, operational safeguards, and public-release limitations. Updated the changelog and repository context/instructions.


# 2026-10-08 — Bifrost account access candidate

- Added first-owner setup code, individual account login, PBKDF2 password hashing, 12-hour in-memory sessions, and owner-managed Admin/Moderator account creation/removal.
- Build/package passed with 0 warnings and 0 errors; dedicated-server sign-in/setup and runtime acceptance remain outstanding.
- Plugin-config Save/Reload remains an integration task for each owning plugin; docs label the limitation clearly.
