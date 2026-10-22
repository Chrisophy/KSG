# 🧩 Kodi Skin Generator

**Baue dein eigenes Kodi-Menü per Drag & Drop – ohne eine Zeile Code zu schreiben.**

Der Kodi Skin Generator ist ein Ein-Datei-Werkzeug für den Browser. Du ziehst Buttons, Texte und Poster auf eine Leinwand, wählst für jeden Button einen fertigen Kodi-Befehl aus einer Liste und exportierst alles als installierbare ZIP-Datei für Kodi. Gedacht für Einsteiger, aber mit genug Optionen für Profis.

> 🇩🇪 Oberfläche und Anleitung auf Deutsch · 📱 funktioniert mit Maus und Touch · 🔒 alles läuft lokal in deinem Browser

---

## ✨ Funktionen

- **Visueller Editor** auf einer 1920×1080-Leinwand: Elemente verschieben, in der Größe ändern, duplizieren, Raster-Einrasten, Rückgängig
- **Skin oder Addon:** entweder eine eigene Oberfläche (Skin) oder ein Menü im Video-Bereich (Video-Addon)
- **📚 Befehlsliste** mit rund 70 Kodi-Befehlen in verständlichem Deutsch (Navigation, Wiedergabe, Lautstärke, Einstellungen, System, Addons) – mit Suche und Kategorien. Ein Tipp genügt, um einen Befehl in einen Button einzusetzen
- **Mehrere Seiten** mit Seiten-Verknüpfung, Seiten duplizieren, Zurück-Buttons
- **Testmodus:** Buttons ausprobieren, bevor du exportierst
- **✔ Prüfen:** findet Buttons ohne Aktion, fehlende Video-Adressen, Platzhalter und unerreichbare Seiten
- **Vorlagen:** Streaming-Hub, Live TV, Musik-Player oder leeres Projekt
- **Design:** fertige Farbthemen, eigene Farben, eigenes Hintergrundbild
- **Bilder fürs Addon:** eigenes **Icon**, **Fanart** und bis zu 8 **Screenshots** – automatisch ins Addon und in die `addon.xml` eingetragen (ohne eigene Bilder werden Icon und Fanart automatisch erzeugt)
- **📁 Ordner & Dateien:** eigene Ordner anlegen, Dateien hinzufügen oder Textdateien direkt schreiben – alles landet in der ZIP
- **Werkzeuge:** Buttons mittig ordnen, gleiche Größe für alle Buttons
- **Projekt speichern und laden** (JSON-Backup) plus automatisches Merken im Browser
- **Unterstützt Kodi 19 (Matrix), 20 (Nexus) und 21 (Omega)**

---

## 🚀 Schnellstart

1. Datei `kodi_skin_generator_v6.html` im Browser öffnen (am besten Chrome, Edge, Firefox oder Safari).
2. Projektnamen vergeben und **Skin** oder **Addon** wählen.
3. Elemente hinzufügen, verschieben, Buttons beschriften.
4. Bei jedem Button über **📚 Befehlsliste** festlegen, was beim Klick passiert.
5. Optional: Icon, Fanart und Screenshots auswählen.
6. **✔ Prüfen**, dann **⬇ ZIP exportieren**.
7. In Kodi: **Einstellungen → Addons → Aus ZIP-Datei installieren**.

Die ausführliche Schritt-für-Schritt-Anleitung findest du in der [ANLEITUNG.md](ANLEITUNG.md).

### Als Webseite nutzen (GitHub Pages)

Benenne die HTML-Datei in `index.html` um und aktiviere unter **Settings → Pages** dein Repository als Webseite. Dann kann jeder das Tool direkt über einen Link öffnen.

---

## 🎨 Skin oder Addon – was ist besser?

| | 🎨 Skin | 🔌 Addon |
|---|---|---|
| Was entsteht | eigene Oberfläche, ersetzt das Kodi-Design | Menü im Bereich *Addons → Video-Addons* |
| Poster und Flächen | werden angezeigt | werden nicht angezeigt, nur Buttons als Menü-Einträge |
| Risiko | enthält nur die Seiten, die du gebaut hast | sehr unkompliziert |
| Empfehlung | zum Experimentieren und für Fortgeschrittene | **für Einsteiger der einfachste Weg** |

---

## 📦 Was steckt in der exportierten ZIP?

**Addon**
```
plugin.video.deinname/
├── addon.xml
├── addon.py
├── icon.png
├── fanart.jpg
├── resources/screenshot-01.jpg …
└── (deine eigenen Ordner und Dateien)
```

**Skin**
```
skin.deinname/
├── addon.xml
├── icon.png
├── fanart.jpg
├── 1080i/   (Home.xml, weitere Seiten, Includes.xml, Font.xml)
├── media/   (white.png, optional background.jpg)
├── resources/screenshot-01.jpg …
└── (deine eigenen Ordner und Dateien)
```

---

## ⚠️ Hinweise

- **Internet nötig beim Öffnen:** Das Tool lädt Tailwind CSS und JSZip von einem CDN. Wer es komplett offline nutzen möchte, kann beide Bibliotheken lokal einbinden.
- **Skin-Umfang:** Ein exportierter Skin enthält nur die Seiten aus dem Generator. Kodi-Standardfenster (z.B. Bibliothek, Wiedergabe-Oberfläche) bringt er nicht mit. Für ein Menü, das sicher funktioniert, ist der Addon-Modus die robustere Wahl.
- **Emojis in Buttons** werden nur in der Vorschau angezeigt, Kodi-Schriften zeigen sie oft nicht.
- **Einige Befehle** hängen von deiner Installation ab, z.B. Live TV und TV-Programm brauchen ein PVR-Addon.
- **Eigene Befehle** sind unter *Aktion → Kodi-Befehl* möglich, siehe [Kodi-Wiki: Built-in functions](https://kodi.wiki/view/List_of_built-in_functions).
- Der Browser-Speicher ist begrenzt. Bei vielen großen Bildern regelmäßig **💾 Speichern** (JSON-Backup) nutzen.

---

## 🛠 Technik

Reines HTML, CSS und JavaScript in einer einzigen Datei. Genutzt werden [Tailwind CSS](https://tailwindcss.com/) und [JSZip](https://stuk.github.io/jszip/). Es werden keine Daten an einen Server gesendet.

---

## 📄 Lizenz

Lege hier deine Lizenz fest (z.B. MIT oder GPL-3.0) und füge eine `LICENSE`-Datei zum Repository hinzu.

---

## 🤝 Mitmachen

Fehler gefunden oder Idee für neue Befehle in der Liste? Eröffne gern ein **Issue** oder einen **Pull Request**.
