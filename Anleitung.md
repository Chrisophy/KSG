# 📖 Schritt-für-Schritt Anleitung – Kodi Video-Addon Generator v8.0 Pro

Mit dem **Kodi Video-Addon Generator v8.0 Pro** erstellst du im Handumdrehen ein funktionstüchtiges Kodi-Video-Addon (`plugin.video...`) mit einem vollkommen individuell gestalteten Vollbild-Menü (`home.xml`). Programmierkenntnisse sind dafür nicht erforderlich.

---

## Bevor du startest

- Öffne `index.html` per Doppelklick in einem Webbrowser (Chrome, Edge, Firefox oder Safari).
- Eine bestehende Internetverbindung wird beim Start benötigt, damit Tailwind CSS und JSZip geladen werden können.
- Dein Projektfortschritt wird automatisch im lokalen Speicher deines Browsers gesichert. Für langfristige Backups nutze den Button **💾 Speichern**.

---

## Schritt 1 – Projekt-Metadaten festlegen

In der linken Seitenleiste unter **1 · Projekt**:

1. **Name eingeben:** Gib deinem Addon einen Namen (z. B. „Mein Streaming Hub“). Die technische ID (z. B. `plugin.video.meinstreaminghub`) wird dabei automatisch generiert.
2. **Autor, Version & Beschreibung:** Fülle die Felder aus. Diese Informationen werden in Kodi in der Addon-Detailansicht und der `addon.xml` angezeigt.
3. **Kodi-Version:** Wähle deine Zielversion aus (**19 Matrix**, **20 Nexus** oder **21 Omega**).

> 💡 **Tipp:** Klicke oben in der Kopfzeile auf **📂 Vorlagen**, um mit vorgefertigten Layouts (Streaming-Hub, Live TV oder Musik-Player) zu starten.

---

## Schritt 2 – Elemente hinzufügen und anordnen

In der Seitenleiste unter **2 · Hinzufügen**:

| Element | Beschreibung |
|---|---|
| **📚 Befehlsliste** | Fügt direkt einen vorkonfigurierten Button aus der Befehlsdatenbank ein. |
| **🖼 Eigenes Bild** | Lädt eigene Bilddateien hoch, die als Deko oder anklickbare Schaltflächen dienen. |
| **➕ Button** | Erstellt eine Standard-Schaltfläche. |
| **🔤 Text** | Fügt ein Textfeld / eine Überschrift ein. |
| **🖼 Poster-Platzhalter** | Dient als Platzhalter für Poster-Elemente. |
| **⬛ Fläche** | Erzeugt einen farbigen Hintergrundblock. |

### Interaktion auf der Canvas:
- **Verschieben:** Ziehe Elemente per Maus oder Touch an die gewünschte Position.
- **Größe ändern:** Ziehe an der weißen Ecke unten rechts eines markierten Elements.
- **Raster / Einrasten:** Über das Kontrollkästchen *Raster / Einrasten* richtest du Elemente präzise an einem 20px-Raster aus.
- **Fehler korrigieren:** Mit **↩ Rückgängig** oder der Tastenkombination `Strg + Z` kannst du Schritte zurücknehmen.

---

## Schritt 3 – Aktionen und Befehle zuweisen

Markiere ein Element (Button oder eigenes Bild), um in der rechten Seitenleiste die **Eigenschaften** und den Bereich **⚡ Was passiert beim Klick?** aufzurufen.

### 1. Aus der Befehlsliste wählen (Empfohlen)
Klicke auf **📚 Aus Befehlsliste wählen**. Suche nach Kategorien oder Stichworten (z. B. „Filme“, „Lautstärke“, „Neustart“, „YouTube“) und tippe auf **Einsetzen** (für das markierte Element) oder **＋ Neuer Button**.

### 2. Manuelle Aktionsauswahl
Du kannst im Dropdown-Menü folgende Aktionen manuell festlegen:
- **Andere Seite öffnen:** Verlinkt auf eine weitere Menüseite innerhalb deines Addons.
- **Anderes Addon öffnen:** Startet ein fremdes Addon über dessen URI (z. B. `plugin.video.youtube/`).
- **Video / Stream abspielen:** Spielt direkt eine URL oder Datei ab (`PlayMedia(...)`).
- **Wiedergabesteuerung:** Play/Pause, Nächster Titel, Stopp, Lautstärke etc.
- **Zurück:** Navigiert zur vorherigen Menüseite (schließt das Addon auf der Startseite).
- **Kodi-Befehl:** Für fortgeschrittene Kodi `Built-in functions`.

---

## Schritt 4 – Unterseiten erstellen und verlinken

Über der Leinwand befindet sich die Seitenleiste:

1. Klicke auf **＋ Seite**, um eine neue Menüseite anzulegen.
2. Erstelle auf der Startseite einen Button/Bild und wähle als Aktion **Andere Seite öffnen**.
3. Wähle die gewünschte Zielseite im Dropdown aus.
4. Achte darauf, dass jede Unterseite eine Schaltfläche mit der Aktion **Zurück** enthält.

---

## Schritt 5 – Farben und Design anpassen

Unter **3 · Design**:

- Wähle eines der vorgefertigten **Farbthemen** (z. B. Cyberpunk, Matrix, Sonnenuntergang) oder stelle die Farben für Buttons, Fokus-Rahmen und Hintergrund individuell ein.
- Über **🖼 Hintergrundbild** kannst du ein benutzerdefiniertes Vollbild-Hintergrundbild für dein Menü laden.

Unter **4 · Werkzeuge**:

- **📐 Buttons mittig untereinander ordnen:** Richtet alle Buttons automatisch als zentrierte vertikale Liste aus.
- **📏 Alle Buttons so groß wie markierter:** Vereinheitlicht die Abmessungen aller Buttons.

---

## Schritt 6 – Addon-Bilder & Grafiken

Unter **5 · Addon-Bilder & Dateien**:

- **Icon (512×512):** Das Quadrat-Logo deines Addons in der Kodi-Übersicht.
- **Fanart (1920×1080):** Das Hintergrundbild in der Addon-Infoansicht.
- **Screenshots:** Füge bis zu 8 Vorschaubilder für die Addon-Details hinzu.

*Hinweis: Wenn du kein eigenes Icon oder Fanart hochlädst, generiert das Tool automatisch passende Standard-Grafiken.*

---

## Schritt 7 – Dateimanager (Optional)

Klicke auf **📁 Ordner & Dateien verwalten**:

1. **Ordner erstellen:** Gib einen Pfad ein (z. B. `resources/lib`) und klicke auf **＋ Ordner**.
2. **Dateien hochladen:** Wähle den Zielordner und klicke auf **＋ Dateien hinzufügen** (z. B. für Python-Skripte, Playlists, etc.).
3. **Textdateien erstellen:** Schreibe Konfigurationsdateien (z. B. `settings.xml`) direkt im integrierten Editor.

---

## Schritt 8 – Testen, Prüfen und Exportieren

1. **▶ Testen:** Aktiviert den interaktiven Vorschaumodus. Teste Seitenwechsel und prüfe, welche Befehle Kodi ausführen würde.
2. **✔ Prüfen:** Analyse-Tool für dein Projekt. Warnungen (⚠️) zeigen fehlende Links, verwaiste Seiten oder unvollständige Parameter auf.
3. **</> Code:** Zeigt die generierten XML-Dateien, `addon.py` und Konfigurationen an.
4. **⬇ ZIP exportieren:** Erstellt das finale Paket als `.zip`-Datei für die Installation in Kodi.

---

## Schritt 9 – Installation in Kodi

1. Kopiere die heruntergeladene `.zip`-Datei auf dein Kodi-Gerät.
2. Aktiviere in Kodi unter **Einstellungen → System → Addons** die Option **Unbekannte Quellen**.
3. Navigiere zu **Einstellungen → Addons → Aus ZIP-Datei installieren** und wähle die Datei aus.
4. Starte dein Addon über **Addons → Video-Addons → [Dein Addon-Name]**. Dein gestaltetes Menü öffnet sich im Vollbild.

---

## Tastenkürzel im Editor

| Taste | Aktion |
|---|---|
| **Pfeiltasten** | Markiertes Element um 20 Pixel verschieben |
| **Umschalt + Pfeiltasten** | Markiertes Element um 100 Pixel verschieben |
| **Entf / Rücktaste** | Markiertes Element löschen |
| **Strg + D** | Markiertes Element duplizieren |
| **Strg + Z** | Letzte Aktion rückgängig machen |


# Copyright (c) 2026 Team IT('s) Possible. All rights reserved.
# Version 2026.10.22
# RECHTLICHER HINWEIS:
# Jegliche Haftung und Garantie für Schäden jeglicher Art ist ausgeschlossen. 
# Dieser Code ist das geistige Eigentum der Autoren.
# Das Modifizieren, Verändern, Umschreiben oder die unautorisierte 
# Weiterverbreitung des Codes ist strengstens untersagt.