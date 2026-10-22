# 🔌 Kodi Video-Addon Generator v8.0 Pro

**Baue dein eigenes Kodi-Video-Addon mit individuellem Vollbild-Menü – ohne eine Zeile Code zu schreiben.**

→ [Online-Tool öffnen](https://chrisophy.github.io/KSG) ←

Der **Kodi Video-Addon Generator** ist ein vollwertiges Web-Tool in einer einzigen Datei. Mit ihm erstellst du ein echtes Video-Addon (`plugin.video...`), dessen Startmenü (`home.xml`) du frei auf einer 1920×1080 Canvas gestalten kannst. Beim Öffnen des Addons in Kodi erscheint dein Menü im Vollbild und ersetzt die Standardansicht.

> 🇩🇪 Deutsche Benutzeroberfläche & Anleitung · 📱 Funktioniert mit Maus, Keyboard & Touch · 🔒 Läuft zu 100 % lokal in deinem Browser

---

## ✨ Funktionen & Highlights

- **Visueller Menü-Editor:** 1920×1080-Leinwand mit Drag & Drop, Touch-Unterstützung, frei skalierbaren Elementen, Ausrichthilfen, Raster-Einrasten (Snap) und mehrstufigem Undo/Redo (`Strg+Z`).
- **Anklickbare Bilder & Design-Elemente:** Füge eigene Bilder, Poster-Platzhalter, Farbflächen und Buttons ein. Bilder können rein dekorativ sein oder eigene Klick-Aktionen erhalten.
- **📚 Befehlsliste:** Über 70 vorgefertigte Kodi-Befehle (Navigation, Wiedergabe, Lautstärke, Systemsteuerung, Addon-Starts) sortiert nach Kategorien und mit Schnellsuche.
- **Mehrseitige Menüs:** Erstelle komplexe Menüstrukturen mit Unterseiten, dynamischer Seitenverknüpfung und automatischer Navigation für Fernbedienungen.
- **▶ Testmodus & ✔ Prüfen:** Teste Seitenwechsel und Befehle direkt im Browser. Die Prüffunktion deckt fehlende Links, leere Video-URLs, unvollständige Befehle oder verwaiste Seiten auf.
- **Addon-Assets & Metadata:** Eigenes **Icon**, **Fanart** und bis zu 8 **Screenshots** verwalten, die direkt in die `addon.xml` und die ZIP-Struktur eingepflegt werden.
- **📁 Integrierter Dateimanager:** Eigene Ordnerstrukturen anlegen, Dateien per Drag & Drop hinzufügen oder Textdateien (z. B. `settings.xml`) direkt im Generator schreiben.
- **Flexibles Projektmanagement:** Automatische Speicherung im Browser sowie lokaler Export und Import über JSON-Dateien.
- **Kompatibilität:** Generiert valide Addon-Pakete für Kodi 19 (Matrix), 20 (Nexus) und 21 (Omega).

---

## 🚀 Schnellstart

1. Öffne die Datei `index.html` in einem modernen Browser (Chrome, Edge, Firefox, Safari).
2. Vergabe einen **Projektnamen** unter **1 · Projekt** (die technische ID `plugin.video...` wird automatisch gebildet).
3. Füge über **2 · Hinzufügen** Buttons, Texte oder **eigene Bilder** hinzu und positioniere sie auf der Leinwand.
4. Markiere ein Element und wähle über **📚 Befehlsliste** eine Aktion aus (z. B. Öffnen von Unterseiten, Abspielen von Streams oder Ausführen von Kodi-Befehlen).
5. Lade unter **5 · Addon-Bilder & Dateien** dein Icon und Fanart hoch.
6. Klicke auf **✔ Prüfen** und danach auf **⬇ ZIP exportieren**.
7. In Kodi: **Einstellungen → Addons → Aus ZIP-Datei installieren** wählen. Dein Addon ist nun unter **Addons → Video-Addons** verfügbar.

Eine ausführliche Anleitung findest du in der [Anleitung.md](Anleitung.md).

---

## 📦 Inhalt der generierten ZIP-Datei

Das exportierte ZIP-Paket entspricht der offiziellen Kodi-Addon-Struktur:

```text
plugin.video.deinprojekt/
├── addon.xml
├── addon.py
├── pages.json
├── icon.png
├── fanart.jpg
├── resources/
│   ├── screenshot-01.jpg …
│   └── skins/
│       └── Default/
│           ├── 1080i/
│           │   ├── home.xml
│           │   ├── page_1.xml …
│           │   └── (weitere Unterseiten)
│           └── media/
│               ├── white.png
│               ├── background.jpg (optional)
│               └── img_*.png / img_*.jpg (eigene Bilder)
└── (deine manuell hinzugefügten Ordner und Dateien)
```

---

## 🛠 Technik

Das Tool besteht aus einer einzigen HTML-Datei ohne Server-Backends:
- **Styling:** [Tailwind CSS](https://tailwindcss.com/)
- **ZIP-Erstellung:** [JSZip](https://stuk.github.io/jszip/)
- **Laufzeit in Kodi:** Python 3 (`xbmc.python` v3.0.0+) und Kodi `WindowXML`-GUI.

---

## 📄 Lizenz & Credits

Erstellt von **IT('s) Possible**. Freie Nutzung unter GPL-2.0-or-later.