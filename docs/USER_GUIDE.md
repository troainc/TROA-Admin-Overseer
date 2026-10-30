# User guide

## Setup
Install one current Overseer ZIP while Torch is stopped. Start Torch, confirm a clean plugin load, review generated XML files, and run `!ova doctor` and `!ova status`. Keep the plugin's data directory backed up.

## Routine use
Players use `!ov help`, `motd`, `report`, `vote`, `claim`, `daily`, `rewards progress`, and supported owned-grid tools. Staff use `!ova` commands permitted by Torch. Owners manage configuration, roles, restart coordination, webhooks, and Bifrost accounts.

In Bifrost, open a plugin workspace to view only supported owner-plugin settings/data. Save/reload runs through that plugin. Use preview before consequential operations.

## Boundaries
Cleaner+ owns cleanup; GridVault owns backup/recovery; Hangar owns hangar storage. Missing measurements are not assumed to be zero. Core Controller affects scheduling eligibility only; it cannot increase AMP quota or parallelize SE simulation.

See [commands](COMMANDS.md), [configuration](CONFIGURATION.md), [Bifrost](BIFROST-PLUGIN-PANEL.md), and [deployment](DEPLOYMENT.md).
