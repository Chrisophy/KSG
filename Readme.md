# 🚀 Kodi Skin & Addon Fusion Engine v3.0 Pro

Ein hochmoderner, browserbasierter **Visual Builder, Python Script Generator & XML Studio** für Kodi Addons und Skins. Entwickelt, um Skins und Python-Addons in einer einzigen, leistungsstarken Benutzeroberfläche zu entwerfen, anzupassen und als fertiges ZIP-Paket zu exportieren.

---

## ✨ Hauptfunktionen

- **Addon + Skin Fusion Engine**: Wähle zwischen einem reinen Skin (`skin.name`) oder einer vollständigen Addon-Skin-Kombination (`plugin.video.name` / `script.module`).
- **Automatisierte Python-Generierung**: Erstellt sauberen Python-Code (`main.py`, `addon.py`, `resources/lib/plugin.py`) mit echtem Kodi-Routing und Builtin-Unterstützung.
- **Interaktiver Button- & Action-Editor**: Erstelle, bearbeite und platziere Buttons, Navigationsleisten, Sidebars und Dynamic Hub Cards direkt per Klick im Live-Vorschaufenster.
- **Umfassender Kodi Action Katalog**: Integriere Standard-Befehle wie `RunPlugin(...)`, `PlayMedia(...)`, `Container.Update(...)`, `ActivateWindow(...)` oder `PlayerControl(Play)` mit Leichtigkeit.
- **Vorgefertigte Templates & Muster**:
  - *VOD Streaming Hub*: Video-Kategorien, Hero-Featured Banner, Play-Buttons und Detail-Dialoge.
  - *IPTV / Live TV EPG Guide*: Kanal-Grid, EPG-Aktionen, Senderwechsel und PiP-Player Commands.
  - *Audio / Music Player*: Album Art Grid, Viz-Player Controls.
  - *Custom Addon Dashboard*: Universelles Smart-Dashboard mit frei konfigurierbaren Tiles.
- **Builtin Command & Property Explorer**: Durchsuche und verwende `$INFO[...]`, `$VAR[...]` und Kodi Built-in Befehle direkt im Editor.
- **Echtzeit-Vorschau & Code Inspector**: Betrachte generierte XML-Includes, Windows & Python-Skripte sofort im Code-Tab.
- **Erweiterter ZIP-Export**: Generiert mit nur 1 Klick eine voll funktionsfähige Kodi-Struktur inklusive `addon.xml`, `colors/defaults.xml`, `font/font.xml` und allen XML-Fenstern.

---

## 🛠️ Schnellstart & GitHub Pages Setup

Das Projekt ist zu **100% Client-side** (HTML, Tailwind CSS, JavaScript) aufgebaut und benötigt keinen Backend-Server. Du kannst es direkt über **GitHub Pages** hosten:

1. **Repository erstellen**: Erstelle ein neues öffentliches Repository auf GitHub (z. B. `kodi-fusion-engine`).
2. **Datei hochladen**: Lade deine `index.html` (als `index.html` im Root-Verzeichnis des Repositories) hoch.
3. **GitHub Pages aktivieren**:
   - Gehe in deinem Repository auf **Settings** (Einstellungen).
   - Klicke links auf **Pages**.
   - Wähle unter *Build and deployment* -> *Branch* den Ast `main` (oder `master`) und den Ordner `/ (root)` aus.
   - Klicke auf **Save**.
4. Nach wenigen Augenblicken ist deine App unter der angegebenen GitHub Pages URL live verfügbar!
