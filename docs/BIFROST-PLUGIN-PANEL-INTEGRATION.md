# Plugin integration contract

Admin Overseer hosts Bifrost; plugins remain authoritative for their own config, status, metrics, commands, events, and domain actions. Do not add another listener/login or read/write another plugin's files.

Optional adapter methods:

```csharp
public string GetBifrostPanelDescriptorJson();
public string GetBifrostPanelStateJson();
public string GetBifrostPanelConfigJson();
public string SaveBifrostPanelConfigJson(string configJson);
public string ReloadBifrostPanelConfig();
public string ValidateBifrostPanelConfigJson(string configJson); // optional
```

Return bounded valid JSON, truthful timestamps, real metrics/history/events, and safe operator errors. Never leak secrets; blank secret fields preserve stored values. Capture game state on correct thread. Server-side roles remain mandatory.

Do not persist custom Discord presence text/message bodies; roster access is Analytics-authorized. Generic reflection config editing is allowed only with supported owner-plugin save/reload APIs.
