# Kodi Video-Addon Generator v8.1 Pro

Ein Werkzeug für Kodi-Bastler: Du baust im Browser ein eigenes Kodi-Addon mit Menü, einen kompletten Skin oder ein Menü um dein bestehendes Addon, und lädst es als ZIP-Datei herunter. Ohne Programmierkenntnisse, aber mit Platz für Profis.

**Ausführliche Anleitung:** [Anleitung.md](Anleitung.md)

## Was du damit machen kannst

- **Eigenes Video-Addon** mit Startmenü im Vollbild, mit Buttons, Texten, Bildern, Listen, Schaltern, Widgets und Seiten.
- **Eigener Skin im Titan-Modus:** Der Generator baut den offiziellen Skin Estuary passend zu deiner Kodi-Version um. Farben, Layout, Hauptmenü und Widgets sind frei gestaltbar.
- **Fremd-Addon einbinden:** Wähle die ZIP-Datei eines bestehenden Addons. Der Generator packt sie in dein Addon, trägt die benötigten Module (z. B. `bs4`, `requests`) selbst in die `addon.xml` ein und zeigt das Addon in deinem Menü.
- **Kontextmenü mit Favoriten:** Lange drücken, Rechtsklick oder Taste C öffnet im fertigen Addon ein Menü mit Favoriten, Wiedergabeliste und Einstellungen.
- **Modding-Werkstatt:** Listen, Kachel-Raster, Karussell, Regler, Animationen, Python-Hooks, eigenes XML und das komplette Projekt als JSON.

## So funktioniert es

1. Die Datei `kodi_generator.html` im Browser öffnen. Es ist keine Installation nötig.
2. Das Menü bauen oder mit einer Vorlage starten.
3. Mit **⬇ ZIP exportieren** das Addon herunterladen.
4. In Kodi: **Einstellungen → Addons → Aus ZIP-Datei installieren**.

## Dateien in diesem Projekt

| Datei | Inhalt |
|---|---|
| `kodi_generator.html` | Das Werkzeug. Eine einzelne Datei, läuft im Browser. Für den Titan-Modus wird Estuary aus dem Netz geladen. |
| `Anleitung.md` | Die ausführliche Anleitung mit allen Funktionen. |
| `README.md` | Diese Übersicht. |

## Lizenz

© 2026 Team IT('s) Possible. Alle Rechte vorbehalten.

Das Werkzeug ist eine **Freeware-Lizenz**: kostenlos für die Kodi-Community, aber **nicht Open Source**. Verkauf, Vermietung, Werbung, Bereitstellen auf anderen Seiten, Servern oder App-Stores und das Verbreiten veränderter Fassungen sind ohne schriftliche Erlaubnis verboten. Die mit dem Generator gebauten Addons gehören dir.

Der Titan-Modus verwendet Estuary (Code: GPL-2.0, Grafiken: CC BY-SA 4.0 von phil65 und Team Kodi). Daraus gebaute Skins stehen unter denselben freien Lizenzen.

Lizenztext: [LICENSE](LICENSE) · Original: https://chrisophy.github.io/KSG/
