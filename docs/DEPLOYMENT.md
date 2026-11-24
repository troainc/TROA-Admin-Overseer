# Deployment

The newest binary committed to this public repository is **v0.8.148**. The documented private implementation is **v0.8.268**, whose package is not included here. Select an artifact that actually exists in [releases](../releases/) or a separately authorized channel; newer documentation does not install newer features.

## Install or update

1. Back up the installed Overseer package and the configuration/data directory reported by Torch.
2. Stop Torch. Remove duplicate older Overseer packages from the active plugin directory, then install exactly one ZIP containing `Overseer.dll` and `manifest.xml` with matching versions.
3. Start Torch. Confirm the loaded version, storage paths, module status and Bifrost listener readiness. Run `!ova doctor` and `!ova status` with an authorized account.
4. Complete initial account setup using the one-time setup information reported by the installed build. Review staff permissions and relevant owning-plugin capabilities.
5. Exercise configured features in a safe window. Confirm save and Cleaner+ handoff behavior before relying on restart workflows.

The public v0.8.148 ZIP SHA-256 is `10BFECA2B7B077C15014B2E16351E6E3940D365FCB58091C83841C3A2EAF159C`. See the [README](../README.md) and [release index](RELEASES.md) for version boundaries and links.

## Network, assets and rollback

The default Bifrost listener is `127.0.0.1:18750`. Use the generated webserver configuration and an HTTPS reverse proxy with appropriate network restrictions for remote access. A public URL setting is not DNS/TLS provisioning. Supported configuration reloads do not replace a loaded DLL; binary updates require a restart.

Features depending on game/mod assets require an authorized accessible asset source in builds supporting them. The plugin package does not contain game assets. A block inventory loading completely does not certify texture success.

For rollback, stop Torch, restore the previous package and its matching backed-up data/configuration and asset-source setup, then verify startup. Backup-file checks are not restore tests. Keep target-host runtime acceptance separate from build, fixture and offline-replay results.

Core Controller is optional and host-bound. Verify Linux allowed CPUs, preview, apply/readback, disable/restore and cancellation where supported. Affinity does not parallelize SE simulation or guarantee improved SimSpeed. Observed Overseer-init to Torch-Loaded timing is not AMP or full world-load timing.
