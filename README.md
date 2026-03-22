# Twitch (dev) — Custom Integration

Test build of the Twitch integration including four improvements over the current HA Core version:

## Changes

### 1. Automatic follow sync (PR [#166196](https://github.com/home-assistant/core/pull/166196))
Channels you newly follow on Twitch are automatically added as sensors. No more manual reconfiguration needed.

Channels you unfollow are intentionally **kept** — they continue to be tracked in Home Assistant. Use the cleanup option below if you want them removed automatically.

### 2. Fix: no more CancelledError on reload (PR [#166203](https://github.com/home-assistant/core/pull/166203))
When new follows were detected, the integration scheduled a reload mid-refresh, causing HA to cancel the running API call and log a `CancelledError`. Fixed by returning early after scheduling the reload — the fresh coordinator set up by the reload fetches the data anyway.

### 3. Option to remove sensors for unfollowed channels (PR [#166198](https://github.com/home-assistant/core/pull/166198))
New toggle under **Settings → Devices & Services → Twitch → Configure**:
- **"Remove sensors for unfollowed channels"** (default: off)
- When enabled: sensors for channels you have unfollowed are permanently removed from the entity registry on the next reload.
- When disabled: sensors are kept (default behavior).

### 4. Configurable poll interval (PR [#166200](https://github.com/home-assistant/core/pull/166200))
New number field under **Settings → Devices & Services → Twitch → Configure**:
- **"Poll interval (minutes)"** (default: 5, min: 1, max: 1440)
- Controls how often Home Assistant polls Twitch for updates.

## Installation via HACS

1. Open HACS → ⋮ → **Custom repositories**
2. URL: `https://github.com/AlexCherrypi/ha-twitch-dev`
3. Category: **Integration** → **Add**
4. Search for **"Twitch (dev)"** → **Download**
5. Restart Home Assistant
