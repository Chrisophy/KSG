# 🎁 Demo-Vorlagen für den Kodi Video-Addon Generator

Sieben fertige Beispiele zum Laden, Anschauen, Umbauen und Übernehmen. Der Generator selbst bleibt unverändert – es sind ganz normale Projekt-Dateien (`.json`), dazu ein kleines Beispiel-Addon (`.zip`).

## So lädst du eine Demo (Demo 1–5)

1. Generator öffnen: [chrisophy.github.io/KSG](https://chrisophy.github.io/KSG/)
2. Bereich **Projekt sichern** → **📥 Laden** → eine der Dateien wählen.
3. Die Seiten oben in der Seiten-Leiste durchklicken, **▶ Testen** drücken, Elemente verschieben und ändern.
4. **⬇ ZIP exportieren** und in Kodi installieren.

⚠️ **Laden ersetzt dein aktuelles Projekt.** Sichere es vorher mit **💾 Speichern**.

## Die sieben Demos

| Datei | Addon-ID | Zeigt | Besonderheiten zum Lernen |
|---|---|---|---|
| `Demo1_Kinder-Kino.json` | `plugin.video.kinderkino` | Kindermenü in Pillen-Form | **PIN-Schutz** (🔐, PIN `1234`), **Kindermodus-Schalter** mit Bedingung, Kachel-Reihe, Widget, eigene Addon-Einstellungen, Fokus-Zoom |
| `Demo2_Live-TV-Kiosk.json` | `plugin.video.livetvkiosk` | Senderliste mit Videofenster | **Autostart**, **letzte Seite merken**, Zurück „erst beim zweiten Mal“, Uhr- und Wetter-Info-Widget, M3U-Datei im Addon |
| `Demo3_Musik-Lounge.json` | `plugin.video.musiklounge` | Musik-Player | **Jetzt läuft** mit Cover, **Visualisierung**, **Lautstärke-Regler**, drei Album-Widgets, Party-Modus |
| `Demo4_Retro-Terminal.json` | `plugin.video.retroterminal` | Matrix-Terminal | **Python-Hooks** (`custom.py`), **Tastenbelegung**, Befehl beim Öffnen einer Seite, **Kodi-Einstellung als Schalter**, Merker + Bedingung, Dialog-Seite, eigenes Kontextmenü |
| `Demo5_Addon-Portal.json` | `plugin.video.addonportal` | Eigener Browser für Kodi-Pfade | **Live-Browser**: Ordner öffnen sich im eigenen Skin, Zurück geht eine Ebene hoch, **Kontextmenü mit Favoriten**, Beschreibung des gewählten Eintrags |
| `Demo6_Titan-Kino-OSD.json` | Skin `skin.titankinoosd` (Titan-Modus) | Estuary-Skin mit angepasstem Video-OSD | **Reiter 🪟 Fenster**: Aufnehmen-Knopf fest ausgeblendet, Knopfreihe höher und größer, Wiedergabe-Knopf in Gelb, **eigene Skin-Einstellungen** („Stopp-Knopf ausblenden“, „Zusatzknöpfe ausblenden“) mit Fenster **Skin-Optionen** und Menüpunkt dafür |
| `demo7/plugin.video.demonews-1.0.0.zip` | Addon `plugin.video.demonews` | Kleines Fremd-Addon zum Einbinden | **📦 Fremd-Addon**: drei Rubriken (aus einer Liste im Code) plus Live-Teststream – der Generator erkennt die Rubriken samt Parametern und baut daraus ein eigenes Menü |

## Demo 6: Titan-Skin mit angepasstem Video-OSD

1. Generator öffnen → Kopfzeile **⚡ Titan** → Reiter **🔧 Profi** → **💾 Projekt als Datei** → **⬆ Importieren** → `Demo6_Titan-Kino-OSD.json` wählen. (Das ersetzt dein aktuelles Titan-Projekt, mit „Rückgängig“ kommst du zurück.)
2. Reiter **🧬 Basis** → **⬇ Estuary laden**, damit die Fenster-Dateien da sind.
3. Reiter **🪟 Fenster** → **Video-OSD** wählen → **Bedienelemente** aufklappen und **🖼 Vorschau** ansehen. Die ⚙-Knöpfe zeigen, was verschoben, vergrößert oder an eine Skin-Einstellung gekoppelt ist.
4. Reiter **📦 Export** → Skin bauen und in Kodi installieren. In Kodi öffnest du **Skin-Optionen** im Hauptmenü und schaltest dort die Knöpfe des Video-OSD an und aus.

Die Nummern der OSD-Knöpfe (601, 603, 608 …) stammen aus Estuary für Kodi 21. Gibt es in deiner Version eine Nummer nicht, meldet der Generator das beim Bauen als Warnung.

## Demo 7: Fremd-Addon einbinden

1. Generator öffnen → Kopfzeile **📦 Fremd-Addon** → `plugin.video.demonews-1.0.0.zip` wählen.
2. Der Generator listet die erkannten Einträge: **Startseite**, **Live**, **Animationsfilme**, **Technik und Autos**, **Kurzes zwischendurch**. Die Rubriken tragen ihre Parameter (`?mode=list&cat=…&title=…`) schon in der Adresse.
3. Stil **📂 Live-Browser** wählen und bauen. Danach ZIP exportieren und in Kodi installieren – das Beispiel-Addon wird automatisch mit installiert.

Das Addon selbst (`addon.py`, rund 90 Zeilen) ist als Vorlage gedacht: Rubriken stehen in einer Liste `CATEGORIES`, und eine Schleife baut daraus die Menüpunkte.

## Hinweise

- **Test-Videos:** Die Beispiel-Adressen (Big Buck Bunny, Sintel, Elephants Dream, ein HLS-Teststream) sind frei verfügbare Testvideos. Tausche sie gegen deine eigenen aus. Ob die Adressen dauerhaft erreichbar sind, kann ich nicht zusichern.
- **Bibliothek:** Widgets wie „Neue Filme“ füllen sich nur, wenn Filme, Serien oder Musik in der Kodi-Bibliothek sind.
- **YouTube und Co. (Demo 5):** Die Pfade zu anderen Addons funktionieren nur, wenn das Addon installiert ist.
- **PIN ändern:** In Demo 1 steht die PIN lesbar in der `pages.json`. Ein Schutz vor Kindern, kein echtes Passwort.
- **Icon:** Die Demos bringen kein eigenes Icon mit – der Generator erzeugt automatisch eines. Unter **5 · Addon-Bilder & Dateien** wählst du ein eigenes.
- **Geprüft:** Alle Dateien lassen sich im Generator laden, ✔ Prüfen meldet keine Warnungen, und die erzeugten Addon-Dateien (Python, XML, JSON) sind syntaktisch fehlerfrei. Das Beispiel-Addon ist mit Simulation von Kodi getestet.
