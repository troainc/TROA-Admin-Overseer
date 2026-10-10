# Bifrost Plugin Panel Privacy & GDPR Notice — deployment draft

**Status:** Draft disclosure template. It does not certify GDPR compliance or replace a deployment-specific privacy notice. Review the actual deployment with qualified privacy counsel before relying on it.

**Last updated:** 2026-10-10

This notice borrows the structured, source-derived disclosure approach used by Bifrost Server Manager and narrows it to the current **Bifrost Plugin Panel** implementation. It distinguishes Panel-local processing from independent processing by the Server Operator, Torch host, plugins, and network providers.

## 1. Who operates the Panel and handles requests

The person or organization that installs and runs the Panel (**Server Operator**) controls its local accounts, permissions, command records, panel events, hosting, and retention. Depending on the purposes and applicable law, the Server Operator may be the controller for those local records. It is responsible for identifying its role, determining and documenting a lawful basis, publishing a monitored privacy contact, giving required notices, and handling requests for records it controls.

The Panel is software hosted by the Server Operator. Its current server code has no built-in remote account or analytics service that receives the Panel's local account, role-view, command-history, or panel-event files. This statement does not cover separate TROA services, hosting tools, backups, or independent plugin integrations.

For an account or information associated with a particular game server, contact that server's owner/operator. The operator should publish its organization name, contact details, and request procedure before making the Panel available to staff.

## 2. Information stored by the Panel

The following inventory reflects source inspected for the October 2026 build. Verify it against the exact version and deployment in use.

| Record | Current fields and purpose | Local storage and current behavior |
|---|---|---|
| Panel accounts | Username, role, enabled state, random salt, derived password verifier, and verifier iteration count; used for authentication and authorization. No email or phone field is collected by the account form. | `Accounts.json`. Passwords are not stored as plaintext. Removing an account disables its row and revokes its active in-memory sessions; it does not erase the row. |
| Login sessions | Random bearer token, username, role, and expiration; used to authenticate requests. | Server process memory for 12 hours. The browser stores the token in tab-scoped `sessionStorage`; the Panel does not set a persistent login cookie. Process exit or expiration ends the session. |
| Initial owner setup | Random one-time setup code used to create the first owner account. | May be written to `OwnerSetupCode.txt` before setup and is deleted after successful owner creation. Treat it as a credential. |
| Command history | Submitted command text, response text, outcome, timestamp, operator username, and role; supports accountability and troubleshooting. | `CommandHistory.json`, capped at the newest 1,000 entries; the UI returns up to 500. There is no time-based expiry. Commands and responses can contain identifying or sensitive text. |
| Panel events | Plugin name, title, bounded diagnostic message, severity, and timestamp; supports alerts and event review. | `PanelEvents.json`, capped at 500 entries. Entries are not automatically deleted based on age. Messages may reflect plugin diagnostics or operator actions. |
| Role views | Section/plugin visibility and role capabilities for Admin and Moderator accounts. | `RoleViews.json`. |
| Live plugin data and settings | Status, metrics, command descriptions, events, and settings exposed by each loaded plugin. | Read through the plugin in the running Torch process. Configuration saves/reloads are delegated to the owning plugin's supported API. Each plugin controls its own persistent data and integrations. |

Panel data files are under the Bifrost Panel data directory adjacent to the owner setup-code path. The Server Operator controls access to that directory and its backups.

## 3. Information not sent by the Panel

The inspected Panel server code has no built-in telemetry or remote synchronization path for the local account file, role views, command history, or panel events. Those records remain on the server unless the Server Operator, its backup system, hosting provider, or another locally installed service copies them. Separately configured plugins may contact Discord or other external services and follow their own policies. This notice does not describe those independent services.

## 4. Network, logs, and browser storage

The Panel serves requests on the configured listener. Its current Panel JSON stores do not record client IP addresses. The operating system, firewall, Torch, hosting platform, reverse proxy, or security tools may separately record source addresses, request metadata, or errors under their own configurations; the Server Operator must inspect those systems and document their retention.

The built-in listener does not provide HTTPS. Use a correctly configured TLS reverse proxy or private network for remote access and restrict inbound traffic. The browser stores the session token in tab-scoped `sessionStorage` and keeps view state in memory. The Panel does not set advertising or analytics cookies. Clearing the browser's session/site data signs the Operator User out.

## 5. Purposes and legal basis

Local records support account authentication, role enforcement, command accountability, troubleshooting, plugin configuration, and game-server operation. The Server Operator must identify and document a legal basis for its actual purposes and jurisdictions. This template does not choose a legal basis or establish that the operator complies with GDPR or another privacy law.

## 6. Recipients and international transfers

Panel records may be accessible to the Server Operator and staff whose permissions allow access. Hosting, backup, network, security, and remote-access providers may process information if used by the operator. Plugin-specific information can be sent to destinations configured for that plugin. The operator must inventory the providers, locations, transfers, and safeguards that apply to its deployment; the Panel does not maintain that inventory.

## 7. Retention, export, and deletion

The implementation currently uses count caps, not age-based retention, for command history and panel events. Disabled account rows remain in `Accounts.json`; role views remain in `RoleViews.json`; plugin data follows each plugin's behavior. Backups, server logs, proxy logs, and replicas follow their respective operator settings. The Panel does not currently provide a one-click export or erasure workflow for all records.

The Server Operator should establish a purpose-specific retention schedule, restrict access to the data directory, plan for backup expiry, and document how it will find and delete records when appropriate. Deleting a live file or row may not remove copies already held in backups.

## 8. Privacy requests and individual rights

Where applicable law grants rights such as access, correction, deletion, restriction, objection, or portability, requests should be sent to the Server Operator using its published privacy contact. The operator should verify identity proportionately, identify affected systems and backups, and respond under the applicable rules. Requests about independent plugin or third-party services may need to go to those services as well.

Official background is available from the [European Data Protection Board's data-subject-rights page](https://www.edpb.europa.eu/topics/key-gdpr-concepts/data-subject-rights_en) and the [official GDPR text on EUR-Lex](https://eur-lex.europa.eu/eli/reg/2016/679/oj). This notice is informational and is not legal advice.

## 9. Security responsibilities

The Panel has account roles and server-side permission checks, but no software feature removes the Server Operator's responsibility to secure its deployment. At minimum, use unique accounts, strong passwords, least-privilege roles, HTTPS through a trusted reverse proxy or a private network, firewall controls, current software, and protected backups. Never enter passwords, webhook tokens, or unrelated personal information in command text.

## 10. Updates and deployment review

Update this notice whenever the software or deployment changes its data fields, purposes, recipients, retention, hosting, logs, or plugin integrations. Before deployment, the Server Operator should insert its identity and monitored contact and verify the processors, locations, lawful bases, log behavior, backups, retention periods, and request workflow. No qualified review, processor inventory, request response-time commitment, or GDPR certification is represented here.

---

**Source references:** Admin Overseer `BifrostAuthService`, `BifrostPanelDataStore`, and `BifrostPanelServer`; Bifrost Server Manager `Docs/Privacy-Notice.md` (used as a structure/reference, not copied as Panel data practice).
