# 🎁 Demo-Vorlagen für den Kodi Video-Addon Generator

Fünf fertige Projekte zum Laden, Anschauen, Umbauen und Übernehmen. Der Generator selbst bleibt unverändert – es sind ganz normale Projekt-Dateien (`.json`).

## So lädst du eine Demo

1. Generator öffnen: [chrisophy.github.io/KSG](https://chrisophy.github.io/KSG/)
2. Bereich **Projekt sichern** → **📥 Laden** → eine der Dateien wählen.
3. Die Seiten oben in der Seiten-Leiste durchklicken, **▶ Testen** drücken, Elemente verschieben und ändern.
4. **⬇ ZIP exportieren** und in Kodi installieren.

⚠️ **Laden ersetzt dein aktuelles Projekt.** Sichere es vorher mit **💾 Speichern**.

## Die fünf Demos

| Datei | Addon-ID | Zeigt | Besonderheiten zum Lernen |
|---|---|---|---|
| `Demo1_Kinder-Kino.json` | `plugin.video.kinderkino` | Kindermenü in Pillen-Form | **PIN-Schutz** (🔐, PIN `1234`), **Kindermodus-Schalter** mit Bedingung, Kachel-Reihe, Widget, eigene Addon-Einstellungen, Fokus-Zoom |
| `Demo2_Live-TV-Kiosk.json` | `plugin.video.livetvkiosk` | Senderliste mit Videofenster | **Autostart**, **letzte Seite merken**, Zurück „erst beim zweiten Mal“, Uhr- und Wetter-Info-Widget, M3U-Datei im Addon |
| `Demo3_Musik-Lounge.json` | `plugin.video.musiklounge` | Musik-Player | **Jetzt läuft** mit Cover, **Visualisierung**, **Lautstärke-Regler**, drei Album-Widgets, Party-Modus |
| `Demo4_Retro-Terminal.json` | `plugin.video.retroterminal` | Matrix-Terminal | **Python-Hooks** (`custom.py`), **Tastenbelegung**, Befehl beim Öffnen einer Seite, **Kodi-Einstellung als Schalter**, Merker + Bedingung, Dialog-Seite, eigenes Kontextmenü |
| `Demo5_Addon-Portal.json` | `plugin.video.addonportal` | Eigener Browser für Kodi-Pfade | **Live-Browser**: Ordner öffnen sich im eigenen Skin, Zurück geht eine Ebene hoch, **Kontextmenü mit Favoriten**, Beschreibung des gewählten Eintrags |

## Hinweise

- **Test-Videos:** Die Beispiel-Adressen (Big Buck Bunny, Sintel, Elephants Dream, ein HLS-Teststream) sind frei verfügbare Testvideos. Tausche sie gegen deine eigenen aus. Ob die Adressen dauerhaft erreichbar sind, kann ich nicht zusichern.
- **Bibliothek:** Widgets wie „Neue Filme“ füllen sich nur, wenn Filme, Serien oder Musik in der Kodi-Bibliothek sind.
- **YouTube und Co. (Demo 5):** Die Pfade zu anderen Addons funktionieren nur, wenn das Addon installiert ist.
- **PIN ändern:** In Demo 1 steht die PIN lesbar in der `pages.json`. Ein Schutz vor Kindern, kein echtes Passwort.
- **Icon:** Die Demos bringen kein eigenes Icon mit – der Generator erzeugt automatisch eines. Unter **5 · Addon-Bilder & Dateien** wählst du ein eigenes.
- **Geprüft:** Alle fünf Dateien lassen sich im Generator laden, ✔ Prüfen meldet keine Warnungen, und die erzeugten Addon-Dateien (Python, XML, JSON) sind syntaktisch fehlerfrei. Auf einem echten Kodi-Gerät sind sie noch nicht getestet.

## Eigene Demo beisteuern

Baue dein Projekt im Generator, sichere es mit **💾 Speichern** und schicke die `.json` als Pull Request in den Ordner `demos/` des Repos. Bitte ohne Zugangsdaten, fremde Logos oder urheberrechtlich geschützte Bilder.
