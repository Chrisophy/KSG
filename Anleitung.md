# Anleitung: Kodi Video-Addon Generator v8.1 Pro

Der Generator ist ein einzelnes HTML-Werkzeug. Du öffnest es im Browser, baust dort ein Kodi-Addon oder einen kompletten Skin zusammen und lädst es als ZIP-Datei herunter. Die ZIP installierst du dann in Kodi.

Inhalt:

1. [Überblick](#1-überblick)
2. [Start und Speicherung](#2-start-und-speicherung)
3. [Das erste Addon in fünf Minuten](#3-das-erste-addon-in-fünf-minuten)
4. [Elemente, Seiten und Aktionen](#4-elemente-seiten-und-aktionen)
5. [Design](#5-design)
6. [Testen, Prüfen und Export](#6-testen-prüfen-und-export)
7. [In Kodi installieren](#7-in-kodi-installieren)
8. [Modding-Werkstatt für Profis](#8-modding-werkstatt-für-profis)
9. [Titan-Modus: eigener Skin](#9-titan-modus-eigener-skin)
10. [Fremd-Addon einbinden](#10-fremd-addon-einbinden)
11. [Kontextmenü und Favoriten](#11-kontextmenü-und-favoriten)
12. [Eigene Dateien und custom.py](#12-eigene-dateien-und-custompy)
13. [Bekannte Grenzen](#13-bekannte-grenzen)
14. [Problemlösung](#14-problemlösung)
15. [Lizenz](#15-lizenz)

---

## 1. Überblick

Mit dem Generator baust du:

- **Ein Video-Addon** (`plugin.video.<name>`) mit eigenem Startmenü. Das Menü erscheint beim Öffnen des Addons im Vollbild, statt der Standardansicht von Kodi.
- **Einen eigenen Skin** (`skin.<name>`) im Titan-Modus. Er basiert auf Estuary und ersetzt die Oberfläche von ganz Kodi.
- **Ein Menü um ein bestehendes Addon.** Du wählst die ZIP-Datei eines fertigen Addons, und der Generator packt sie in dein Addon. Über den Live-Browser zeigst du es in deinem eigenen Menü.

Die Bedienung ist für Einsteiger gedacht. Wer tiefer einsteigen will, findet im Modding-Bereich Listen, Schalter, Python-Hooks und eigenes XML.

---

## 2. Start und Speicherung

- Beim ersten Start erscheint eine kurze Einführung. Du kannst sie jederzeit über die Hilfe wieder öffnen.
- Dein Projekt wird automatisch im Browser gespeichert (localStorage). Es bleibt erhalten, bis du den Browser-Speicher für diese Seite löschst.
- Über **Projekt sichern** exportierst du das komplette Projekt als JSON-Datei und lädst es später wieder. Das ist die sicherste Methode, bevor du größere Umbauten machst.
- **Fremd-Addon-ZIPs** (und die Titan-Profile) liegen nur im Browser (IndexedDB). Sie sind nicht im JSON-Export enthalten. Wenn du den Browser-Speicher löschst, musst du sie neu wählen.
- Mit **🚪 Beenden** verlässt du die Seite. Beim Klick auf „Zurück“ oder beim Schließen des Tabs fragt der Generator nach, ob du noch Änderungen sichern willst.

---

## 3. Das erste Addon in fünf Minuten

1. Gib dem Projekt unter **1 · Projekt** einen Namen. Der Generator erstellt daraus die Addon-ID.
2. Unter **2 · Hinzufügen** fügst du Buttons, Texte, Flächen und eigene Bilder hinzu.
3. Verschiebe Elemente mit Maus oder Finger. An der weißen Ecke änderst du die Größe.
4. Markiere ein Element und wähle rechts unter **⚡ Funktion** eine Aktion, z. B. „Seite öffnen“ oder „Kodi-Fenster öffnen“.
5. Unter **5 · Addon-Bilder & Dateien** wählst du Icon, Fanart und Screenshots.
6. Klicke auf **▶ Testen**, um das Menü wie in Kodi auszuprobieren. **✔ Prüfen** findet Aktionen, die noch fehlen.
7. Mit **⬇ ZIP exportieren** lädst du das Addon herunter.

Vorlage zum Lernen: Unter **📂 Vorlagen** findest du „Mein Kino-Hub“, ein fertiges Menü mit fünf Seiten. Vorlagen ersetzen Seiten und Elemente deines Projekts. Bilder, Dateien, Einstellungen und Modding-Schalter bleiben erhalten.

---

## 4. Elemente, Seiten und Aktionen

### Elemente

- **Buttons, Texte, Flächen, Bilder, Poster, Cover, Fortschrittsbalken** und weitere Elemente stehen unter **2 · Hinzufügen** bereit.
- Jedes Element kann eine Aktion haben. Das gilt auch für Texte, Poster und Flächen.
- **Bilder ohne Aktion** sind reine Dekoration. Sobald du rechts eine Aktion wählst, wird das Bild anklickbar und bekommt einen Fokus-Rahmen für die Fernbedienung.
- **Poster mit echtem Bild:** Markiere das Poster und trage ein Bild vom Gerät oder eine Bild-Adresse aus dem Internet ein.
- **🔐 Schutz:** Mit einem Schutz fragt Kodi vor der Aktion nach PIN oder Ja/Nein.
- **📚 Befehlsliste:** Hier suchst du Kodi-Befehle (z. B. „Filme“, „Lautstärke“, „Neustart“) und setzt sie mit einem Tipp in ein Element ein.

### Seiten

- Jede Seite hat einen eigenen **🎨 Hintergrund**.
- Seiten lassen sich **duplizieren** und mit **◀ ▶** sortieren.
- Mit **👁 Wann sichtbar?** erscheinen Elemente nur in bestimmten Situationen, zum Beispiel nur bei eingeschaltetem Ton.

### Mehr Kodi-Funktionen

- **Fortschrittsbalken** und **Cover** zeigen die laufende Wiedergabe.
- **Live-Infos** zeigen Werte wie Uhrzeit, Wetter, Jetzt-läuft-Titel oder Systeminfos.
- **Seitenübergänge** animieren den Wechsel zwischen Seiten.
- **Addon-Einstellungen (⚙):** Dein Addon bekommt eine eigene Einstellungsseite.
- **Abhängigkeiten:** Andere Addons, die dein Addon braucht, trägst du hier ein.
- **Begrüßung beim Start:** Optional erscheint beim Öffnen ein kurzer Hinweis.
- **Textdateien bearbeiten (✎):** Du kannst die Textdateien deines Addons direkt ändern.

### Live-Ansicht

Wenn die große Vorschau nicht zu sehen ist (z. B. auf dem Handy, in der Modding-Werkstatt oder beim Scrollen), erscheint ein kleines Fenster mit der Live-Ansicht.

- Am Kopf verschieben, mit **⤢** vergrößern, mit **✖** ausblenden.
- Du kannst Elemente auch dort antippen und ziehen.
- Unter **Position & Größe** verschiebst du Elemente mit **◀ ▲ ▼ ▶** punktgenau.

---

## 5. Design

- Unter **3 · Design** stellst du die Standard-Rundung von Buttons und Bildern ein.
- Buttons und Bilder können **eckig, abgerundet oder als Pille** dargestellt werden.
- Rahmen und Deckkraft lassen sich einstellen.
- Buttons können auf Wunsch ein **eigenes Bild** bekommen.
- Beim Design hilft die **Live-Ansicht**: Du siehst jede Änderung sofort.

---

## 6. Testen, Prüfen und Export

- **▶ Testen** startet eine Vorschau, die sich wie das Addon in Kodi anfühlt. Du kannst Seiten wechseln, Listen durchblättern, Schalter umlegen und zurückgehen.
- **✔ Prüfen** sucht vergessene Aktionen und zeigt sie als Liste.
- **⬇ ZIP exportieren** erstellt die Addon-ZIP. Enthalten sind das Icon, das Fanart, die Screenshots und alle Dateien, die du im Editor verändert hast.
- Das Addon bekommt eine Versionsnummer. Wenn du ein Addon mit gleichem Namen neu installieren willst und Kodi es nicht übernimmt, erhöhe die Version oder deinstalliere das alte Addon zuerst.

---

## 7. In Kodi installieren

1. Kopiere die ZIP-Datei auf das Kodi-Gerät.
2. In Kodi: **Einstellungen → Addons → Aus ZIP-Datei installieren**. Erlaube bei Bedarf „Unbekannte Quellen“.
3. Das Addon findest du unter **Addons → Video-Addons**.
4. Beim Öffnen erscheint dein Menü im Vollbild.

---

## 8. Modding-Werkstatt für Profis

Im Bereich **6 · Modding für Profis** gibt es erweiterte Funktionen:

- **Listen**, auch automatisch aus der Bibliothek, ähnlich einem Widget.
- **Kachel-Raster** und **Karussell** für Medien-Übersichten.
- **Ein/Aus-Schalter** und **Regler** für Lautstärke oder Spulen.
- **Textbox**, **Videofenster**, **Visualisierung** und **RSS**.
- **Animationen** pro Element, **Fokus-Zoom**, **Tastenbelegung** und ein **Bedingungs-Baukasten**.
- **Dialog-Seiten**, **Seiten-Befehle** und eigenes **XML**.
- **Python-Hooks**, **Autostart** und **Direkt-Links** (Deep Links).
- **Inspektor** mit allen Kodi-IDs.
- **Das komplette Projekt als JSON** lesen und bearbeiten.
- **Schalter** für Kodi-Verhalten: Beim Beenden landest du auf der Kodi-Startseite. Öffnet ein Button ein Kodi-Fenster oder ein Video, kommst du mit Zurück bzw. nach dem Video wieder in dein Menü. Beides lässt sich hier abschalten.
- **Kontextmenü:** Ein- oder Ausschalten, siehe Abschnitt 11.

### Widgets

Unter **🧩 Widgets** fügst du Reihen wie im Kodi-Hauptmenü hinzu, z. B. Neue Filme, Weiterschauen, Neue Folgen, Zufällige Filme, Neue Alben oder Inhalte aus Addons. Sie füllen sich in Kodi von selbst. Außerdem gibt es Info-Widgets (Uhr, Wetter, Jetzt läuft, System-Info), deren Teile sich zusammen bewegen.

### Editor

Alle erzeugten Dateien (z. B. `addon.py`, `addon.xml`, `home.xml`, `pages.json`) kannst du von Hand ändern. Sie kommen genau so in die ZIP.

---

## 9. Titan-Modus: eigener Skin

Der Titan-Modus baut einen echten Kodi-Skin für ganz Kodi.

1. Wähle unter **7 · ⚡ Titan-Modus** deine Kodi-Version. Der Generator lädt dazu den offiziellen Skin **Estuary** passend zur Version.
2. Passe Farben, Hintergrund, Logo, Schrift und das Hauptmenü an. Du kannst eigene Menüpunkte hinzufügen, z. B. für dein Addon.
3. Unter **📐 Layout** ziehst du Logo, Uhr, Knöpfe, Hauptmenü, Widget-Bereich und Player-Leiste an jede Stelle.
   - Das Hauptmenü kann als einzelne Buttons, waagerecht oder senkrecht angeordnet werden.
   - Eigene Bilder lassen sich als Dekoration einsetzen.
4. Mit **Undo/Redo** machst du Schritte rückgängig.
5. Im **Profi-Reiter** speicherst du Profile (in IndexedDB im Browser).
6. Der Export erzeugt eine **`skin.<name>.zip`**.

Der Skin ist eine Bearbeitung von Estuary und steht deshalb unter denselben Lizenzen (siehe Abschnitt 15). Die Datei `TITAN.txt` im Skin nennt Estuary als Grundlage.

---

## 10. Fremd-Addon einbinden

Du hast schon ein Addon, z. B. eines, das du selbst geschrieben hast? Dann kannst du es in dein Projekt einbauen.

1. Wähle die ZIP-Datei unter **🧩 Fremd-Addon**.
2. Der Generator packt sie in dein Addon. Beim Installieren wird sie automatisch entpackt und eingeschaltet.
3. Der **📂 Live-Browser** zeigt das Fremd-Addon direkt in deinem Skin:
   - Ordner öffnen sich in der Liste.
   - Zurück geht eine Ebene hoch.
   - Videos starten sofort.
   - Kodis eigene Ansicht taucht nicht auf.
4. Alternativ baust du Buttons im Stil **Taschenrechner, Linux-Desktop, Kacheln oder Liste**.

### Abhängigkeiten

Benötigte Python-Module erkennt der Generator selbst, z. B. `bs4` (BeautifulSoup), `requests` oder `feedparser`. Er trägt die passenden Kodi-Abhängigkeiten (z. B. `script.module.beautifulsoup4`) in die `addon.xml` ein.

Wenn ein Fehler wie `No module named 'bs4'` erscheint, fehlt meistens dieser Eintrag in der Haupt-`addon.xml`. Der Generator löst das automatisch.

### Eigene Einträge

Eigene Menüpunkte für das Fremd-Addon stehen in `resources/lib/custom.py` (Liste `MENUE`). Die Datei kannst du im Editor anpassen.

---

## 11. Kontextmenü und Favoriten

Im fertigen Addon öffnet ein Kontextmenü mit **langem Drücken** (Touch), **Rechtsklick** oder **Taste C**.

Je nach Eintrag zeigt es:

- **Ordner im Live-Browser:** Öffnen, Als Favorit speichern, In Kodis Ansicht öffnen, Beschreibung anzeigen.
  - Ein als Favorit gespeicherter Ordner öffnet später direkt in deinem Skin, an genau dieser Stelle.
- **Videos:** Abspielen, Zur Wiedergabeliste hinzufügen, Als Favorit speichern.
- **Artikel:** Ausführen. Kodi kann Artikel nicht als Favorit speichern, deshalb fehlt der Eintrag hier.
- **Buttons:** Ausführen. Bei Seiten und Ordnern zusätzlich Als Favorit speichern.
- **Immer:** Dieses Menü als Favorit speichern, Kodi-Favoriten öffnen und die Einstellungen des Addons, falls vorhanden.
- **Bereits gespeicherte Favoriten** heißen im Menü „aus Favoriten entfernen“.

**Ausschalten:** Im 🛠 Modding unter „🖱 Kontextmenü“.

**Eigene Einträge:** Die Funktion `kontextmenue(window, info)` in `custom.py` kann eigene Einträge ergänzen.

### Langes Drücken im Hauptmenü

Beim langen Drücken auf einen Button sendet Kodi zuerst ein künstliches „Zurück“ und direkt danach den Rechtsklick. Das Addon erkennt diese Folge und öffnet das Kontextmenü, statt das Addon zu schließen. Echte Zurück-Tasten (Fernbedienung, Esc, Handy-App) funktionieren wie gewohnt. Dadurch kann das Kontextmenü beim langen Drücken minimal verzögert erscheinen.

---

## 12. Eigene Dateien und custom.py

- **📁 Ordner & Dateien:** Eigene Dateien und Ordner nimmst du in das Addon auf.
- **resources/lib/custom.py:** Eigene Python-Funktionen. Die Liste `MENUE` enthält die Menüpunkte. Jeder Eintrag ruft eine Funktion `eintrag_N_…` auf.
- Eine Funktion gibt zurück, was passieren soll:
  - `browse:<pfad>` öffnet den Live-Browser an diesem Pfad.
  - `page:<id>` öffnet eine Seite.
  - `back`, `home` oder `exit`.
  - Oder einen Kodi-Befehl.
- Die Funktion `kontextmenue(window, info)` ergänzt das Kontextmenü.

---

## 13. Bekannte Grenzen

- Der Generator läuft im Browser. Für den Titan-Modus lädt er Estuary passend zur Kodi-Version aus dem Netz.
- Fremd-Addon-ZIPs und Titan-Profile liegen nur im Browser, nicht im JSON-Export.
- Ein Favorit für einen Ordner setzt voraus, dass die Browse-Seite im Addon existiert.
- Kodi 19: Dort werden alle Einträge im Live-Browser als abspielbar behandelt, weil Kodi 19 die dafür nötige Information nicht liefert.
- Das Kontextmenü und das Verhalten beim langen Drücken sind neu. Die Erkennung des künstlichen „Zurück“ arbeitet mit einer kurzen Wartezeit von etwa 0,4 Sekunden.

Wenn etwas davon bei dir nicht wie beschrieben funktioniert, melde es bitte mit Kodi-Version, Gerät und den Schritten, die zum Fehler geführt haben.

---

## 14. Problemlösung

| Problem | Ursache und Lösung |
|---|---|
| Ein altes Addon gleichen Namens ändert sich nicht | Deinstalliere das alte Addon oder erhöhe die Version und installiere neu. |
| `No module named 'bs4'` oder ähnlich | Eine Abhängigkeit fehlt in der `addon.xml`. Der Generator trägt sie beim Export ein, prüfe aber die Haupt-`addon.xml`. |
| Ein Fremd-Addon fehlt nach dem Neuladen der Seite | Die ZIP liegt nur im Browser. Wähle sie erneut unter „Fremd-Addon“. |
| Das Menü startet nicht im Vollbild | Prüfe, ob `home.xml` im Addon liegt und das Addon als Video-Addon installiert ist. |
| Änderungen gehen verloren | Sichere das Projekt regelmäßig über „Projekt sichern“ als JSON. |
| Kontextmenü erscheint nicht | Prüfe unter 🛠 Modding, ob „🖱 Kontextmenü“ eingeschaltet ist. |

---

## 15. Lizenz

**Kodi Video-Addon Generator v8.1 Pro**
© 2026 Team IT('s) Possible. Alle Rechte vorbehalten.

Freeware-Lizenz: Der Generator ist kostenlos für die Kodi-Community, aber **nicht Open Source**. Ohne schriftliche Erlaubnis verboten sind:

- Verkauf, Vermietung und Angebot gegen Bezahlung,
- Werbung,
- das Bereitstellen auf anderen Seiten, Servern oder App-Stores,
- das Verbreiten veränderter Fassungen,
- das Entfernen dieses Hinweises.

Die mit dem Generator gebauten Addons gehören dir.

Original: https://chrisophy.github.io/KSG/
Lizenztext: https://github.com/Chrisophy/KSG/blob/main/LICENSE

**Estuary:** Estuary stammt von phil65 und Team Kodi. Der Code steht unter GPL-2.0, die Grafiken unter CC BY-SA 4.0. Ein daraus gebauter Skin steht unter denselben freien Lizenzen und nennt Estuary als Grundlage.
