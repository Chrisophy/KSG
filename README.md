# 🔌 Kodi Addon & Skin Generator v9.1 Pro by IT('s) Possible (-W.I.P.-)

**Baue dein eigenes Kodi-Video-Addon mit individuellem Vollbild-Menü, einen kompletten Kodi-Skin oder ein Menü um ein vorhandenes Addon – ohne eine Zeile Code zu schreiben.**

👉 **Direkt im Browser starten:** [chrisophy.github.io/KSG](https://chrisophy.github.io/KSG/)
📖 **Ausführliches Handbuch:** [Anleitung.md](Anleitung.md)

> 🧪 **Kontextmenü, Live-Browser, Fremd-Addon und die neue Desktop-Vorlage sind brandneu** und noch im Praxistest auf echten Geräten. Fehler bitte mit Kodi-Version, Gerät und Schritten melden.

> 🇩🇪 Oberfläche und Handbuch auf Deutsch · 📱 Maus, Tastatur und Touch (PC, Tablet, Handy) · 🔒 Läuft komplett in deinem Browser – nichts wird hochgeladen · 💚 Gratis für die Kodi-Community

---

## 🆕 Neu im Update vom 14.11.2026

| | Neuheit | Was sie bringt |
|---|---|---|
| ✨ | **Vorlagen-Assistent „Desktop-Vorlage“** | Ein Klick auf **✨ Desktop-Vorlage** (Kopfzeile) bzw. **🖥 Kodi Desktop erstellen** (Einstellungen), dann Name, Stil und Akzentfarbe wählen – fertig ist ein komplettes Desktop-Addon. Danach lässt sich alles wie gewohnt im Designer ändern. Für Profis gibt es aufklappbare **Profi-Optionen**. |
| 🖥 | **Kodi Desktop** | Ein Desktop wie am PC: Der Nutzer legt in Kodi selbst **Addons, Scripte, Kodi-Verknüpfungen und einzelne Menüs aus Addons** (z.B. „Live TV“ aus einem IPTV-Addon) als Kacheln ab, ordnet sie per Touch oder Fernbedienung an und bedient alles über Taskleiste und Startmenü. Der Desktop ist am Anfang leer. |
| 🎨 | **Vier Stile zum Umschalten** | **Ubuntu**, **Windows**, **Bunt** und **Dunkel** – jeweils mit eigener Taskleiste, eigenem Hintergrund und eigener Ordner-Ansicht. Der Stil lässt sich in Kodi in den Addon-Einstellungen oder im Startmenü wechseln und gilt **sofort**. |
| 📂 | **Menüs im Desktop-Look** | Einzelne Menüs eines Addons erscheinen als Kachel und öffnen im **selben Design** statt in Kodis Standardansicht. Wer die Originalansicht braucht, schaltet das pro Kachel um. |
| 🔤 | **Lesbare Beschriftungen** | Kachel-Beschriftungen stehen auf einer **farbigen Platte** (Farbe und Deckkraft einstellbar) mit scharfer Schrift ohne Schatten. Farbcodes, Emojis und Flaggen aus Addon-Namen werden entfernt, damit keine Kästchen erscheinen. |
| ▦ | **Spalten wählbar (4–10)** | Das Kachel-Raster nutzt die Breite aus: Standard sind **9 Spalten**, mittig auf dem Bildschirm. |
| 🔒 | **Zurück-Taste sperren** | „⬅ Zurück auf der Startseite“ gilt jetzt auf **jeder** Startseite, auch wenn ein Hook oder ein Stilwechsel eine andere Seite als Start setzt. Kein kurzes Aufblitzen von Kodi mehr. Beenden geht dann nur über das Power-Symbol. |
| 🐍 | **Neue Python-Hook-Möglichkeiten** | Rückgabe `swap:SEITE` (Seite ersetzen), `browse:PFAD@@Titel@@SEITE`, `py:NAME` sowie die optionalen Funktionen `start_page()` (eigene Startseite) und `open_settings(window)` (eigene Einstellungs-Aktion). |
| 🛠 | **Korrektur Favoriten-Befehl** | Der Befehl „Favoriten“ in der 📚 Befehlsliste nutzt jetzt `favouritesbrowser`. In Kodi 20/21 schloss das alte Fenster `favourites` Kodi. |

Alles dazu steht im Handbuch: **[Anleitung.md](Anleitung.md), Teil I (Kapitel 59–63)**.

---

## Frühere Neuerungen – Update vom 23.10.2026

| | Neuheit | Was sie bringt |
|---|---|---|
| ⚡ | **Titan-Modus: dein eigener Kodi-Skin** | Der Generator baut den offiziellen Skin Estuary um: Farben, Hintergrund, Logo, Schrift, Hauptmenü, eigene Menüpunkte (z.B. zu deinem Addon) und Widgets – mit Live-Vorschau. Export als `skin.<name>.zip`. |
| 📐 | **Titan-Layout** | Logo, Uhr, Knöpfe, Hauptmenü, Widget-Bereich und Player-Leiste an jede Stelle ziehen. Das Hauptmenü auch als **einzelne Buttons, waagerecht oder senkrecht**, dazu **eigene Bilder als Dekoration**. |
| 🪟 | **Titan-Fenster-Reiter** | Video-OSD, Zeitleiste, Dialoge, Musik- und Einstellungsfenster des Skins einzeln bearbeiten: Knöpfe **ausblenden, verschieben, vergrößern, umfärben**, Skizzen-Vorschau, **eigene Skin-Einstellungen** (Schalter in Kodi), XML von Hand ändern, mit Estuary vergleichen, **Bilder der Fenster gegen eigene tauschen**, **neue eigene Fenster** aus Vorlagen anlegen. |
| 🎭 | **Skin-Modus für beliebige Skins** | Die ZIP eines anderen Kodi-Skins laden (getestet mit Bello 10): Der Generator erkennt den Fenster-Ordner und die Bausteine (Includes) selbst. Fenster bearbeiten (Knöpfe ausblenden/verschieben/umfärben, Bilder tauschen, neue Fenster, eigene Schalter) und als eigenen Skin mit neuer ID exportieren – Original-Autor und Lizenz bleiben erhalten. |
| 🔧 | **Titan-Profi-Reiter** | Änderungen an Estuary vergleichen und von Hand anpassen, Suchen-und-Ersetzen-Regeln, eigene Dateien im Skin, Estuary-Widgetreihen ausblenden, Profile für mehrere Varianten, Undo/Redo. |
| 📜 | **Script-Werkstatt** | Eigene **Programm-Addons, Scripte, Hintergrund-Dienste, Module und Kontextmenü-Einträge** bauen: fertiges Python-Gerüst mit Einstellungen, Code-Editor mit Bausteinen und Syntax-Sichtprüfung, ZIP-Export. Scripte lassen sich in jedem Menü-/Skin-Button per `RunScript(…)` aufrufen (Gruppe „Scripte“ in der Befehlsliste) oder ins Menü-Addon einbetten. |
| 🧩 | **Fremd-Addon einbinden** | Du hast schon ein Addon (ZIP)? Der Generator packt es in dein Addon, entpackt und aktiviert es beim Installieren und zeigt es in deinem Menü: als Live-Browser, Kachel-Raster, Liste, Taschenrechner oder Linux-Desktop. |
| 📂 | **Live-Browser** | Ordner eines Addons gehen in **deinem Skin** auf, Zurück geht eine Ebene hoch, Videos starten direkt. Kodis eigene Ansicht taucht nicht auf. |
| 🔗 | **Abhängigkeiten automatisch** | Module wie `bs4`, `requests` oder `feedparser` erkennt der Generator im Code und trägt sie selbst in die `addon.xml` ein – kein `No module named …` mehr. |
| 🖱 | **Kontextmenü mit Favoriten** | Lange drücken, Rechtsklick oder Taste C öffnet im fertigen Addon ein eigenes Menü: Öffnen, Als Favorit speichern/entfernen, Wiedergabeliste, Beschreibung, Kodi-Favoriten, Einstellungen. Ordner-Favoriten öffnen direkt in deinem Skin. Langes Drücken wirft dich nicht mehr aus dem Addon. |
| 👁 | **Live-Ansicht in Menüs** | Ein kleines, verschiebbares Live-Bild deines Menüs erscheint, sobald die große Vorschau nicht zu sehen ist: in den Einstellungen auf dem Handy, in der Modding-Werkstatt und beim Scrollen zu den Eigenschaften. Jede Änderung siehst du sofort – und du kannst darin sogar Elemente antippen und ziehen. Ein- und ausblenden mit einem Klick. |
| 🧩 | **Widgets** | Reihen wie im Kodi-Hauptmenü, die sich in Kodi **von selbst** füllen: Neue Filme, Filme weiterschauen, Noch nicht gesehen, Zufällige Filme, Am besten bewertet, Neue Folgen, Serien weiterschauen, Neue/Zufällige Alben, Video-Playlists, Inhalte aus anderen Addons oder jede eigene Kodi-Quelle. Als Poster, Breitbild, Quadrat oder Liste – auf Wunsch mit Jahr, Bewertung und Inhalt des gewählten Titels. |
| 🕒 | **Info-Widgets** | Uhr & Datum, Wetter, „Jetzt läuft“ und System-Info als fertige Karten. Ihre Teile bewegen sich gemeinsam. |
| 🍿 | **Beispiel zum Lernen** | „Mein Kino-Hub“: 5 fertige Seiten mit Animationen, Widgets, Kachel-Raster, Demo-Video, Musik-Seite und Info-Dialog – inklusive kurzer Einführung. Perfekt zum Umbauen. |
| 🎁 | **Demo-Vorlagen** | Im Ordner [`demos/`](demos/README_Demos.md): fünf fertige Addon-Projekte, ein Titan-Skin mit angepasstem Video-OSD und ein kleines Fremd-Addon zum Einbinden – laden, anschauen, umbauen. |
| ◀▶ | **Punktgenau verschieben** | Pfeil-Knöpfe unter „Position & Größe“, X/Y-Felder wirken sofort beim Tippen. |
| 📱 | **Handy-Ansicht aufgeräumt** | Die Kopfzeile ist jetzt eine wischbare Reihe und verdeckt die Vorschau nicht mehr. |
| 🎯 | **Klügerer Startfokus** | Ist ein Widget in Kodi noch leer, springt der Fokus automatisch zum nächsten bedienbaren Element. |

---

## ✨ Funktionen & Highlights

**Gestalten**

- ✨ **Vorlagen-Assistent:** In drei Klicks zum fertigen **Kodi Desktop** mit vier Stilen (Ubuntu, Windows, Bunt, Dunkel).
- 🎨 **Visueller Menü-Editor** auf einer 1920×1080-Bühne: Buttons, Texte, Flächen, Poster, eigene Bilder, Fortschrittsbalken, Cover – ziehen, Größe ändern, fertig.
- 🧩 **Widgets & Info-Widgets** (siehe oben), **Listen**, **Kachel-Raster**, **Karussell**, echte **Ein/Aus-Schalter**, **Regler** für Lautstärke und Spulen, **Textbox**, **Laufschrift**, **Videofenster**, **Visualisierung**, **RSS-Ticker**.
- 🖼 **Alles ist anklickbar:** Jedes Element kann eine Aktion bekommen – auch Bilder, Texte und Flächen.
- 💅 **Form & Stil:** eckig, abgerundet, Pille, nur Rahmen, Glas – dazu Rahmen, Deckkraft, Farben, 10 fertige Designs, eigene Hintergrundbilder pro Seite.
- 📄 **Mehrere Seiten** mit Seitenübergängen, Zurück-Logik und **Dialog-Seiten**, bei denen Kodi durchscheint.

**Kodi-Skin und Fremd-Addons**

- ⚡ **Titan-Modus:** echter Kodi-Skin auf Basis von Estuary – Farben, Hintergrund, Logo, Schrift, Hauptmenü, eigene Menüpunkte, Widgets und freies Layout.
- 📦 **Fremd-Addon einbinden:** eine vorhandene Addon-ZIP wird mitgeliefert, beim Installieren entpackt und eingeschaltet. Deine Oberfläche wird zum Gesicht des Addons.
- 📂 **Live-Browser** und Button-Stile **Kacheln, Liste, Taschenrechner, Linux-Desktop**.
- 🖱 **Kontextmenü** mit Favoriten, erweiterbar über `kontextmenue()` in `custom.py`.

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

Du kannst ein Addon-Menü bauen (Schritte unten), einen **⚡ Titan-Skin** (Kopfzeile ⚡ Titan), ein Menü um ein **📦 Fremd-Addon** (Kopfzeile 📦 Fremd-Addon) oder einen **🖥 Kodi Desktop** per Assistent (Kopfzeile ✨ Desktop-Vorlage).

1. **Öffnen:** [chrisophy.github.io/KSG](https://chrisophy.github.io/KSG/) aufrufen (oder die `index.html` herunterladen und im Browser öffnen).
2. **Starten:** Unter **📂 Vorlagen** das **✨ Beispiel „Mein Kino-Hub“** laden – oder mit einer leeren Seite beginnen.
3. **Benennen:** Links bzw. im Tab „Einstellungen“ den Namen deines Addons eintragen.
4. **Gestalten:** Elemente antippen, ziehen, Texte und Farben ändern. Über **🧩 Widgets** fertige Reihen einfügen, über **📚 Befehlsliste** Buttons mit Funktion.
5. **Ausprobieren:** **▶ Testen** zeigt, wie sich dein Menü anfühlt. **✔ Prüfen** findet Vergessenes.
6. **Exportieren:** **⬇ ZIP exportieren** klicken.
7. **Installieren:** In Kodi **Einstellungen → Addons → Aus ZIP-Datei installieren**. Dein Addon findest du unter **Addons → Video-Addons**.

**Skin bauen:** Kopfzeile ⚡ Titan → Estuary laden → Farben, Hauptmenü, Layout einstellen → Export als `skin.<name>.zip`.
**Fremd-Addon einbinden:** Kopfzeile 📦 Fremd-Addon → ZIP wählen → Stil wählen (empfohlen: Live-Browser) → exportieren.
**Desktop in drei Klicks:** Kopfzeile ✨ Desktop-Vorlage → Name, Stil und Akzentfarbe wählen → **✨ Desktop erstellen** → **⬇ ZIP exportieren**. Profi-Optionen (Spalten, Platte, Schrift, Stile, Autostart) stehen aufklappbar im Assistenten.

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
├── service.py                nur mit Autostart oder Fremd-Addon
├── resources/
│   ├── settings.xml          nur mit eigenen Addon-Optionen oder Autostart
│   ├── screenshot-01.jpg …   bis zu 8 Screenshots
│   ├── bundled/<id>.zip      nur mit Fremd-Addon (unverändert, wird beim Installieren entpackt)
│   ├── lib/custom.py         nur mit Python-Hooks oder Fremd-Addon
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
- Der **Live-Browser** liest Ordner eines Addons ebenfalls über `Files.GetDirectory` und füllt eine Liste im eigenen Skin. Das **Kontextmenü** baut `addon.py` selbst, weil Kodi sein eigenes in Addon-Fenstern abschaltet.
- **Titan-Skins** entstehen aus dem offiziellen Estuary (wird passend zur Kodi-Version von GitHub geladen). Der Generator verschiebt Elemente über unsichtbare Gruppen mit Versatz, Estuary selbst wird nicht umgeschrieben.
- Zustände (Schalter-Merker, letzte Seite) speichert das Addon in seinem Profil-Ordner (`state.json`).

---

## 📄 Lizenz & Credits

**Kostenlos, aber nicht Open Source.** Es gilt die **[IT('s) Possible Freeware-Lizenz](LICENSE)**.

```text
Kodi Addon & Skin Generator v9.1 Pro – Copyright (c) 2026 Team IT('s) Possible
Stand 2026.11.14. Alle Rechte vorbehalten.
```

| ✅ Erlaubt | 🚫 Verboten ohne schriftliche Erlaubnis |
|---|---|
| Kostenlos nutzen – online oder als heruntergeladene Datei | Verkaufen, vermieten oder gegen Bezahlung anbieten (auch als Abo oder hinter einer Bezahlschranke) |
| Verlinken und weiterempfehlen | Mit Werbung oder anderen Einnahmequellen versehen |
| Deine damit gebauten Addons frei veröffentlichen – sie gehören dir | Auf anderen Seiten, Servern oder in App-Stores bereitstellen oder spiegeln |
| | Veränderte Fassungen verbreiten oder als eigenes Werk ausgeben |
| | Copyright- und Lizenzhinweise entfernen |

Die Nutzung erfolgt auf eigene Gefahr, ohne Gewähr und ohne Haftung. Die vollständigen Bedingungen stehen in der Datei **[LICENSE](LICENSE)**.

- **Estuary** stammt von phil65 und Team Kodi (Code GPL-2.0, Grafiken CC BY-SA 4.0). Ein daraus gebauter Skin steht unter denselben freien Lizenzen und nennt Estuary als Grundlage.
- **Fremd-Addons** behalten ihre eigene Lizenz. Gib dein Addon nur weiter, wenn du das eingebundene Addon weitergeben darfst.
- **Deine Addons gehören dir.** Für die damit gebauten Addons ist `GPL-2.0-or-later` nur als Lizenz **vorgeschlagen** – du kannst im Generator jede andere eintragen.
- Kodi® ist eine Marke der XBMC Foundation. Dieses Projekt steht in keiner Verbindung zur XBMC Foundation.
- Gemacht mit 💚 von **IT('s) Possible** für die Kodi-Community.
