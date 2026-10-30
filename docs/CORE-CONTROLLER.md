# Core Controller

Overseer v0.8.98 provides an Owner-only Bifrost CPU topology map and affinity picker, building on the disabled-by-default CPU-affinity controller introduced in v0.8.95 for Torch on Linux/Wine hosts. It changes which logical processors the Torch process may run on; it cannot grant CPU time, alter AMP quotas, or make a single-threaded simulation task parallel.

## CPU layout and safety

Linux logical CPU IDs are not physical core counts. A host described as having “24 threads” may expose 24 logical processors across fewer physical cores. The page shows every Linux-online logical CPU separately from the CPUs allowed to Torch. When sysfs exposes topology, logical processors are grouped by physical core and socket. Host-online count, Torch-allowed count, physical cores, and sockets are separate metrics. If host-online inventory cannot be read, the page says so and falls back to showing only the process-allowed set.

The controller prefers the process cgroup's effective cpuset as the AMP/host boundary. If cgroup data is unavailable, it falls back to `/proc/self/status` `Cpus_allowed_list`, which may already be narrower than the allocation. It never accepts CPUs outside the verified set. If Linux allowance data or runtime read/set/readback support is missing, affinity stays unchanged.

Affinity is not CPU isolation: Linux may schedule other workloads on the same allowed logical CPUs. Overseer does not reserve cores, change quotas, or promise exclusive use. Configure dedicated AMP/host cgroup isolation if exclusive cores are required; the controller stays within the CPU set the OS exposes.

## Commands

All actions are Torch Owner-only:

| Command | Purpose |
|---|---|
| `!ova core status` | Show support, logical/physical topology, allowed/current/startup/saved masks, and last result. |
| `!ova core preview <hex-mask>` | Validate the selected logical processors without applying. |
| `!ova core enable <hex-mask>` | Apply, verify, and persist an explicit mask. |
| `!ova core disable` | Disable the saved setting and restore startup affinity where still allowed. |

Bit 0 selects logical CPU 0; `0x000F` selects logical CPUs 0–3, if all are allowed. Preview first. A multi-CPU mask makes Torch eligible to schedule on multiple logical processors; it does not promise parallel simulation or higher SimSpeed.

Bifrost under **Administration → Core controller** is the recommended workflow. Its CPU map labels CPUs as allowed to Torch or outside the Torch allocation. When disabled, choose **Enable controller with selection**; when enabled, choose **Update selected CPUs**. To turn it off, choose **Disable and restore startup affinity** and confirm. Cancel leaves the current state unchanged. Current, startup, and saved affinity are shown separately. A collapsed Advanced section provides hexadecimal masks; IDs 0–63 are supported by the current affinity mask. Preview/apply/restore POSTs use the same Base64-encoded JSON body as the rest of Bifrost; plain JSON causes `invalid_request`. The page remains Owner-only, enforced by the server.

There is no periodic enforcement loop. Overseer will not continuously fight AMP or external affinity changes. Compare similar Profiler+ observation windows before and after applying one mask; disable it if results do not support keeping it.
