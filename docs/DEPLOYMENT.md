# Deployment

The current documented package is v0.8.104. Phase 3's optional Cleaner+ panel integration requires Cleaner+ v1.12.7 for aggregate-only read-only cleanup preview. Install one ZIP while Torch is stopped; it should contain only `Overseer.dll` and `manifest.xml` with matching versions. The startup metric measures Overseer initialization to an observed Torch `Loaded` event; it is not an AMP or world-load timer.

After startup, confirm clean plugin loading, config paths, module status, and Bifrost readiness. Run `!ova doctor` and `!ova status`. Review role boundaries with test accounts. Exercise configured features in a safe test window.

Before production restart workflows, confirm save and Cleaner+ handoff behavior. For Core Controller, verify Linux allowed CPUs, preview, apply/readback, disable/restore, and cancellation; compare Profiler+ under comparable load. Build verification is not Linux/Wine/AMP runtime acceptance.
