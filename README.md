# Twitch (dev) — Custom Integration

Testversion der Twitch-Integration mit drei Verbesserungen gegenüber dem HA-Core-Stand:

## Änderungen

### 1. Automatischer Follow-Sync (PR [#166196](https://github.com/home-assistant/core/pull/166196))
Neue Kanäle, denen du auf Twitch folgst, werden automatisch als Sensoren angelegt. Kanäle denen du nicht mehr folgst, werden aus der Config entfernt. Kein manuelles Neu-Einrichten mehr nötig.

### 2. Sensoren für unfollowed Kanäle automatisch löschen (PR [#166198](https://github.com/home-assistant/core/pull/166198))
Neue Option unter **Einstellungen → Geräte & Dienste → Twitch → Konfigurieren**:
- **"Remove sensors for unfollowed channels"** (default: aus)
- Wenn aktiviert: Sensoren für Kanäle, denen du nicht mehr folgst, werden beim nächsten Reload automatisch aus der Entity Registry gelöscht.
- Wenn deaktiviert: Sensoren bleiben erhalten (bisheriges Verhalten).

### 3. Konfigurierbares Poll-Intervall (PR [#166200](https://github.com/home-assistant/core/pull/166200))
Neue Option unter **Einstellungen → Geräte & Dienste → Twitch → Konfigurieren**:
- **"Poll interval (minutes)"** (default: 5, min: 1, max: 1440)
- Steuert wie oft HA Twitch nach Updates fragt.

## Installation via HACS

1. HACS öffnen → ⋮ → **Custom repositories**
2. URL: `https://github.com/AlexCherrypi/ha-twitch-dev`
3. Kategorie: **Integration** → **Add**
4. Nach **"Twitch (dev)"** suchen → **Download**
5. HA neu starten
