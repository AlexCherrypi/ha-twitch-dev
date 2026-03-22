# Twitch (dev) — Custom Integration

Test build of the Twitch integration including three improvements over the current HA Core version:

## Changes

### 1. Automatic follow sync (PR [#166196](https://github.com/home-assistant/core/pull/166196))
Channels you follow on Twitch are automatically added as sensors. Channels you unfollow are removed from the config. No more manual reconfiguration needed.

### 2. Option to remove sensors for unfollowed channels (PR [#166198](https://github.com/home-assistant/core/pull/166198))
New toggle under **Settings → Devices & Services → Twitch → Configure**:
- **"Remove sensors for unfollowed channels"** (default: off)
- When enabled: sensors for channels you have unfollowed are permanently removed from the entity registry on the next reload.
- When disabled: sensors are kept (existing behavior).

### 3. Configurable poll interval (PR [#166200](https://github.com/home-assistant/core/pull/166200))
New number field under **Settings → Devices & Services → Twitch → Configure**:
- **"Poll interval (minutes)"** (default: 5, min: 1, max: 1440)
- Controls how often Home Assistant polls Twitch for updates.

## Installation via HACS

1. Open HACS → ⋮ → **Custom repositories**
2. URL: `https://github.com/AlexCherrypi/ha-twitch-dev`
3. Category: **Integration** → **Add**
4. Search for **"Twitch (dev)"** → **Download**
5. Restart Home Assistant
