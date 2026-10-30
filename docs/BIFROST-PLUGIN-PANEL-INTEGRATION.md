# Bifrost Plugin Panel integration contract

## Overseer Core Controller

The v0.8.95 Owner-only Core controller is an Overseer-owned process-affinity operation, not a generic plugin adapter. Its server routes enforce Owner authorization and constrain masks to the verified Linux cgroup CPU set, with /proc/self/status fallback. See [Core Controller](CORE-CONTROLLER.md).

**Bifrost Plugin Panel** is the rebranded name for the operator interface hosted by TROA Admin Overseer inside Torch. The rebrand changes the product name; it does not change the existing reflection method names, Torch command ownership, or plugin config formats.

## Communication model

- Admin Overseer discovers loaded TROA plugins through Torch's `IPluginManager` and calls their supported APIs in-process.
- Plugin integrations must not connect back to the Panel over HTTP, open another listener, implement Panel login, or store Panel credentials. Admin Overseer owns the web server, authentication, roles, and operator session.
- Each plugin remains authoritative for its own settings, validation, save/reload, commands, metrics, events, and domain data. The Panel only displays or requests actions through APIs the plugin explicitly supports.
- Unsupported settings remain read-only. Do not advertise a save path until the plugin validates and persists it safely.

## Optional explicit adapter methods

Admin Overseer recognizes a complete adapter on the loaded Torch plugin type when these public instance methods are present with the exact signatures below. Every method returns a JSON string except that the method names remain the stable `BifrostPanel` API identifiers for compatibility.

```csharp
public string GetBifrostPanelDescriptorJson();
public string GetBifrostPanelStateJson();
public string GetBifrostPanelConfigJson();
public string SaveBifrostPanelConfigJson(string configJson);
public string ReloadBifrostPanelConfig();
```

An optional validator is called when present:

```csharp
public string ValidateBifrostPanelConfigJson(string configJson);
```

Return descriptor/state/config as valid JSON. Save, reload, and validation responses should use `{ "success": true, "message": "..." }` on success and `{ "success": false, "error": "..." }` on failure. Never throw across the adapter boundary; catch and return a safe operator-facing error while logging the exception in Torch.

## Data shape

A descriptor should include a human-readable `description` and a `settings` array. Each editable setting needs a stable `key`, `label`, and supported `type` (`text`, `number`, `bool`, `select`, or `json`); optional fields include `description`, `min`, `max`, `options`, `secret`, `ownerOnly`, and `readOnly`. Config JSON is an object keyed by those stable names. Secret values must be omitted or redacted; a blank submitted secret should preserve the stored value.

State JSON may include:

- `sampledUtc` or `generatedUtc` as a UTC timestamp;
- `metrics`: real plugin measurements with `label`, `value`, and optional `unit`;
- `charts`: `{ "title": "...", "points": [{ "timestampUtc": "...", "value": 0 }] }` using actual timestamped samples;
- `events`: `{ "timestampUtc": "...", "severity": "info|warning|error|critical", "title": "...", "message": "..." }`.

Do not synthesize values, use a current timestamp for old data, expose credentials, or include private player data. Keep histories bounded and return quickly; capture game state on the Torch/game thread and serialize immutable snapshots outside expensive work where possible.

## Current support status

The Panel also has a conservative generic reflection fallback for some plugin configuration and live data. That fallback does not mean a plugin implements this explicit adapter, and some integrations remain read-only or status-only. A local source scan at v0.8.88 found no TROA plugin implementing the complete explicit method set. Add and validate adapters plugin-by-plugin before claiming full interactive support.