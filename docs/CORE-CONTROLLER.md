# Core Controller

v0.8.95 introduced an optional, disabled-by-default Linux process-affinity controller. v0.8.96 added the CPU topology map/picker; v0.8.97 fixed request encoding; v0.8.98 added explicit Enable/Update and Disable/Restore controls and fixed confirmation. v0.8.100 added source freshness; v0.8.101 adds measured Torch lifecycle timing to Bifrost operations.

It changes Torch's eligible logical CPUs only within the verified Linux process/cgroup allowance. Preview is read-only; apply validates/readbacks; disable attempts startup affinity restore. Topology maps logical IDs to physical cores/sockets when Linux exposes it.

It cannot grant CPU quota, reserve cores, promise SimSpeed gains, or make the SE simulation thread multi-threaded. Logical processors are not physical cores; SMT siblings share cores.

In Bifrost, choose allowed CPUs, preview, confirm Enable/Update. To turn off, confirm Disable/Restore. Cancel makes no change. Owner-only. Unsupported runtime capabilities fail without applying affinity. Current documented Overseer build is v0.8.104; this page remains focused on Core Controller CPU-affinity behavior.
