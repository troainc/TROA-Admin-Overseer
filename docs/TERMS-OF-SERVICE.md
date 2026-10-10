# Bifrost Plugin Panel Terms of Service — deployment draft

**Status:** Draft template for operator and qualified-counsel review. It is not legal advice, a signed agreement, or a claim of legal compliance. Review it against the applicable Admin Overseer software license and the law governing the actual deployment before relying on it.

**Last updated:** 2026-10-10

These terms describe use of **Bifrost Plugin Panel**, the self-hosted Torch administration interface supplied with TROA Admin Overseer (the **Panel**). The person or organization installing and operating the Torch server is the **Server Operator**. A person given a Panel account is an **Operator User**.

## 1. Operator and service boundary

The Server Operator installs, configures, hosts, and controls access to the Panel. The Panel runs alongside Torch on that server; it is not a TROA-hosted account service. The Server Operator controls the server, account creation, staff permissions, network exposure, backups, and the notices and policies given to Operator Users and players.

## 2. Software license and ownership

Use and redistribution of Admin Overseer and the Panel remain governed by the license and distribution terms accompanying the software. These terms do not transfer ownership or grant rights beyond that license. If this template conflicts with the applicable software license, the license controls for software use.

## 3. Permitted and prohibited use

Use the Panel only on a Torch server you own or are authorized to administer. Do not bypass access controls, interfere with another system, or use the software for unlawful activity. Keep account credentials, owner setup codes, bearer tokens, network configuration, and plugin secrets private.

## 4. Operator accounts and permissions

The Server Operator is responsible for creating individual accounts, selecting Admin or Moderator roles, configuring role visibility and capabilities, and promptly removing access when it is no longer needed. Shared accounts reduce accountability. A Moderator may have read-only access; actual capabilities depend on owner-configured role views.

## 5. Commands, settings, and plugin operations

The Panel presents operations exposed by loaded plugins. Each plugin remains responsible for its own commands, configuration validation, saves, reloads, metrics, webhooks, and game-side effects. A command or setting may be unavailable, read-only, delayed, or behave differently by plugin version or server state. The Panel does not guarantee that a plugin action succeeds or can be reversed.

Operator Users must review commands, configuration changes, reward grants, and other actions before submission. Actions may affect a live server or player experience. The Server Operator is responsible for establishing approvals and least-privilege access appropriate to the server.

## 6. Security and network exposure

The Server Operator is responsible for securing the machine and network, applying updates, protecting Panel files and backups, using strong unique passwords, and limiting filesystem access. The built-in Panel listener does not provide HTTPS. Do not expose it directly to an untrusted network; use a correctly configured HTTPS reverse proxy or private network together with firewall restrictions.

## 7. Privacy and local data

The Panel's current local data practices are described in [Privacy & GDPR Notice](PRIVACY-GDPR.md). The Server Operator must tailor the notice to its deployment, provide appropriate information to staff and players where required, establish a monitored privacy contact and request process, and handle records it controls under applicable law. Plugins and hosting providers may have separate data practices.

## 8. Availability, compatibility, and updates

Compatibility can depend on Torch, Space Engineers, the operating system, network configuration, and installed plugin versions. Features may be unavailable when a plugin does not expose a supported Panel integration. Review release notes and test updates in a safe environment before production use. Support channels, if offered, do not create a guaranteed response time unless separately agreed in writing.

## 9. Warranty and liability

To the maximum extent permitted by applicable law and subject to the accompanying software license, the Panel is supplied without a promise that it will be uninterrupted, error-free, compatible with every environment, or suitable for a particular purpose. Nothing in this draft excludes rights or liability that applicable law does not allow to be excluded. The Server Operator remains responsible for server operations, access decisions, backups, and actions taken by its staff.

## 10. Suspension and termination

The Server Operator can disable accounts, stop the Panel listener, or uninstall the software. Account removal revokes active in-memory sessions, but the current implementation marks account records disabled rather than deleting their rows. Other local records and backups require separate retention and deletion handling by the Server Operator.

## 11. Changes and contact

This draft may be updated when the software or deployment practices change. Server access, account, or local-data questions should go to the Server Operator through its published contact method. Software license questions should use the contact specified by the applicable license or official TROA support channel. Any governing law or venue is determined by the applicable software license and mandatory local law; this template does not choose one.

---

**Review note:** Before publication as binding terms, insert the correct contracting entity, monitored contact, governing-law language if appropriate, and counsel-approved terms. The footer link makes this document accessible; it does not itself implement an acceptance workflow.
