# Repository snapshot

Latest documented package: **v0.8.99**. The package adds capability/freshness cards and a role-gated Operations timeline for plugin/audit events and Profiler+ incidents. Public documentation covers released behavior; see the roadmap for remaining integrations.

Bifrost is hosted inside Torch. It discovers TROA plugins and uses supported plugin-owned APIs for settings and live data. Player commands use `!ov`; staff/owner commands use `!ova`. Overseer owns its staff features, rewards, webhooks, and restart coordination. Cleaner+, GridVault, and Hangar retain cleanup, backup/recovery, and storage ownership.

Core Controller is optional, disabled by default, Owner-only, and bounded by verified process CPU allowance. It does not parallelize the SE simulation thread. README illustrations use demonstration values only.
