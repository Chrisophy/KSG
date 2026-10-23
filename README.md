# 🔌 Kodi Video-Addon Generator v8.1 Pro by IT('s) Possible (-W.I.P.-)

**Baue dein eigenes Kodi-Video-Addon mit individuellem Vollbild-Menü – ohne eine Zeile Code zu schreiben.**

👉 **Direkt im Browser starten:** [chrisophy.github.io/KSG](https://chrisophy.github.io/KSG/)
📖 **Ausführliches Handbuch:** [Anleitung.md](Anleitung.md)

> 🇩🇪 Oberfläche und Handbuch auf Deutsch · 📱 Maus, Tastatur und Touch (PC, Tablet, Handy) · 🔒 Läuft komplett in deinem Browser – nichts wird hochgeladen · 💚 Gratis für die Kodi-Community

---

## 🆕 Neu in v8.1 Pro

| | Neuheit | Was sie bringt |
|---|---|---|
| 👁 | **Live-Ansicht in Menüs** | Ein kleines, verschiebbares Live-Bild deines Menüs erscheint, sobald die große Vorschau nicht zu sehen ist: in den Einstellungen auf dem Handy, in der Modding-Werkstatt und beim Scrollen zu den Eigenschaften. Jede Änderung siehst du sofort – und du kannst darin sogar Elemente antippen und ziehen. Ein- und ausblenden mit einem Klick. |
| 🧩 | **Widgets** | Reihen wie im Kodi-Hauptmenü, die sich in Kodi **von selbst** füllen: Neue Filme, Filme weiterschauen, Noch nicht gesehen, Zufällige Filme, Am besten bewertet, Neue Folgen, Serien weiterschauen, Neue/Zufällige Alben, Video-Playlists, Inhalte aus anderen Addons oder jede eigene Kodi-Quelle. Als Poster, Breitbild, Quadrat oder Liste – auf Wunsch mit Jahr, Bewertung und Inhalt des gewählten Titels. |
| 🕒 | **Info-Widgets** | Uhr & Datum, Wetter, „Jetzt läuft“ und System-Info als fertige Karten. Ihre Teile bewegen sich gemeinsam. |
| 🍿 | **Beispiel zum Lernen** | „Mein Kino-Hub“: 5 fertige Seiten mit Animationen, Widgets, Kachel-Raster, Demo-Video, Musik-Seite und Info-Dialog – inklusive kurzer Einführung. Perfekt zum Umbauen. |
| ◀▶ | **Punktgenau verschieben** | Pfeil-Knöpfe unter „Position & Größe“, X/Y-Felder wirken sofort beim Tippen. |
| 📱 | **Handy-Ansicht aufgeräumt** | Die Kopfzeile ist jetzt eine wischbare Reihe und verdeckt die Vorschau nicht mehr. |
| 🎯 | **Klügerer Startfokus** | Ist ein Widget in Kodi noch leer, springt der Fokus automatisch zum nächsten bedienbaren Element. |

---

## ✨ Funktionen & Highlights

**Gestalten**

- 🎨 **Visueller Menü-Editor** auf einer 1920×1080-Bühne: Buttons, Texte, Flächen, Poster, eigene Bilder, Fortschrittsbalken, Cover – ziehen, Größe ändern, fertig.
- 🧩 **Widgets & Info-Widgets** (siehe oben), **Listen**, **Kachel-Raster**, **Karussell**, echte **Ein/Aus-Schalter**, **Regler** für Lautstärke und Spulen, **Textbox**, **Laufschrift**, **Videofenster**, **Visualisierung**, **RSS-Ticker**.
- 🖼 **Alles ist anklickbar:** Jedes Element kann eine Aktion bekommen – auch Bilder, Texte und Flächen.
- 💅 **Form & Stil:** eckig, abgerundet, Pille, nur Rahmen, Glas – dazu Rahmen, Deckkraft, Farben, 10 fertige Designs, eigene Hintergrundbilder pro Seite.
- 📄 **Mehrere Seiten** mit Seitenübergängen, Zurück-Logik und **Dialog-Seiten**, bei denen Kodi durchscheint.

**Funktionen**

- 📚 **Befehlsliste mit 92 Kodi-Befehlen** zum Anklicken (Navigation, Wiedergabe, Lautstärke, Einstellungen, System, Addons …) – plus eigene Befehle.
- 🕒 **15 Live-Infos** wie Uhrzeit, Datum, Wetter, laufender Titel, CPU-Last oder IP-Adresse.
- 👁 **Sichtbarkeits-Regeln** („nur wenn ein Video läuft“, „nur abends“, „nur wenn Kindermodus an“ …) mit einem Baukasten aus 29 fertigen Bedingungen.
- 🔐 **PIN-Sperre und Sicherheitsfragen** für einzelne Buttons.
- ⚙ **Eigene Addon-Einstellungen** (Schalter, Text, Zahl, Auswahl) – automatisch als `resources/settings.xml`.

**Für Profis – die 🛠 Modding-Werkstatt**

- Animationen pro Element, Fokus-Zoom, nacheinander einblenden, Textschatten, Schriften.
- Tastenbelegung, Seiten-Befehle (`onload`/`onunload`), Startfokus, eigenes XML pro Element und pro Seite.
- Python-Hooks (`custom.py`), Autostart-Dienst, Hintergrundmusik, Direkt-Links zu jeder Seite (z.B. als Kodi-Favorit).
- Inspektor mit allen Kodi-IDs, Ausrichten- und Verteilen-Werkzeuge, komplettes Projekt als JSON.
- 💻 **Editor** für alle erzeugten Dateien (`addon.py`, `addon.xml`, `home.xml`, `pages.json` …) mit Syntax-Prüfung.

**Sicher und bequem**

- ▶ **Testmodus**, ✔ **Prüfen** (findet vergessene Aktionen, fehlende Bilder, kaputtes XML), ↩ Rückgängig/Wiederholen.
- 💾 Projekt als Datei speichern und laden – zusätzlich automatisch im Browser gemerkt.
- 🏠 Beenden führt im fertigen Addon zur **Kodi-Startseite**, nach Kodi-Fenstern und Videos geht es zurück **in dein Menü**.
- ✅ Kompatibel mit **Kodi 19 Matrix, 20 Nexus und 21 Omega**.

---

## 🚀 Schnellstart

1. **Öffnen:** [chrisophy.github.io/KSG](https://chrisophy.github.io/KSG/) aufrufen (oder die `index.html` herunterladen und im Browser öffnen).
2. **Starten:** Unter **📂 Vorlagen** das **✨ Beispiel „Mein Kino-Hub“** laden – oder mit einer leeren Seite beginnen.
3. **Benennen:** Links bzw. im Tab „Einstellungen“ den Namen deines Addons eintragen.
4. **Gestalten:** Elemente antippen, ziehen, Texte und Farben ändern. Über **🧩 Widgets** fertige Reihen einfügen, über **📚 Befehlsliste** Buttons mit Funktion.
5. **Ausprobieren:** **▶ Testen** zeigt, wie sich dein Menü anfühlt. **✔ Prüfen** findet Vergessenes.
6. **Exportieren:** **⬇ ZIP exportieren** klicken.
7. **Installieren:** In Kodi **Einstellungen → Addons → Aus ZIP-Datei installieren**. Dein Addon findest du unter **Addons → Video-Addons**.

Alles Weitere – Schritt für Schritt, mit Rezepten und Fehlerhilfe – steht in der **[Anleitung.md](Anleitung.md)**.

---

## 📦 Inhalt der erzeugten ZIP-Datei

```text
plugin.video.<projektname>/
├── addon.xml                 Addon-Beschreibung (Name, Version, Icon, Fanart, Screenshots …)
├── addon.py                  Startet dein Menü, führt Aktionen aus, füllt Listen und Widgets
├── pages.json                Seiten, Aktionen, Listen, Widgets, Schalter, Tasten, Optionen
├── icon.png                  Eigenes Icon oder automatisch erzeugt
├── fanart.jpg                Eigene Fanart, Hintergrundbild oder automatisch erzeugt
├── service.py                nur mit Autostart
├── resources/
│   ├── settings.xml          nur mit eigenen Addon-Optionen oder Autostart
│   ├── screenshot-01.jpg …   bis zu 8 Screenshots
│   ├── lib/custom.py         nur mit Python-Hooks
│   └── skins/Default/
│       ├── 1080i/
│       │   ├── home.xml      deine Startseite
│       │   └── page_1.xml …  weitere Seiten
│       └── media/            white.png, background.jpg, bg_page_*.jpg, img_* (deine Bilder),
│                             round_* / ring_* / mask_* (Rundungen und Rahmen), Schalter- und Regler-Grafiken
└── (deine eigenen Ordner und Dateien)
```

---

## 🛠 Technik

- **Eine einzige HTML-Datei**, kein Server, keine Anmeldung. Für die Darstellung wird [Tailwind CSS](https://tailwindcss.com) geladen.
- **Eigener ZIP-Schreiber** direkt im Browser – keine Fremd-Bibliothek nötig.
- Das erzeugte Addon ist ein normales **`plugin.video`-Addon** (Python 3). Das Menü läuft als `xbmcgui.WindowXML` bzw. `WindowXMLDialog` mit eigenem Skin (`resources/skins/Default/1080i`).
- **Listen und Widgets** füllt `addon.py` beim Öffnen einer Seite über Kodis **JSON-RPC** (`Files.GetDirectory`) – mit Bildern, Jahr, Bewertung, Inhalt und Fortschritt. Bibliotheks-Widgets nutzen dieselben intelligenten Listen (`?xsp=…`) wie die Kodi-Skins.
- Zustände (Schalter-Merker, letzte Seite) speichert das Addon in seinem Profil-Ordner (`state.json`).

---

## 📄 Lizenz & Credits

```text
Kodi Video-Addon Generator – Copyright (c) 2026 Team IT('s) Possible
Version 2026.10.23 (v8.1 Pro). Alle Rechte vorbehalten.

Die Nutzung ist für die Kodi-Community kostenlos – für Anfänger und Profis.
Der Generator darf weder verkauft noch kopiert und weiterverkauft werden.
Änderungen am Code und eine Weiterverbreitung sind nur mit Erlaubnis der Autoren gestattet.

Die Nutzung erfolgt auf eigene Gefahr. Eine Haftung für Schäden jeder Art
und jegliche Gewährleistung sind ausgeschlossen.
```

- **Deine Addons gehören dir.** Für die damit gebauten Addons ist `GPL-2.0-or-later` nur als Lizenz **vorgeschlagen** – du kannst im Generator jede andere eintragen.
- Kodi® ist eine Marke der XBMC Foundation. Dieses Projekt steht in keiner Verbindung zur XBMC Foundation.
- Gemacht mit ?? von **IT('s) Possible** für die Kodi-Community.
