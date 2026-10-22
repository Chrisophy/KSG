# 📖 Handbuch – Kodi Video-Addon Generator v8.1 by IT('s) Possible

Mit dem **Kodi Video-Addon Generator** baust du ein funktionierendes Kodi-Video-Addon (`plugin.video.…`) mit einem komplett selbst gestalteten Vollbild-Menü (`home.xml`). Programmierkenntnisse brauchst du nicht – wer sie hat, bekommt in der **🛠 Modding-Werkstatt** volle Kontrolle bis ins letzte Detail.

> 💚 Das Werkzeug ist gratis für die Kodi-Community – für Anfänger und Profis. Es darf nicht verkauft werden. Die damit gebauten Addons gehören dir.

---

## Inhalt

**Teil A – Grundlagen (für alle)**
1. [Was baust du hier eigentlich?](#1-was-baust-du-hier-eigentlich)
2. [Bevor du startest](#2-bevor-du-startest)
3. [Die Oberfläche im Überblick](#3-die-oberfläche-im-überblick)
4. [Schritt 1 – Projekt anlegen](#4-schritt-1--projekt-anlegen)
5. [Schritt 2 – Mit einer Vorlage starten](#5-schritt-2--mit-einer-vorlage-starten)
6. [Schritt 3 – Elemente hinzufügen](#6-schritt-3--elemente-hinzufügen)
7. [Schritt 4 – Auf der Bühne arbeiten](#7-schritt-4--auf-der-bühne-arbeiten)
8. [Schritt 5 – Eigenschaften einstellen](#8-schritt-5--eigenschaften-einstellen)
9. [Schritt 6 – Aktionen: Was passiert beim Klick?](#9-schritt-6--aktionen-was-passiert-beim-klick)
10. [Schritt 7 – Seiten anlegen und verlinken](#10-schritt-7--seiten-anlegen-und-verlinken)
11. [Schritt 8 – Design](#11-schritt-8--design)
12. [Schritt 9 – Werkzeuge](#12-schritt-9--werkzeuge)
13. [Schritt 10 – Addon-Bilder, Dateien und Einstellungen](#13-schritt-10--addon-bilder-dateien-und-einstellungen)
14. [Schritt 11 – Testen, Prüfen, Editor und Export](#14-schritt-11--testen-prüfen-editor-und-export)
15. [Schritt 12 – Installation in Kodi](#15-schritt-12--installation-in-kodi)

**Teil B – Die neuen Bausteine im Detail**
16. [Liste, Kachel-Raster, Karussell und Widgets](#16-liste-kachel-raster-karussell-und-widgets)
17. [Ein/Aus-Schalter](#17-einaus-schalter)
18. [Regler (Lautstärke und Spulen)](#18-regler-lautstärke-und-spulen)
19. [Textbox, Laufschrift und mehrzeiliger Text](#19-textbox-laufschrift-und-mehrzeiliger-text)
20. [Videofenster, Visualisierung, RSS-Ticker](#20-videofenster-visualisierung-rss-ticker)
21. [🛠 Modding pro Element](#21--modding-pro-element)

**Teil C – Die Modding-Werkstatt**
22. [Überblick](#22-überblick)
23. [🎛 Schalter](#23--schalter)
24. [🧩 Bausteine](#24--bausteine)
25. [🧰 Werkzeuge](#25--werkzeuge)
26. [📄 Seiten-Tuning](#26--seiten-tuning)
27. [⌨ Tasten](#27--tasten)
28. [🧠 Bedingungen](#28--bedingungen)
29. [🔍 Inspektor & Links](#29--inspektor--links)
30. [🧬 Projekt-JSON](#30--projekt-json)

**Teil D – Für Profis**
31. [Was im ZIP steckt](#31-was-im-zip-steckt)
32. [Die Kodi-IDs](#32-die-kodi-ids)
33. [pages.json – die Schaltzentrale](#33-pagesjson--die-schaltzentrale)
34. [Python-Hooks (custom.py)](#34-python-hooks-custompy)
35. [Direkt-Links und Favoriten](#35-direkt-links-und-favoriten)
36. [Merker, Zustände und Speicherorte](#36-merker-zustände-und-speicherorte)

**Teil E – Rezepte (Schritt für Schritt)**
37. [Rezepte](#37-rezepte)

**Teil F – Hilfe**
38. [Vorschau und Kodi – die Unterschiede](#38-vorschau-und-kodi--die-unterschiede)
39. [Fehlerbehebung und häufige Fragen](#39-fehlerbehebung-und-häufige-fragen)
40. [Tastenkürzel](#40-tastenkürzel)

---

# Teil A – Grundlagen

## 1. Was baust du hier eigentlich?

Du baust ein ganz normales **Kodi-Video-Addon**. Das Besondere: Beim Start zeigt es nicht die übliche Kodi-Liste, sondern **dein eigenes, gestaltetes Menü** im Vollbild.

- Es ist **kein System-Skin**. Der Kodi-Skin (z. B. Estuary) bleibt, wie er ist.
- Dein Menü kann aus mehreren **Seiten** bestehen (Startseite = `home.xml`, weitere Seiten = `page_1.xml`, `page_2.xml` …).
- Jedes Element kann eine **Aktion** auslösen: Seite wechseln, Video abspielen, Kodi-Befehl ausführen, anderes Addon öffnen und vieles mehr.
- Unterstützt werden **Kodi 19 Matrix, 20 Nexus und 21 Omega**.

---

## 2. Bevor du startest

- Öffne die HTML-Datei per Doppelklick in einem aktuellen Browser (Chrome, Edge, Firefox oder Safari). Am Handy oder Tablet funktioniert es auch.
- Beim Öffnen sollte eine **Internetverbindung** bestehen, damit das Design (Tailwind CSS) geladen wird. Der **ZIP-Export braucht kein Internet** – der Generator hat einen eigenen ZIP-Schreiber eingebaut.
- Dein Projekt wird **automatisch im Browser gespeichert**. Für ein sicheres Backup nutze **💾 Speichern** (unten links). Damit erhältst du eine `…_projekt.json`, die du jederzeit mit **📥 Laden** wieder öffnen kannst.
- Beim ersten Start erscheint die Kurzhilfe **❓ So geht's**. Du kannst sie jederzeit oben wieder öffnen.
- **Beenden:** Die Seite verlässt du sauber mit **🚪 Beenden**. Bei „Zurück“ im Browser oder beim Schließen des Tabs fragt der Generator vorher nach, damit nichts verloren geht.

> 💡 **Tipp:** Speichere vor größeren Umbauten (Vorlage laden, Projekt-JSON bearbeiten) immer ein Backup mit **💾 Speichern**.

---

## 3. Die Oberfläche im Überblick

### Kopfzeile

| Button | Funktion |
|---|---|
| **🗑 Neu** | Startet ein neues Projekt (vorher Rückfrage). |
| **❓ So geht's** | Kurzhilfe direkt im Generator. |
| **📂 Vorlagen** | Fertige Menüs als Startpunkt (siehe Schritt 2). |
| **↩ Rückgängig / ↪ Wiederholen** | Schritte zurücknehmen bzw. wiederholen. |
| **▶ Testen** | Vorschau-Modus: Klicks lösen die Aktionen aus, wie in Kodi. Nochmal klicken = **✏ Bearbeiten**. |
| **✔ Prüfen** | Sucht vergessene Aktionen, kaputte Links, fehlende Bilder, XML-Fehler usw. |
| **💻 Editor** | Alle erzeugten Dateien von Hand ansehen und ändern. |
| **🛠 Modding** | Öffnet die Modding-Werkstatt (Teil C). |
| **⬇ ZIP exportieren** | Erstellt das fertige Addon als installierbare ZIP. |
| **🚪 Beenden** | Generator sicher verlassen. |

### Linke Seitenleiste (Einstellungen & Werkzeuge)

1. **Projekt** – Name, Autor, Version, Beschreibung, Kodi-Version
2. **Hinzufügen** – Elemente, Bilder, Schnell-Buttons, Live-Infos
3. **Design** – Farbthemen, Farben, Hintergrund, Übergänge, Rundung, Raster
4. **Werkzeuge** – Ordnen, Größen angleichen, Kopieren/Einfügen, Editor
5. **Addon-Bilder & Dateien** – Icon, Fanart, Screenshots, Dateien, Addon-Einstellungen
6. **Modding für Profis** – Modding-Werkstatt und die neuen Bausteine

### Mitte: Seitenleiste und Bühne

Oben die **Seiten-Buttons** (🏠 = Startseite, 🪟 = Dialog-Seite), darunter die **Bühne** im Format 1920 × 1080 Pixel – genau so groß wie das Menü später in Kodi.

### Rechts: Eigenschaften

Zeigt alle Einstellungen des **markierten** Elements. Auf dem Handy stehen die Eigenschaften direkt unter der Bühne.

### Handy und Tablet

Oben schaltest du zwischen **📱 Vorschau & Seiten** und **⚙️ Einstellungen & Werkzeuge** um.

---

## 4. Schritt 1 – Projekt anlegen

In der linken Leiste unter **1 · Projekt**:

1. **Wie soll es heißen?** – Der Name deines Addons. Daraus entsteht automatisch die technische ID, z. B. „Mein Streaming Hub“ → `plugin.video.meinstreaminghub`.
2. **Autor** und **Version** – Mit **＋** neben der Version erhöhst du sie um 1 (z. B. `1.0.0` → `1.0.1`). Wichtig bei Updates: Kodi erkennt eine neue Version nur, wenn die Nummer höher ist.
3. **Kurzbeschreibung** – Erscheint in Kodi in den Addon-Details.
4. **Lizenz** – Standard ist `GPL-2.0-or-later`.
5. **Kodi-Version** – 19 Matrix, 20 Nexus oder 21 Omega.

### ⚙ Erweiterte Addon-Angaben (optional)

| Feld | Wirkung |
|---|---|
| **Webseite** | Wird in der `addon.xml` eingetragen. |
| **Neu in dieser Version** | Änderungstext, den Kodi bei Updates zeigt. |
| **Begrüßung beim Start** | Kleine Meldung beim Öffnen des Addons, z. B. „Willkommen im Hub!“. |
| **Zusätzliche Abhängigkeiten** | Andere Addons, die dein Addon braucht. Kodi installiert sie automatisch mit. Schnell-Buttons: `requests`, `beautifulsoup4`, `inputstreamhelper`, `routing` (ein Klick = hinzufügen, nochmal = entfernen). |

---

## 5. Schritt 2 – Mit einer Vorlage starten

Oben auf **📂 Vorlagen**:

| Vorlage | Inhalt |
|---|---|
| **🎬 Streaming-Hub** | Startseite mit Buttons, Filme-Seite mit Postern, Live-TV-Seite |
| **📺 Live TV** | Senderliste mit Abspiel-Buttons |
| **🎵 Musik-Player** | Cover, Titel, Fortschritt, Play/Pause, Weiter, Stopp |
| **🛠 Profi-Menü** | Liste, Widgets aus der Bibliothek, Ein/Aus-Schalter, Lautstärke-Regler, Videofenster, Kindermodus mit Bedingung – ideal zum Kennenlernen der neuen Funktionen |
| **📄 Leer** | Nur eine Überschrift und ein Button |

> ⚠️ Eine Vorlage **ersetzt alle Seiten und Elemente**. Erhalten bleiben: Projektangaben, Design, Bilder, Dateien, Addon-Einstellungen und Modding-Schalter. Von Hand geänderte Dateien aus dem Editor werden zurückgesetzt.

---

## 6. Schritt 3 – Elemente hinzufügen

Ein Klick fügt das Element **in der Mitte der Bühne** ein. Danach einfach an die richtige Stelle ziehen.

### Alle Elemente

| Element | Wo? | Wofür? |
|---|---|---|
| **➕ Button** | 2 · Hinzufügen | Klassischer Menü-Button mit Text, Farbe oder eigenem Bild |
| **🔤 Text** | 2 · Hinzufügen | Überschriften, Hinweise, Live-Infos (Uhrzeit, Wetter …) |
| **🖼 Poster-Platzhalter** | 2 · Hinzufügen | Fläche für ein Poster – mit Bild vom Gerät oder Bild-Adresse |
| **⬛ Fläche** | 2 · Hinzufügen | Farbiger Block, z. B. als Hintergrund für Gruppen |
| **▬ Fortschrittsbalken** | 2 · Hinzufügen | Zeigt den Fortschritt der laufenden Wiedergabe |
| **🎵 Cover** | 2 · Hinzufügen | Bild bzw. Cover des gerade laufenden Titels |
| **🖼 Eigenes Bild** | 2 · Hinzufügen | Eigene Bilddatei vom Gerät (mehrere auf einmal möglich) |
| **📋 Liste** | 6 · Modding | Blätterbare Liste, Kachel-Raster, Karussell oder Widget |
| **🔘 Schalter** | 6 · Modding | Echter Ein/Aus-Schalter, der sich den Zustand merkt |
| **🎚 Regler** | 6 · Modding | Lautstärke oder Spulen |
| **📝 Textbox** | 6 · Modding | Mehrzeiliger Text, scrollt automatisch |
| **📺 Videofenster** | 6 · Modding | Laufendes Video als Fenster im Menü |
| **🌈 Visualisierung** | 6 · Modding | Musik-Visualisierung |
| **📡 RSS-Ticker** | 🛠 Modding → Bausteine | Nachrichten-Laufband aus Kodi |

### 📚 Befehlsliste

Über **📚 Befehlsliste** wählst du aus über 90 fertigen Kodi-Befehlen. Mit **＋ Neuer Button** entsteht sofort ein passender Button (Text, Symbol und Aktion schon eingestellt). Mehr dazu in Schritt 6.

### Schnell-Buttons

Fertige Buttons mit eingestellter Aktion: **🎬 Filme**, **📺 Live TV**, **🎵 Musik** (öffnen eine andere Seite), **⚙ Einstellungen**, **🔧 Addon-Optionen**, **⏯ Play/Pause**, **⬅ Zurück**.

### Live-Infos

Texte, die Kodi während der Nutzung selbst ausfüllt:

| Live-Info | Kodi-Code |
|---|---|
| 🕒 Uhrzeit | `$INFO[System.Time]` |
| 🕒 Uhrzeit mit Sekunden | `$INFO[System.Time(hh:mm:ss)]` |
| 📅 Datum | `$INFO[System.Date]` |
| 📆 Datum kurz | `$INFO[System.Date(dd.mm.yyyy)]` |
| 🌡 Temperatur | `$INFO[Weather.Temperature]` |
| ☁ Wetter | `$INFO[Weather.Conditions]` |
| 📍 Wetter-Ort | `$INFO[Weather.Location]` |
| 🎵 Läuft gerade | `$INFO[Player.Title]` |
| ⏱ Laufzeit | `$INFO[Player.Time] / $INFO[Player.Duration]` |
| 🎤 Interpret | `$INFO[MusicPlayer.Artist]` |
| 🎬 Filmtitel | `$INFO[VideoPlayer.Title]` |
| 💾 Freier Speicher | `$INFO[System.FreeMemory]` |
| ⚙ CPU-Last | `$INFO[System.CPUUsage]` |
| 🌐 IP-Adresse | `$INFO[Network.IPAddress]` |
| ℹ Kodi-Version | `$INFO[System.BuildVersion]` |

Ein Klick unter **Live-Infos** erzeugt einen neuen Text. In Buttons, Texten, Textboxen und Schaltern fügst du Live-Infos über **➕ Live-Info einfügen …** in die Beschriftung ein. In der Vorschau siehst du Beispielwerte, die Uhrzeit läuft live mit.

---

## 7. Schritt 4 – Auf der Bühne arbeiten

- **Markieren:** Element anklicken. Es bekommt einen weißen Rahmen.
- **Verschieben:** Mit Maus oder Finger ziehen.
- **Größe ändern:** An der **weißen Ecke unten rechts** ziehen.
- **Pfeiltasten:** Verschieben um eine Rasterweite (Standard 20 px), mit **Umschalt** um 100 px.
- **Raster / Einrasten:** Unter 3 · Design ein- und ausschalten. Die Rastergröße (5–80 px) stellst du in der Modding-Werkstatt ein.
- **🔒 Sperren:** In den Eigenschaften. Gesperrte Elemente lassen sich nicht mehr versehentlich verschieben.
- **Ebenen:** **⬆ nach vorn** / **⬇ nach hinten** legt Elemente über- oder untereinander.
- **Abwählen:** Auf eine leere Stelle der Bühne klicken.

> 💡 Alle Tastenkürzel findest du am Ende dieses Handbuchs.

---

## 8. Schritt 5 – Eigenschaften einstellen

Was rechts erscheint, hängt von der Art des Elements ab.

### Beschriftung und Text

- **Beschriftung** – Text auf Button, Text, Poster oder Schalter. Bei der Textbox gibt es ein großes Textfeld.
- **➕ Live-Info einfügen** – Hängt eine Live-Info an die Beschriftung an.
- **Symbol (Emoji)** – Nur bei Buttons. ⚠️ Nur in der Vorschau sichtbar, die meisten Kodi-Schriften zeigen keine Emojis.
- **Textausrichtung** – Links, mittig oder rechts.
- **Textfarbe** – Bei Buttons, Schaltern und Listen. **Standard** setzt sie zurück.

### Farbe

Je nach Element heißt das Feld **Farbe**, **Textfarbe**, **Farbe der Einträge**, **Farbe der Leiste** oder **Farbe des Balkens**. **Standard** übernimmt wieder die Farbe aus dem Design.

### Bilder

- **Bild / Poster-Bild:** **🖼 Bild vom Gerät wählen** oder eine **Bild-Adresse** eintragen (`https://…`). Profis können auch Kodi-Pfade wie `special://…` oder `$INFO[…]` nutzen. Ein Bild vom Gerät hat Vorrang vor der Adresse.
- **Eigenes Bild als Button-Hintergrund:** Der Button zeigt statt der Farbe ein Bild. Wenn das Bild allein wirken soll, die Beschriftung leeren.
- **Bildanpassung:**
  - *Ganzes Bild zeigen* – Seitenverhältnis bleibt, ggf. mit Rand
  - *Fläche füllen* – füllt alles, Ränder werden abgeschnitten
  - *Strecken* – auf die Fläche gezogen

### 🔘 Form & Stil

Für Buttons, Poster, Flächen, Bilder, Cover, Listen und Schalter:

| Einstellung | Wirkung |
|---|---|
| **Vorgaben** | ▢ Eckig, ▢ Abgerundet, 💊 Pille, ◻ Nur Rahmen, 🪟 Glas |
| **Rundung der Ecken** | 0 % = eckig, 100 % = Pille. Ohne eigene Einstellung gilt die Rundung aus dem Design. Bei Listen gilt sie für jeden Eintrag. |
| **Rahmen (Dicke)** | 0–20 px, mit eigener Rahmenfarbe |
| **Deckkraft** | 0–100 % |

> 💡 Bei Bildern sieht die Rundung mit „Fläche füllen“ am schönsten aus.

### Position & Größe

X, Y, Breite und Höhe in Pixeln (Bühne = 1920 × 1080). **↔ mittig** und **↕ mittig** zentrieren das Element.

### 👁 Wann sichtbar? (in Kodi)

| Auswahl | Bedeutung |
|---|---|
| Immer | Standard |
| Nur wenn etwas läuft | `Player.HasMedia` |
| Nur wenn nichts läuft | `!Player.HasMedia` |
| Nur wenn ein Video läuft | `Player.HasVideo` |
| Nur wenn Musik läuft | `Player.HasAudio` |
| Nur bei Pause | `Player.Paused` |
| Nur mit / ohne Internet | `System.InternetState` / `!System.InternetState` |
| Eigene Bedingung (Profis) | Freies Feld für jede Kodi-Bedingung |

Mit **🧠 Baukasten** öffnest du den Bedingungs-Baukasten (siehe Abschnitt 28).

> ⚠️ In der Vorschau sind **alle** Elemente immer sichtbar. Kodi blendet sie später je nach Bedingung ein oder aus.

---

## 9. Schritt 6 – Aktionen: Was passiert beim Klick?

Jedes Element kann eine Aktion bekommen – nicht nur Buttons, auch Texte, Bilder, Poster, Flächen, Cover, Textboxen, Videofenster und mehr. Sobald ein Element eine Aktion hat, kann man es in Kodi mit Maus oder Fernbedienung auswählen (mit Fokus-Rahmen).

> Listen, Schalter und Regler haben eigene Einstellungen statt dieses Bereichs (Teil B).

### Alle Aktionen

| Aktion | Was passiert? |
|---|---|
| **Nichts (nur Optik)** | Reine Deko |
| **Andere Seite öffnen** | Wechselt auf eine Seite deines Menüs |
| **Anderes Addon öffnen** | z. B. `plugin://plugin.video.youtube/` |
| **Video / Stream abspielen** | Internet-Adresse oder Dateipfad (`PlayMedia(…)`) |
| **Play / Pause**, **Nächster Titel**, **Wiedergabe stoppen** | Wiedergabesteuerung |
| **Zurück (vorherige Seite)** | Eine Seite zurück; auf der Startseite schließt sich das Addon und Kodi zeigt die Kodi-Startseite |
| **Zur Startseite dieses Addons** | Springt direkt zur Startseite deines Menüs – egal wie tief man drin ist |
| **Addon komplett schließen** | Beendet dein Addon von jeder Seite aus und kehrt zur Kodi-Startseite zurück |
| **Kodi-Einstellungen öffnen** | Öffnet das Einstellungs-Menü von Kodi |
| **Kodi beenden** | Schließt Kodi |
| **Einstellungen dieses Addons öffnen** | Öffnet die Optionen, die du selbst angelegt hast (Schritt 10) |
| **Datei aus diesem Addon abspielen** | z. B. `resources/playlist.m3u` (Datei vorher in „📁 Ordner & Dateien“ anlegen) |
| **Kodi-Befehl** | Jeder Kodi-Befehl (aus der Befehlsliste oder selbst geschrieben) |
| **Python-Funktion (custom.py)** | Ruft eine eigene Python-Funktion auf (Profis, Abschnitt 34) |

### 📚 Aus der Befehlsliste wählen

Suche nach Stichworten (z. B. „Filme“, „Lautstärke“, „Neustart“, „YouTube“) oder wähle eine Kategorie:

| Kategorie | Beispiele |
|---|---|
| **Navigation** | Filme- und Serien-Bibliothek, Genres, Neue Filme, Favoriten, Suche, Live TV, TV-Programm, Addon-Browser, Ereignisprotokoll |
| **Wiedergabe** | Play/Pause, Stopp, Spulen, Untertitel, Audiospur, Vollbild, Seitenverhältnis, Codec-Info, Party-Modus |
| **Lautstärke** | Lauter, Leiser, Stumm |
| **Einstellungen** | Oberfläche, Player, Medien, Dienste, Profile, System-Info, TV |
| **System** | Bibliothek aktualisieren/säubern, Addon-Updates, Bildschirmfoto, Benachrichtigung, Sleep-Timer, Neustart, Ausschalten |
| **Addons** | YouTube, Netflix, Twitch, Radio.de, eigenes Addon, Addon-Einstellungen |
| **Abspielen** | Video direkt abspielen, Playlist öffnen |
| **Profi** | Eigenschaft setzen/löschen, Skin-Schalter, Fokus setzen, Lautstärke auf 50 %, zu 50 % spulen, Container neu laden |

- **Einsetzen** gibt den Befehl dem markierten Element.
- **＋ Neuer Button** erzeugt einen fertigen Button.

> ⚠️ Befehle mit Platzhaltern wie `DEINE.ADDON.ID` oder `PlayMedia(https://)` musst du anpassen. **✔ Prüfen** erinnert dich daran.

### Was passiert mit dem Menü bei Kodi-Fenstern und Videos?

Befehle, die ein anderes Fenster öffnen oder etwas abspielen (`ActivateWindow`, `PlayMedia`, `RunAddon`, `RunPlugin`, `RunScript` …), schließen dein Menü automatisch **vorher**. Sonst würde das Menü über dem Video oder dem anderen Fenster hängen bleiben.

Danach geht es so weiter (Schalter **↩ Nach Kodi-Fenstern zurück ins Menü**, Standard: an):

- **Kodi-Fenster** (z. B. Filme-Bibliothek, Favoriten, ein anderes Addon): Mit **Zurück** kommst du wieder **in dein Menü** – auf dieselbe Seite.
- **Video:** Nach dem Stoppen bzw. am Ende des Videos öffnet sich dein Menü wieder.
- **Ausnahmen:** Nach `ActivateWindow(home)` (Kodi-Startseite), `Quit`, `RestartApp`, `Reboot`, `Powerdown`, `Suspend`, `Hibernate`, `Shutdown` und `ActivateScreensaver` endet das Addon – dort soll man ja gerade hin.

Alle anderen Befehle (z. B. Lautstärke, Benachrichtigung) laufen, während das Menü offen bleibt.

### 🔐 Schutz (optional)

Sobald ein Element eine Aktion hat:

- **PIN-Sperre (Kindersicherung):** 1–8 Ziffern. Kodi fragt vor der Aktion nach dem PIN. Ein einfacher Schutz vor Kindern, kein echtes Passwort.
- **Sicherheitsfrage:** z. B. „Kodi wirklich beenden?“ – Kodi fragt vorher mit Ja/Nein.

---

## 10. Schritt 7 – Seiten anlegen und verlinken

Über der Bühne:

| Button | Funktion |
|---|---|
| **＋ Seite** | Neue Seite (mit Überschrift und Zurück-Button) |
| **✏ Umbenennen** | Seitennamen ändern |
| **🎨 Hintergrund** | Eigene Farbe oder eigenes Bild nur für diese Seite. **↺ Wie im Design** setzt zurück. |
| **◀ / ▶** | Reihenfolge der Seiten ändern (die Startseite bleibt immer vorne) |
| **🗑 Seite löschen** | Löscht die Seite. Links dorthin werden automatisch entfernt. |

**Seiten duplizieren:** 4 · Werkzeuge → **⧉ Diese Seite duplizieren**.

### So verlinkst du Seiten

1. Lege eine neue Seite an.
2. Gehe zurück zur Startseite und markiere einen Button (oder einen Listen-Eintrag).
3. Wähle **Andere Seite öffnen** und die Zielseite.
4. Jede Unterseite braucht eine Möglichkeit zurück: einen Button mit **Zurück**. Die Zurück-Taste der Fernbedienung funktioniert zusätzlich immer.

> 💡 **✔ Prüfen** warnt, wenn eine Seite nicht erreichbar ist oder kein anklickbares Element hat.

---

## 11. Schritt 8 – Design

Unter **3 · Design**:

- **Farbthemen:** Standard, Cyberpunk, Matrix, Sonnenuntergang, Hell, Netflix, Ozean, Wald, Violett, Monochrom.
- **Eigene Farben:** **Buttons** (Grundfarbe), **Fokus** (Farbe des ausgewählten Elements), **Hintergrund**.
- **🖼 Hintergrundbild:** Gilt für alle Seiten ohne eigenen Hintergrund. **✖** entfernt es.
- **Übergang beim Seitenwechsel:** Einblenden, Hereinschieben, Heranzoomen oder Keiner.
- **Rundung aller Buttons:** 0 % (eckig) bis 100 % (Pille). Einzelne Elemente stellst du unter „Form & Stil“ anders ein.
- **Raster / Einrasten:** Hilfsraster auf der Bühne und Einrasten beim Verschieben.

Weitere Feinheiten (Fokus-Zoom, Textschatten, Standard-Schrift, Fokus-Textfarbe, Schalterfarbe) stehen in der Modding-Werkstatt.

---

## 12. Schritt 9 – Werkzeuge

Unter **4 · Werkzeuge**:

| Werkzeug | Wirkung |
|---|---|
| **📐 Buttons mittig untereinander ordnen** | Alle Buttons als zentrierte Spalte |
| **📏 Alle Buttons so groß wie markierter** | Einheitliche Größe |
| **⧉ Diese Seite duplizieren** | Kopie der aktuellen Seite |
| **🔲 Buttons im Raster anordnen …** | Fragt nach der Spaltenzahl (1–8) und ordnet alle Buttons an |
| **🎨 Stil des markierten Buttons auf alle Buttons** | Überträgt Rundung, Rahmen, Deckkraft, Ausrichtung, Textfarbe, Schrift, Animationen und Farbe |
| **📋 Kopieren / 📌 Einfügen** | Element kopieren – auch auf andere Seiten |
| **💻 Dateien von Hand bearbeiten** | Öffnet den Editor |

Viele weitere Werkzeuge (Ausrichten, Verteilen, Spiegeln, Skalieren …) findest du in der Modding-Werkstatt unter **🧰 Werkzeuge**.

---

## 13. Schritt 10 – Addon-Bilder, Dateien und Einstellungen

Unter **5 · Addon-Bilder & Dateien**:

### Icon, Fanart, Screenshots

| Bild | Format | Hinweis |
|---|---|---|
| **Icon** | quadratisch (wird auf 512 × 512 gebracht) | Logo in der Kodi-Addon-Übersicht |
| **Fanart** | 16:9 (1920 × 1080) | Hintergrund in den Addon-Details |
| **Screenshots** | bis zu 8 Bilder | Vorschaubilder in den Addon-Details |

Alles wird automatisch ins Addon **und** in die `addon.xml` eingetragen. Ohne eigenes Icon erzeugt der Generator eines mit dem Anfangsbuchstaben; ohne eigenes Fanart wird das Hintergrundbild oder ein Farbverlauf verwendet.

### 📁 Ordner & Dateien verwalten

1. **Ordner anlegen:** z. B. `resources/lib` → **＋ Ordner**.
2. **Dateien hinzufügen:** Zielordner wählen → **＋ Dateien hinzufügen** (max. 4 MB pro Datei). Geeignet für Playlists, Skripte, Musik, Bilder usw.
3. **📝 Textdatei selbst schreiben:** Mit Vorlagen für **M3U-Playlist**, **Python-Hilfsdatei** und **changelog.txt**.
4. **✎** öffnet eine Textdatei zum Bearbeiten, **✖** löscht Datei oder Ordner.

> ⚠️ `addon.py`, `addon.xml`, `pages.json`, alles unter `resources/skins` sowie – wenn genutzt – `resources/settings.xml` und `service.py` werden automatisch erzeugt. Diese bearbeitest du im **💻 Editor**.

### ⚙ Einstellungen deines Addons bauen

Hier legst du Optionen an, die man in Kodi unter **Addon → Konfigurieren** ändern kann:

| Art | Startwert |
|---|---|
| **Schalter (An/Aus)** | „an“ oder „aus“ |
| **Text** | beliebiger Text |
| **Zahl** | z. B. 10 |
| **Auswahlliste** | Werte mit Komma trennen, z. B. „Klein, Mittel, Groß“ |

- Daraus entsteht automatisch `resources/settings.xml`.
- Ein Button mit der Aktion **Einstellungen dieses Addons öffnen** öffnet sie direkt.
- **An/Aus-Optionen** kannst du mit einem **🔘 Schalter** direkt im Menü umschalten (Abschnitt 17).
- Im eigenen Python-Code liest du eine Option mit `xbmcaddon.Addon().getSetting('ID')`. Die ID steht in der Liste unter jeder Option.

---

## 14. Schritt 11 – Testen, Prüfen, Editor und Export

### ▶ Testen

Im Testmodus reagiert die Bühne wie Kodi:

- Seitenwechsel, **Zurück** und **Zur Startseite** funktionieren echt.
- Listen-Einträge sind einzeln anklickbar.
- Schalter wechseln zwischen 🟢 AN und ⚪ AUS.
- Regler springen an die angeklickte Stelle.
- PIN-Sperre und Sicherheitsfrage werden abgefragt.
- Bei Kodi-Befehlen siehst du unten rechts, **was Kodi ausführen würde**.

### ✔ Prüfen

Zeigt Warnungen (⚠️) und Tipps (💡), zum Beispiel:

- Buttons ohne Aktion, fehlende Video-Adressen, Platzhalter in Befehlen
- Links auf gelöschte Seiten, nicht erreichbare Seiten, Seiten ohne anklickbares Element
- fehlende Bilder oder Dateien
- Listen ohne Einträge oder ohne Quelle, Schalter ohne Merker/Einstellung
- ungültige PINs, Fehler in eigenen XML-Zeilen
- Python-Funktion gewählt, aber Python-Hooks aus
- doppelt belegte oder gesperrte Tasten
- Hintergrundmusik ohne Datei

Beim Export werden Warnungen automatisch angezeigt. Du kannst dann **Trotzdem exportieren**.

### 💻 Editor

Zeigt **alle erzeugten Textdateien** (`addon.py`, `addon.xml`, `home.xml`, `page_1.xml`, `pages.json`, `settings.xml`, `service.py`, `custom.py` …):

- Datei oben auswählen, ändern, mit **💾 Übernehmen** (oder **Strg + S**) speichern.
- XML und JSON werden beim Übernehmen auf Fehler geprüft.
- Geänderte Dateien sind mit **✎** markiert und landen genau so in der ZIP.
- **↺ Original wiederherstellen** bzw. **↺ Alle Originale** macht deine Änderungen rückgängig.
- **Tab** rückt ein (4 Leerzeichen in Python, 2 in XML).

> ⚠️ Eine von Hand geänderte Datei aktualisiert sich **nicht mehr automatisch**, wenn du danach im Designer etwas änderst. Stelle dann das Original wieder her oder passe die Datei erneut an.

### ⬇ ZIP exportieren

Erstellt `plugin.video.<deine-id>.zip` – fertig zur Installation.

---

## 15. Schritt 12 – Installation in Kodi

1. Kopiere die ZIP-Datei auf dein Kodi-Gerät (USB-Stick, Netzwerkordner, Download-Ordner).
2. Kodi: **Einstellungen → System → Addons → Unbekannte Quellen** einschalten.
3. **Einstellungen → Addons → Aus ZIP-Datei installieren** und die Datei auswählen.
4. Starte dein Addon über **Addons → Video-Addons → [Dein Addon]**. Dein Menü öffnet sich im Vollbild. Kodis Video-Ansicht wird dabei übersprungen.
5. Beim Beenden (Zurück auf der Startseite deines Menüs oder „Addon komplett schließen“) landest du auf der **Kodi-Startseite**.

**Update installieren:** Version erhöhen (**＋** neben der Version), neu exportieren und wieder „Aus ZIP-Datei installieren“. Ändert sich nichts, das alte Addon vorher deinstallieren.

---

# Teil B – Die neuen Bausteine im Detail

## 16. Liste, Kachel-Raster, Karussell und Widgets

Listen sind ideal für Menüs mit vielen Einträgen. Man blättert mit der Fernbedienung durch, ohne dass du jeden Button einzeln platzieren musst.

### Art der Liste

| Art | Verhalten |
|---|---|
| **Liste (normal)** | Klassische Liste, senkrecht oder waagerecht |
| **Kachel-Raster (panel)** | Kacheln neben- und untereinander, z. B. für Sender oder Kategorien |
| **Endlos-Karussell (wraplist)** | Beginnt nach dem letzten Eintrag wieder von vorn – wie bei Streaming-Diensten |
| **Fester Fokus (fixedlist)** | Der Fokus bleibt an einer Stelle, die Einträge wandern |

### Maße

- **Richtung:** Senkrecht (untereinander) oder waagerecht (nebeneinander).
- **Eintrag-Höhe**, **Eintrag-Breite** (bei Kacheln und waagerechten Listen), **Abstand** zwischen den Einträgen.
- Die Rundung unter „Form & Stil“ gilt für **jeden Eintrag**.
- **Farbe der Einträge** und **Textfarbe** wie bei Buttons. Der ausgewählte Eintrag bekommt die Fokusfarbe.

### Inhalt: Eigene Einträge

Jeder Eintrag hat:

- **Titel**
- **Zusatz rechts** (optional, z. B. „Bibliothek“)
- **Bild** – Adresse oder **🖼 vom Gerät**
- **eine eigene Aktion** (alle Aktionen aus Schritt 6, mit **📚** auch aus der Befehlsliste)

Mit **↑ / ↓** sortierst du Einträge, **✖** löscht, **＋ Eintrag hinzufügen** legt neue an.

### Inhalt: Automatisch aus Kodi (Widget)

Die Liste füllt sich beim Öffnen **selbst** – wie ein Widget im Kodi-Startbildschirm. Ein Klick spielt den Eintrag ab oder öffnet den Ordner.

| Vorschlag | Pfad |
|---|---|
| 🆕 Neue Filme | `videodb://recentlyaddedmovies/` |
| 🆕 Neue Folgen | `videodb://recentlyaddedepisodes/` |
| 🎬 Alle Filme | `videodb://movies/titles/` |
| 📺 Alle Serien | `videodb://tvshows/titles/` |
| ▶ Serien weiterschauen | `videodb://inprogresstvshows/` |
| 💿 Neue Alben | `musicdb://recentlyaddedalbums/` (Art: Musik) |
| 🎵 Zuletzt gehört | `musicdb://recentlyplayedalbums/` (Art: Musik) |
| 📃 Video-Playlists | `special://profile/playlists/video/` |
| 🧩 Addon | z. B. `plugin://plugin.video.youtube/` |

- **Art der Medien:** Video, Musik, Bilder oder Dateien – muss zur Quelle passen.
- **Max. Einträge:** Wie viele Einträge höchstens geladen werden (Standard 30).

> ⚠️ In der Vorschau siehst du Platzhalter („Eintrag 1 aus Kodi“). Die echten Inhalte erscheinen erst in Kodi. Widgets aus anderen Addons können einen Moment zum Laden brauchen.

---

## 17. Ein/Aus-Schalter

Ein echter Schalter, den man mit OK umschaltet. **Kodi merkt sich den Zustand – auch nach einem Neustart.**

### Was schaltet der Schalter?

| Modus | Wirkung |
|---|---|
| **Eigener Merker** | Ein eigener An/Aus-Wert, den du für Sichtbarkeits-Bedingungen und Befehle nutzt. Der Name wird automatisch vergeben (z. B. `meinkodiprojekt.kindermodus`) und lässt sich ändern. |
| **Option dieses Addons** | Schaltet eine An/Aus-Option aus deinen Addon-Einstellungen. Mit **＋ Neue An/Aus-Option dafür anlegen** entsteht sie mit einem Klick. |
| **Kodi-Systemeinstellung** | Schaltet eine echte Kodi-Einstellung (nur An/Aus-Einstellungen). Vorschläge: Webserver, UPnP/DLNA, Zeroconf, AirPlay, Event-Server, Debug-Infos, RSS-Laufschrift, versteckte Dateien, „..“-Einträge, stille Bibliotheks-Updates. |

### Weitere Einstellungen

- **Kodi-Befehl beim Einschalten / Ausschalten** (optional), z. B. `Notification(Info,An,2000)`.
- **Vorschau: eingeschaltet zeigen** – nur für die Optik im Generator.
- **🔐 Schutz** – PIN oder Sicherheitsfrage vor dem Umschalten. Bei falschem PIN springt der Schalter zurück.
- Die Farbe für „AN“ stellst du in der Modding-Werkstatt ein (Standard: Grün).

### Merker als Bedingung nutzen

Bei „Eigener Merker“ zeigt der Generator dir die fertige Bedingung, z. B.:

```
String.IsEqual(Window(Home).Property(meinkodiprojekt.kindermodus),1)
```

Diese Bedingung trägst du bei anderen Elementen unter **👁 Wann sichtbar?** ein (📋 kopiert sie). Noch einfacher: Im **🧠 Bedingungen**-Baukasten gibt es für jeden Merker die Buttons „🟢 … ist AN“ und „⚪ … ist AUS“. Ein komplettes Beispiel steht in den Rezepten.

---

## 18. Regler (Lautstärke und Spulen)

Ein Schieberegler, den man mit links/rechts bedient.

| Modus | Wirkung |
|---|---|
| **Lautstärke** | Stellt die Kodi-Lautstärke ein |
| **Spulen** | Springt im laufenden Video oder Lied |

- **Farbe der Leiste** wie gewohnt. Der Knopf bekommt bei Fokus die Fokusfarbe.
- Tipp: Den Spul-Regler mit **👁 Nur wenn etwas läuft** kombinieren.
- In der Vorschau springt der Knopf an die angeklickte Stelle.

---

## 19. Textbox, Laufschrift und mehrzeiliger Text

| Variante | So geht's |
|---|---|
| **📝 Textbox** | Für längere Texte mit Zeilenumbrüchen. **Langen Text automatisch scrollen** lässt Kodi den Text langsam durchlaufen. |
| **📰 Laufschrift** | Normaler Text → 🛠 Modding → **Laufschrift, wenn der Text zu lang ist** |
| **Mehrzeiliger Text** | Normaler Text → 🛠 Modding → **Mehrzeilig (Zeilenumbruch erlaubt)** |

Zeilenumbrüche aus dem Textfeld werden für Kodi automatisch in `[CR]` umgewandelt.

---

## 20. Videofenster, Visualisierung, RSS-Ticker

| Element | Wirkung |
|---|---|
| **📺 Videofenster** | Zeigt das laufende Video als Fenster mitten im Menü. Wird automatisch mit „Nur wenn ein Video läuft“ eingefügt. |
| **🌈 Visualisierung** | Zeigt die Musik-Visualisierung von Kodi. Wird mit „Nur wenn Musik läuft“ eingefügt. |
| **📡 RSS-Ticker** | Laufband mit den RSS-Nachrichten aus Kodi. Dafür muss in Kodi unter **Einstellungen → Oberfläche** die RSS-Laufschrift eingeschaltet sein. |

Alle drei können zusätzlich eine Klick-Aktion bekommen – z. B. Videofenster anklicken → Vollbild (`Action(FullScreen)`).

---

## 21. 🛠 Modding pro Element

Ganz unten in den Eigenschaften jedes Elements:

| Einstellung | Wirkung |
|---|---|
| **Kodi-ID** | Die Control-ID in Kodi. Bei anklickbaren Elementen steht die Fokus-Bedingung `Control.HasFocus(ID)` daneben (📋 kopiert sie). |
| **Schrift** | Schriftname aus dem Kodi-Skin, z. B. `font10` (klein) bis `font45` (groß). Leer = Standard-Schrift aus der Werkstatt. Gibt es den Namen im aktiven Skin nicht, nimmt Kodi eine Standardschrift. |
| **Laufschrift / Mehrzeilig** | Nur bei Texten (Abschnitt 19). |
| **✨ Animationen** | Mehrere gleichzeitig möglich (Tabelle unten). |
| **Verzögerung beim Erscheinen** | 0–2000 ms. Damit erscheinen Elemente nacheinander. |
| **Kodi-Befehl, wenn ausgewählt (Fokus)** | Wird ausgeführt, sobald das Element ausgewählt wird (`<onfocus>`). |
| **Kodi-Befehl, wenn Fokus weggeht** | `<onunfocus>` |
| **Eigene XML-Zeilen** | Werden 1:1 in das Kodi-Control geschrieben, z. B. `<animation>`, `<enable>`, `<hitrect>`, weitere `<onfocus>`-Zeilen. **✔ Prüfen** testet die XML. |

### Animationen

| Animation | Wann? |
|---|---|
| Einblenden beim Öffnen | Beim Öffnen der Seite |
| Von links / rechts / oben / unten hereinfahren | Beim Öffnen der Seite |
| Heranzoomen (mit Federn) | Beim Öffnen der Seite |
| Ausblenden beim Schließen | Beim Schließen der Seite |
| Pulsieren (dauernd) | Immer – ideal für Hinweise wie „NEU!“ |
| Schweben (dauernd) | Immer – sanftes Auf und Ab |
| Drehen (dauernd) | Immer – z. B. für ein Logo |
| Wachsen, wenn ausgewählt (Fokus) | Nur bei anklickbaren Elementen |

> ⚠️ Animationen sieht man nur in Kodi, nicht in der Vorschau.

---

# Teil C – Die Modding-Werkstatt

## 22. Überblick

Öffnen über **🛠 Modding** in der Kopfzeile oder **🛠 Modding-Werkstatt öffnen** links. Oben wählst du einen der acht Bereiche:

| Bereich | Inhalt |
|---|---|
| **🎛 Schalter** | Ein/Aus-Schalter für Generator, Optik und Verhalten in Kodi |
| **🧩 Bausteine** | 16 fertige Profi-Bausteine mit einem Klick |
| **🧰 Werkzeuge** | Ausrichten, Verteilen, Spiegeln, Skalieren … |
| **📄 Seiten-Tuning** | Dialog-Seiten, Startfokus, Seiten-Befehle, eigenes XML, Direkt-Link |
| **⌨ Tasten** | Tasten der Fernbedienung belegen |
| **🧠 Bedingungen** | Baukasten für Sichtbarkeits-Regeln |
| **🔍 Inspektor & Links** | Alle Kodi-IDs und Direkt-Links |
| **🧬 Projekt-JSON** | Das ganze Projekt als Text bearbeiten |

---

## 23. 🎛 Schalter

### 🖥 Im Generator

| Schalter | Wirkung |
|---|---|
| **🔢 Kodi-IDs auf der Bühne zeigen** | Jedes Element zeigt seine Control-ID (gelbes Schildchen) |
| **➕ Hilfslinien** | Mittellinien und Drittel-Raster |
| **📺 Sicherer Bereich (Overscan)** | Gelber Rahmen: Was außerhalb liegt, schneiden manche Fernseher ab |
| **📐 Rastergröße** | 5, 10, 20, 40 oder 80 px – auch die Schrittweite der Pfeiltasten |

### ✨ Optik in Kodi

| Schalter | Wirkung |
|---|---|
| **🔍 Fokus-Zoom** | Ausgewählte Buttons, Schalter, Regler und anklickbare Elemente wachsen (101–125 %). Listen sind ausgenommen, damit nicht die ganze Liste wächst. |
| **🎞 Nacheinander einblenden** | Anklickbare Elemente gleiten beim Öffnen einer Seite nacheinander von links herein. Elemente mit eigener Öffnen-Animation behalten ihre eigene. |
| **🌑 Textschatten** | Bessere Lesbarkeit auf hellen Bildern |
| **🔤 Standard-Schrift** | Schrift für alle Texte ohne eigene Schrift (Standard `font13`) |
| **🎯 Textfarbe bei Fokus** | Schriftfarbe auf ausgewählten Buttons, Schaltern und Listeneinträgen (Standard Schwarz) |
| **🟢 Farbe „Schalter AN“** | Farbe eingeschalteter Ein/Aus-Schalter |

### 🧭 Verhalten in Kodi

| Schalter | Wirkung |
|---|---|
| **🏠 Beenden führt zur Kodi-Startseite** | Wer das Addon verlässt, landet auf der Kodi-Startseite – nicht in Kodis Video-Ansicht („Videos“ mit Dateien, Wiedergabelisten, Video-Addons). Beim Start aus den Video-Addons wird diese Ansicht ebenfalls übersprungen. Standard: an. |
| **↩ Nach Kodi-Fenstern zurück ins Menü** | Öffnet ein Button ein Kodi-Fenster oder ein Video, kommt man mit Zurück bzw. nach dem Video wieder in dein Menü – statt in Kodis Ansicht hängenzubleiben. Standard: an. |
| **❓ Beim Verlassen nachfragen** | „Zurück“ auf der Startseite fragt erst „Addon wirklich verlassen?“ |
| **🧠 Letzte Seite merken** | Das Addon öffnet sich wieder auf der zuletzt besuchten Seite |
| **🔗 Direkt-Links erlauben** | Seiten lassen sich direkt öffnen (Abschnitt 35). Standard: an. |
| **🚀 Autostart-Option einbauen** | Erzeugt `service.py` und die Option „Beim Kodi-Start automatisch öffnen“ in den Addon-Einstellungen. Einstellbar: Wartezeit nach dem Start (Sekunden) und ob die Option nach der Installation schon an ist. |
| **🎵 Hintergrundmusik** | Spielt beim Öffnen Musik oder einen Radio-Stream. Eine Internet-Adresse eintragen oder eine eigene Datei (vorher unter „📁 Ordner & Dateien“ hochladen, z. B. `resources/musik.mp3`). Optionen: **Nur starten, wenn gerade nichts läuft** und **Beim Verlassen des Addons stoppen**. |

### 🐍 Für Profis

| Schalter | Wirkung |
|---|---|
| **🐍 Python-Hooks (custom.py)** | Erzeugt `resources/lib/custom.py` mit Beispielen und erlaubt die Aktion „Python-Funktion“ (Abschnitt 34). **💻 custom.py im Editor öffnen** bringt dich direkt hin. |
| **🐞 Ausführliches Kodi-Log** | Schreibt jeden Seitenwechsel und jeden Schalter ins Kodi-Log, auch ohne Debug-Modus |

---

## 24. 🧩 Bausteine

Ein Klick fügt den Baustein auf der aktuellen Seite ein:

| Baustein | Inhalt |
|---|---|
| 📋 Liste | Senkrechte Liste mit eigenen Einträgen |
| 🔲 Kachel-Raster | 8 Kacheln im Raster |
| 🎠 Karussell | Waagerechte Endlos-Reihe |
| 🆕 Widget „Neue Filme“ | Reihe, die sich aus deiner Bibliothek füllt |
| 🧩 Widget aus Addon | Inhalt eines anderen Addons als Liste (Pfad anpassen) |
| 🔘 Ein/Aus-Schalter | Mit eigenem Merker |
| 🔊 Lautstärke-Regler | Lautstärke im Menü |
| ⏩ Spul-Regler | Nur sichtbar, wenn etwas läuft |
| 📝 Textbox | Mehrzeiliger, scrollender Text |
| 📰 Laufschrift | Durchlaufender Text |
| 📺 Videofenster | Nur sichtbar, wenn ein Video läuft |
| 🌈 Visualisierung | Nur sichtbar, wenn Musik läuft |
| 📡 RSS-Ticker | Nachrichten-Laufband |
| 🕒 Große Uhr | Uhrzeit mit Sekunden |
| 🌤 Wetter-Zeile | Ort · Wetter · Temperatur |
| 💓 Pulsierender Hinweis | „NEU!“ in Gelb, pulsiert dauerhaft |

---

## 25. 🧰 Werkzeuge

Erst ein Element **markieren** – es dient als Vorlage. Die Werkzeuge wirken auf alle **nicht gesperrten** Elemente **derselben Art** auf der aktuellen Seite.

| Werkzeug | Wirkung |
|---|---|
| **⇤ Links / ↔ Mitte / ⇥ Rechts** | Waagerecht am markierten Element ausrichten |
| **⤒ Oben / ↕ Mitte / ⤓ Unten** | Senkrecht am markierten Element ausrichten |
| **↔ Waagerecht / ↕ Senkrecht verteilen** | Gleiche Abstände (ab 3 Elementen) |
| **Gleiche Größe: Breite / Höhe / Beides** | Maße wie das markierte Element |

Für die **ganze Seite**:

| Werkzeug | Wirkung |
|---|---|
| **🪞 Spiegeln** | Layout links ↔ rechts spiegeln (Textausrichtung wird mit getauscht) |
| **🧲 Alles aufs Raster** | Position und Größe aller Elemente einrasten |
| **🧲 Alles ins Bild holen** | Elemente, die über den Rand ragen, zurückholen |
| **⧉ Seite duplizieren** | Kopie der Seite |
| **🔒 Alles sperren / 🔓 Alles entsperren** | Sperre für alle Elemente |
| **Alles verschieben** | Um X/Y Pixel |
| **Alles skalieren** | Prozentual von der Bildmitte aus (auch Listen-Maße und Rahmen) |

Alles lässt sich mit **↩ Rückgängig** zurücknehmen.

---

## 26. 📄 Seiten-Tuning

Oben wählst du die Seite. Angezeigt werden auch Dateiname und **Seiten-ID**.

| Einstellung | Wirkung |
|---|---|
| **🪟 Als Dialog öffnen** | Die Seite legt sich über das, was gerade in Kodi zu sehen ist – ideal für Pop-up-Menüs. Mit **Abdunkeln** (0–100 %) bestimmst du, wie stark der Hintergrund abgedunkelt wird. Hintergrundbilder werden auf Dialog-Seiten nicht verwendet. |
| **🎯 Startfokus** | Welches Element beim Öffnen ausgewählt ist. Standard: das oberste links. |
| **🔗 Direkt-Link** | Adresse und Favoriten-Befehl für genau diese Seite (Abschnitt 35) |
| **▶ Befehle beim Öffnen** | Ein Kodi-Befehl pro Zeile (`<onload>`) |
| **⏹ Befehle beim Schließen** | Ein Kodi-Befehl pro Zeile (`<onunload>`) |
| **🧬 Eigene Controls (XML)** | Eigene Kodi-Controls, die am Ende der Seite eingefügt werden – Gruppen, Labels, Bilder, Animationen … |

Beispiel für eigene Controls:

```xml
<control type="label">
  <left>40</left><top>1000</top><width>800</width><height>50</height>
  <label>$INFO[System.Date]</label>
</control>
```

---

## 27. ⌨ Tasten

Lege fest, was eine Taste in deinem Menü macht – auf **allen Seiten**. Jede Taste kann jede Aktion aus Schritt 6 bekommen (auch Seitenwechsel oder Python-Funktion).

| Taste | Aktions-ID |
|---|---|
| Kontextmenü (Taste C) | 117 |
| Info (Taste I) | 11 |
| Pause (Leertaste) | 12 |
| Play (Taste P) | 79 |
| Play/Pause (Fernbedienung) | 229 |
| Stopp (Taste X) | 13 |
| Nächster Titel (Taste .) | 14 |
| Vorheriger Titel (Taste ,) | 15 |
| Bild hoch / Bild runter | 5 / 6 |
| Menü-Taste (Fernbedienung) | 163 |
| Ziffern 0–9 | 58–67 |
| **Eigene Aktions-ID (Profis)** | beliebige Zahl (siehe Kodi-Wiki „Action IDs“) |

- Kodi führt die normale Funktion der Taste eventuell **zusätzlich** aus.
- **Zurück (10 und 92) ist gesperrt**, damit man das Addon immer verlassen kann.
- Doppelt belegte Tasten meldet **✔ Prüfen**.

---

## 28. 🧠 Bedingungen

Hier baust du Sichtbarkeits-Regeln zusammen, ohne die Kodi-Schreibweise auswendig zu kennen.

### Kodi-Schreibweise

| Zeichen | Bedeutung | Beispiel |
|---|---|---|
| `+` | UND | `Player.HasVideo + !Player.Paused` |
| `\|` | ODER | `Player.HasVideo \| Player.HasAudio` |
| `!` | NICHT | `!System.InternetState` |
| `[ ]` | Klammer | `[System.Time(23:00) \| System.Time(00:00,06:00)]` |

### So geht's

1. Element markieren, Werkstatt öffnen → **🧠 Bedingungen** (oder **🧠 Baukasten** in den Eigenschaften).
2. Bausteine anklicken. Sie werden an der Cursorposition eingefügt. **＋ UND**, **| ODER**, **! NICHT** und **[ ] Klammer** verknüpfen sie.
3. **🧪 Prüfen** kontrolliert Klammern und Verknüpfungszeichen.
4. **✅ Für markiertes Element übernehmen** – fertig.

### Fertige Bausteine

| Gruppe | Bausteine |
|---|---|
| **Wiedergabe** | Etwas läuft, Video läuft, Musik läuft, Pausiert, Ton stumm, Internet-Stream |
| **System** | Internet vorhanden, Bildschirmschoner aktiv, 5 Min. keine Eingabe, Addon installiert, Addon aktiv, Live-TV-Addon vorhanden, Ein Dialog ist offen |
| **Zeit** | Morgens 06–12 Uhr, Abends 18–23 Uhr, Nachts 23–06 Uhr, Dezember (Weihnachtszeit) |
| **Gerät** | Android, Windows, Linux, Raspberry Pi, macOS, iOS/tvOS |
| **Bibliothek** | Filme / Serien / Musik vorhanden |
| **Wetter & TV** | Wetter geladen, TV-Aufnahme läuft |
| **Deine Schalter** | Für jeden Merker-Schalter: „🟢 … ist AN“ und „⚪ … ist AUS“ |
| **Fokus auf dieser Seite** | `Control.HasFocus(ID)` für jedes anklickbare Element |

> 💡 Die Fokus-Bedingungen sind ein Profi-Trick: Ein Infotext erscheint nur, während ein bestimmter Button ausgewählt ist.

---

## 29. 🔍 Inspektor & Links

Für jede Seite:

- Dateiname (`home.xml`, `page_1.xml` …), Seiten-ID und der fertige **Favoriten-Befehl** (📋 kopiert ihn)
- Tabelle aller Elemente mit **Kodi-ID**, Art, Name, Aktion und Sichtbarkeits-Bedingung
- **🎯** springt direkt zum Element und markiert es

---

## 30. 🧬 Projekt-JSON

Das komplette Projekt (Projektangaben, Design, Modding-Schalter, Addon-Einstellungen und alle Seiten) als Text – ohne Bilddaten.

- **💾 Übernehmen** – Änderungen anwenden. Bei Fehlern bleibt das alte Projekt erhalten.
- **↺ Neu laden** – aktuellen Stand wieder anzeigen.
- **✨ Formatieren** – sauber einrücken.
- **📋 Kopieren** – in die Zwischenablage.
- Seiten-Hintergrundbilder stehen als `§BILD§` im Text und bleiben erhalten.

> ⚠️ Vorher mit **💾 Speichern** ein Backup anlegen. Mit **↩ Rückgängig** lassen sich nur die Seiten zurücknehmen.

---

# Teil D – Für Profis

## 31. Was im ZIP steckt

```
plugin.video.<id>/
├── addon.xml                      Addon-Beschreibung, Abhängigkeiten, Bilder, ggf. Autostart-Dienst
├── addon.py                       Startet das Menü, verarbeitet alle Aktionen
├── pages.json                     Seiten, Aktionen, Listen, Schalter, Tasten, Optionen
├── service.py                     nur mit Autostart
├── icon.png / fanart.jpg
└── resources/
    ├── settings.xml               nur wenn Addon-Einstellungen oder Autostart
    ├── screenshot-01.jpg …
    ├── lib/custom.py              nur mit Python-Hooks
    └── skins/Default/
        ├── 1080i/home.xml         Startseite
        ├── 1080i/page_1.xml …     weitere Seiten
        └── media/                 Bilder, Rundungen, Masken, Schalter- und Regler-Grafiken
```

Dazu kommen deine eigenen Ordner und Dateien.

- `addon.py` öffnet jede Seite als `WindowXML` (normale Seite) bzw. `WindowXMLDialog` (Dialog-Seite).
- Das Plugin beendet das Verzeichnis-Listing sofort, wechselt mit `ReplaceWindow(home)` zur Kodi-Startseite (damit Kodis Video-Ansicht nicht im Verlauf bleibt) und zeigt danach dein Menü.
- Befehle, die ein anderes Fenster öffnen, führt `addon.py` erst **nach** dem Schließen des Menüs aus. Danach wartet es, bis wieder das Ausgangsfenster aktiv ist und kein Dialog mehr offen ist, und öffnet dann dieselbe Seite erneut.
- Wird das Addon ein zweites Mal gestartet, während es noch wartet, übernimmt der neue Start; der alte beendet sich still (Kennung `Window(Home).Property(kfe.run.<id>)`).

---

## 32. Die Kodi-IDs

| ID | Wofür |
|---|---|
| **99** | Hintergrund der Seite |
| **100 + Position** | Buttons, Listen, Schalter, Regler sowie alle sichtbaren Elemente |
| **1000 + Position** | Unsichtbarer Fokus-Button über anklickbaren Elementen, die selbst kein Button sind (Texte, Bilder, Flächen …) |
| **2000 + Position** | Rahmen (Form & Stil) |
| **4000 + Position** | Bild hinter einem Button mit eigenem Hintergrundbild |

„Position“ ist die Ebenen-Reihenfolge auf der Seite, beginnend bei 0 (das hinterste Element hat Position 0).

> ⚠️ Die IDs **ändern sich**, wenn du Elemente nach vorn/hinten legst, löschst oder neue davor einfügst. Wenn du IDs in Bedingungen (`Control.HasFocus(…)`), `SetFocus(…)` oder eigenem XML nutzt, prüfe sie nach Umbauten im **🔍 Inspektor** oder mit **🔢 Kodi-IDs auf der Bühne zeigen**.

---

## 33. pages.json – die Schaltzentrale

`addon.py` liest alles aus `pages.json`:

| Schlüssel | Inhalt |
|---|---|
| `start` | ID der Startseite |
| `welcome` | Begrüßungstext |
| `pages` | Liste der Seiten mit `id`, `name`, `file`, `dlg` (Dialog) und `focus` (Startfokus-ID) |
| `actions` | Pro Seite: Control-ID → Aktion (`page`, `back`, `home`, `exit`, `cmd`, `py`, `list`), ggf. mit `pin` und `ask` |
| `lists` | Pro Seite: Listen-Einträge (`l`, `l2`, `t` = Bild) oder Widget-Quelle (`dir`, `media`, `max`) |
| `switches` | Pro Seite: Schalter mit Modus `m` (`flag`, `addon`, `kodi`), Schlüssel `k` und Befehlen `on` / `off` |
| `keys` | Aktions-ID → Aktion |
| `close` | Befehle, vor denen das Menü geschlossen wird |
| `noreturn` | Befehle, nach denen das Addon endet statt ins Menü zurückzukehren |
| `opts` | `home_exit`, `return_menu`, `confirm_exit`, `remember`, `deeplinks`, `hooks`, `debug`, `bgm`, `bgm_idle`, `bgm_stop` |

Du kannst `pages.json` im **💻 Editor** direkt anpassen – z. B. weitere Befehle in `close` aufnehmen.

---

## 34. Python-Hooks (custom.py)

Mit **🐍 Python-Hooks** bekommst du die Datei `resources/lib/custom.py`. Darin schreibst du eigene Python-Funktionen und rufst sie über die Aktion **Python-Funktion (custom.py)** auf – bei Buttons, Listen-Einträgen oder Tasten.

### Regeln

- Als Wert trägst du nur den **Funktionsnamen** ein, z. B. `hallo`.
- Jede Funktion bekommt das geöffnete **Menü-Fenster** übergeben: `def meine_funktion(window):`
- Der **Rückgabewert** steuert, was danach passiert:

| Rückgabe | Wirkung |
|---|---|
| nichts / `None` | Menü bleibt offen |
| `'back'` | Eine Seite zurück |
| `'home'` | Zur Startseite |
| `'exit'` | Addon schließen |
| `'page:ID'` | Zur Seite mit dieser ID (siehe Inspektor) |
| jeder andere Text | Wird als Kodi-Befehl ausgeführt, z. B. `'PlayMedia("…")'` |

### Automatische Hooks (optional)

| Funktion | Wann? |
|---|---|
| `on_start()` | Beim Start des Addons |
| `on_page(window, page_id)` | Bei jeder geöffneten Seite |
| `on_exit()` | Beim Schließen des Addons |

### Mitgelieferte Beispiele

| Funktion | Was sie tut |
|---|---|
| `hallo` | Zeigt einen Dialog „Dein erster Python-Hook funktioniert!“ |
| `zufallsfilm` | Spielt einen zufälligen Film aus der Bibliothek ab |
| `nachfragen` | Ja/Nein-Frage, danach zur Startseite |
| `on_page` | Schreibt jede geöffnete Seite ins Log |

### Eigenes Beispiel

```python
def lauter_und_info(window):
    """Lautstärke auf 80 % und eine Meldung zeigen."""
    xbmc.executebuiltin('SetVolume(80)')
    return 'Notification(Info,Lautstärke 80 %,2000)'
```

- Bearbeiten im **💻 Editor** → `resources/lib/custom.py`, oder eine eigene `custom.py` unter „📁 Ordner & Dateien“ nach `resources/lib/` hochladen (die eigene Datei hat dann Vorrang).
- Fehler in `custom.py` landen mit vollständiger Fehlermeldung im Kodi-Log; in Kodi erscheint „Fehler in custom.… (siehe Log)“.

---

## 35. Direkt-Links und Favoriten

Mit **🔗 Direkt-Links erlauben** lässt sich jede Seite direkt öffnen:

```
plugin://plugin.video.<id>/?page=<Seiten-ID>
```

Statt der Seiten-ID funktioniert auch der **Seitenname** (Groß-/Kleinschreibung egal).

### Als Kodi-Favorit

In der Datei `userdata/favourites.xml`:

```xml
<favourite name="Meine Optionen">RunPlugin(plugin://plugin.video.meinkodiprojekt/?page=opt)</favourite>
```

Die fertigen Befehle stehen im **📄 Seiten-Tuning** und im **🔍 Inspektor** (📋 zum Kopieren).

> 💡 `RunPlugin(…)` öffnet das Menü direkt über dem aktuellen Bildschirm. `ActivateWindow(videos,plugin://…,return)` geht dagegen erst in die Video-Ansicht.

---

## 36. Merker, Zustände und Speicherorte

| Was | Wo |
|---|---|
| Zustand der **Merker-Schalter** und die **zuletzt besuchte Seite** | `special://profile/addon_data/plugin.video.<id>/state.json` |
| **Merker als Kodi-Eigenschaft** | `Window(Home).Property(<name>)` = `1`, solange der Schalter an ist. Wird beim Start des Addons aus `state.json` wiederhergestellt. |
| **Addon-Optionen** | Die normale `settings.xml` im `addon_data`-Ordner |
| **Kodi-Systemeinstellungen** | Direkt in Kodi (über JSON-RPC `Settings.SetSettingValue`) |

> 💡 Merker-Eigenschaften gelten in ganz Kodi. Ein Skin oder ein anderes Addon kann sie ebenfalls abfragen.

---

# Teil E – Rezepte

## 37. Rezepte

### Rezept 1: Kindersicherung mit Schalter

1. Seite „Optionen“ anlegen, **🔘 Schalter** einfügen, Beschriftung „Kindermodus“.
2. Modus **Eigener Merker** lassen. Optional: **🔐 PIN** eintragen, damit nur Eltern umschalten können.
3. Auf der Startseite den Button „Filme ab 18“ markieren → **🧠 Baukasten** → **⚪ Kindermodus ist AUS** → **✅ Übernehmen**.
4. Ergebnis: Ist der Kindermodus an, verschwindet der Button.

> Fertig zum Ansehen in der Vorlage **🛠 Profi-Menü** (Seite „Optionen“).

### Rezept 2: Streaming-Startseite mit Widgets

1. **🧩 Bausteine** → **🆕 Widget „Neue Filme“**.
2. Noch einmal einfügen, unter **Inhalt** die Quelle **🆕 Neue Folgen** wählen.
3. Beide Reihen untereinander schieben, Überschriften als Text darüber.
4. Optional: **🎞 Nacheinander einblenden** und **🔍 Fokus-Zoom** einschalten.

### Rezept 3: Pop-up-Menü als Dialog

1. Neue Seite „Schnellmenü“ mit 3–4 Buttons (z. B. Lautstärke, Untertitel, Stopp).
2. **📄 Seiten-Tuning** → **🪟 Als Dialog öffnen**, Abdunkeln auf 50 %.
3. **⌨ Tasten** → **Kontextmenü (117)** → **Andere Seite öffnen** → „Schnellmenü“.
4. Ergebnis: Taste C bzw. die Kontextmenü-Taste der Fernbedienung öffnet auf jeder Seite deines Menüs das Pop-up.

### Rezept 4: Favorit direkt auf eine Unterseite

1. **🔗 Direkt-Links erlauben** muss an sein.
2. **🔍 Inspektor** → bei der Seite den `RunPlugin(…)`-Befehl kopieren.
3. In Kodi als Favorit eintragen (Abschnitt 35) oder in einem Skin-Menüpunkt verwenden.

### Rezept 5: Zufallsfilm-Button

1. **🐍 Python-Hooks** einschalten.
2. Button „🎲 Überrasch mich“ anlegen, Aktion **Python-Funktion**, Wert `zufallsfilm`.
3. Exportieren – der Button spielt einen zufälligen Film aus deiner Bibliothek.

### Rezept 6: Radio im Hintergrund

1. **🎵 Hintergrundmusik** einschalten, Stream-Adresse eintragen.
2. **Nur starten, wenn gerade nichts läuft** und **Beim Verlassen stoppen** anlassen.
3. Optional: **🎚 Lautstärke-Regler** ins Menü setzen.

### Rezept 7: Begrüßung je nach Tageszeit

1. Drei Texte übereinander legen: „Guten Morgen“, „Schönen Abend“, „Gute Nacht“.
2. Jedem im **🧠 Baukasten** die passende Zeit geben: Morgens 06–12, Abends 18–23, Nachts 23–06.
3. In Kodi ist immer nur der passende Gruß sichtbar.

### Rezept 8: Infotext zum ausgewählten Button

1. Unter den Buttons einen Text „Hier findest du alle Filme“ anlegen.
2. **🧠 Baukasten** → **Fokus auf dieser Seite** → den Filme-Button wählen → **✅ Übernehmen**.
3. Für jeden Button einen eigenen Infotext an derselben Stelle – es ist immer nur der passende sichtbar.

### Rezept 9: Autostart für ein Kiosk-Menü

1. **🚀 Autostart-Option einbauen**, **Nach Installation schon an** aktivieren.
2. Optional **❓ Beim Verlassen nachfragen** einschalten.
3. Nach der Installation öffnet sich dein Menü bei jedem Kodi-Start. Abschalten in den Addon-Einstellungen.

---

# Teil F – Hilfe

## 38. Vorschau und Kodi – die Unterschiede

| In der Vorschau | In Kodi |
|---|---|
| Emojis werden angezeigt | Die meisten Kodi-Schriften zeigen keine Emojis |
| Schriftgröße passt sich der Elementhöhe an | Es gilt die gewählte Kodi-Schrift (z. B. `font13`) |
| Alle Elemente sind immer sichtbar | Bedingungen blenden Elemente ein und aus |
| Keine Animationen | Alle Animationen laufen |
| Widgets zeigen Platzhalter | Echte Inhalte aus der Bibliothek bzw. dem Addon |
| Videofenster, Cover, Fortschritt, Visualisierung als Platzhalter | Echte Wiedergabe-Inhalte |
| Live-Infos mit Beispielwerten | Echte Werte von Kodi |
| Befehle werden nur angezeigt | Befehle werden ausgeführt |

---

## 39. Fehlerbehebung und häufige Fragen

**Das Addon zeigt nach einem Update noch das alte Menü.**
Version erhöhen (**＋**), neu exportieren und installieren. Hilft das nicht: altes Addon deinstallieren und neu installieren.

**Nach dem Beenden lande ich in Kodis Video-Ansicht („Videos“ mit Dateien, Wiedergabelisten, Video-Addons).**
Im 🛠 Modding unter Schalter **🏠 Beenden führt zur Kodi-Startseite** einschalten (Standard: an), neu exportieren und installieren. Projekte aus älteren Versionen bekommen den Schalter beim Laden automatisch eingeschaltet.

**Nach einem Kodi-Fenster (z. B. Filme) komme ich nicht mehr ins Menü zurück.**
**↩ Nach Kodi-Fenstern zurück ins Menü** muss an sein. Zurück geht es, sobald du wieder auf dem Fenster bist, von dem aus das Menü geöffnet wurde (normalerweise die Kodi-Startseite). Navigierst du im Kodi-Fenster woandershin, öffnet sich das Menü erst, wenn du dorthin zurückkehrst.

**„Filme“ zeigt eine leere Liste („0 / 0“).**
Deine Kodi-Bibliothek enthält noch keine Filme. Die Bibliotheks-Befehle zeigen nur, was Kodi gescannt hat. Mit Zurück kommst du wieder in dein Menü.

**„Aus ZIP-Datei installieren“ geht nicht.**
**Einstellungen → System → Addons → Unbekannte Quellen** einschalten.

**Der Generator sieht ohne Internet „kaputt“ aus.**
Das Design (Tailwind CSS) wird beim Öffnen aus dem Internet geladen. Mit Verbindung neu laden. Dein Projekt bleibt gespeichert.

**„Browser-Speicher voll“.**
Viele große Bilder füllen den Browser-Speicher. Mit **💾 Speichern** sichern. Tipp: kleinere Bilder verwenden.

**Die Schrift ist in Kodi zu klein oder zu groß.**
Im 🛠 Modding des Elements eine andere **Schrift** wählen (z. B. `font27`, `font37`) oder die **Standard-Schrift** in der Werkstatt ändern.

**Meine Emojis fehlen in Kodi.**
Normal – Kodi-Schriften haben meist keine Emojis. Nutze stattdessen eigene Bilder als Button-Hintergrund.

**Eine Widget-Liste bleibt leer.**
Stimmt der Pfad? Hat deine Bibliothek Inhalte? Passt die **Art der Medien** (Musik-Pfade brauchen „Musik“)? Bei Addon-Pfaden muss das Addon installiert sein.

**Ein Kodi-Schalter ändert nichts.**
Die Einstellungs-ID muss exakt stimmen und eine An/Aus-Einstellung sein. Im Log steht bei Fehlern „JSON-RPC Settings.SetSettingValue …“.

**Meine Python-Funktion tut nichts.**
**🐍 Python-Hooks** an? Funktionsname richtig geschrieben? Fehler stehen im Kodi-Log (`kodi.log`) mit vollständiger Fehlermeldung.

**Eine Taste macht zusätzlich noch etwas anderes.**
Kodi führt die normale Tastenfunktion eventuell zusätzlich aus. Wähle eine andere Taste oder eine eigene Aktions-ID.

**Bedingung mit `Control.HasFocus(…)` stimmt nicht mehr.**
Die IDs haben sich durch Umbauten geändert (Abschnitt 32). Im 🔍 Inspektor nachsehen und anpassen.

**Meine Änderung im Designer kommt nicht in der ZIP an.**
Die Datei wurde im 💻 Editor von Hand geändert (✎). Im Editor **↺ Original wiederherstellen**.

**Das Menü öffnet sich nicht, Kodi meldet „Menü konnte nicht geladen werden“.**
Meist ein Fehler in eigenem XML (Element-XML, Seiten-XML oder von Hand geänderte Datei). **✔ Prüfen** testet das Element- und Seiten-XML; im Editor werden XML-Dateien beim Übernehmen geprüft. Details stehen im Kodi-Log.

**Wie finde ich das Kodi-Log?**
Der Ort hängt vom Gerät ab – Windows: `%APPDATA%\Kodi\kodi.log`, Linux: `~/.kodi/temp/kodi.log`, Android: `Android/data/org.xbmc.kodi/files/.kodi/temp/kodi.log`. Mit **🐞 Ausführliches Kodi-Log** schreibt dein Addon mehr hinein.

---

## 40. Tastenkürzel

| Taste | Aktion |
|---|---|
| **Pfeiltasten** | Markiertes Element um eine Rasterweite verschieben (Standard 20 px) |
| **Umschalt + Pfeiltasten** | Um 100 px verschieben |
| **Entf / Rücktaste** | Markiertes Element löschen |
| **Strg + C** | Element kopieren |
| **Strg + V** | Element einfügen (auch auf anderen Seiten) |
| **Strg + D** | Element duplizieren |
| **Strg + Z** | Rückgängig |
| **Strg + Y** oder **Strg + Umschalt + Z** | Wiederholen |
| **Strg + S** | Projekt speichern – im Editor: Datei übernehmen |
| **Tab** (im Editor) | Einrücken |

Auf dem Mac gilt **Cmd** statt **Strg**.


# Copyright (c) 2026 Team IT('s) Possible. All rights reserved.
# Version 2026.10.23
# RECHTLICHER HINWEIS:
# Jegliche Haftung und Garantie für Schäden jeglicher Art ist ausgeschlossen. 
# Dieser Code ist das geistige Eigentum der Autoren.
# Das Modifizieren, Verändern, Umschreiben oder die unautorisierte 
# Weiterverbreitung des Codes ist strengstens untersagt.
