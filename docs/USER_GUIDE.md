# Admin Overseer — server owner and staff guide

Admin Overseer is the Torch-side administration suite for Space Engineers. It is the command and feature owner for staff operations and the Rewards module. Monitor+ may forward commands through Discord, but Overseer owns the command behavior and its webhooks. Install the versioned package through Torch, start once to generate configuration and persistent data, then use the root [configuration guide](CONFIGURATION.md), [permissions guide](PERMISSIONS.md), and [webhook guide](WEBHOOKS.md).

## Main capabilities

- **Operations:** status, loaded modules, health/performance summary, reload and configuration doctor checks; save and staged restart workflows with player notices and save verification; rotating announcements and maintenance mode.
- **Moderation and cases:** bans, kicks, mutes, warnings, staff notes, player reports with assignment/status/deadline/updates/timeline, and case/history lookup.
- **Connections and audit:** player/faction dossiers, session and name/IP history subject to configuration, account/faction context, event/audit lookups, and staff watch flags.
- **Grid tools:** grid health checks, owner grid listing, player-safe fix/stop actions, ownership-transfer preview/confirmation and second-staff approval where configured.
- **Limits:** show and recount block-limit usage, preview grid-scoped rules, and export block subtype data.
- **Broadcasts, events, and roles:** server notices, MOTD, event announcements/check-ins/attendance exports, temporary-role management where enabled.
- **Rewards:** daily and playtime rewards, configurable streak/claim rewards, vote links and claims, Discord reservation flow, claim history/leaderboard, and privileged grants through the Rewards-specific commands/config.

Modules load independently. Check `!ova modules` and `!ova doctor` after startup or a reload to see module/configuration state. A disabled module or missing dependency can remove its commands without affecting unrelated modules.

## Command and permission model

Use `!ova` for privileged staff actions and `!ov` for player-facing actions. Legacy short command roots may return a redirect; use the canonical `!ova` form. Never give general players staff commands. Torch permission levels and Overseer-specific gates are described in [Permissions](PERMISSIONS.md). The full, build-aligned command syntax belongs in [Commands](COMMANDS.md), including player grid actions, moderation, reporting, events, limits, roles, and rewards.

Discord rewards use Overseer's own Discord gateway/configuration. Other Discord commands can arrive through Monitor+ forwarding, but the originating plugin still checks its permissions and executes the operation. Route each event to its owning webhook using [Webhook routing](WEBHOOKS.md); do not place live webhook secrets in a public config.

## Safe operational workflows

Before changing settings, back up the generated Overseer data folder. Use the doctor/status commands to diagnose config rather than editing generated files blindly. For restarts, issue the canonical restart command and watch the save/countdown sequence; the plugin should save and verify before it hands off to the restart action. Test this sequence on the actual Torch host because an external restart command and server filesystem determine the final outcome. Follow the release README and changelog for exact version-specific defaults and migration behavior.

## Rewards setup

Configure vote provider URLs, daily/playtime award values, streak rules, and any Discord reservation settings in the generated Rewards config. Verify links and the bot connection, then test player flows with a non-admin: inspect available rewards, claim a daily/playtime reward, reserve a vote reward in Discord if enabled, and complete the in-game claim. Use admin grants only for named Steam IDs and review the reward history/leaderboard afterward. The migration importer preserves supported Monitor+ pending IDs/history when installed data is available; keep a backup until the first successful post-migration claim is confirmed.
