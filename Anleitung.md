# 📖 Handbuch – Kodi Video-Addon Generator v9.0 Pro by IT('s) Possible

Mit dem Generator baust du ein **echtes Kodi-Video-Addon mit einem selbst gestalteten Vollbild-Menü** – ganz ohne Programmierkenntnisse. Du ziehst Buttons, Bilder und Widgets auf eine Bühne, legst fest, was beim Klick passiert, und bekommst am Ende eine ZIP-Datei, die du in Kodi installierst. Wer mehr will, findet in der 🛠 Modding-Werkstatt Kontrolle bis ins letzte Detail – mit dem **⚡ Titan-Modus** baust du sogar einen echten Kodi-Skin für ganz Kodi (Teil G) – und mit **📦 Fremd-Addon** packst du ein vorhandenes Addon (ZIP) in dein Menü und zeigst es im eigenen Skin, mit eigenem Kontextmenü und Favoriten (Teil H).

> 💚 Das Werkzeug ist **gratis für die Kodi-Community** – für Anfänger und Profis. Es ist kostenlos, aber nicht Open Source: Verkauf, Weiterverkauf und Weiterverbreitung sind verboten (siehe [LICENSE](LICENSE)). **Die Addons, die du damit baust, gehören dir.**

**Online starten:** [chrisophy.github.io/KSG](https://chrisophy.github.io/KSG/)
**Verschiedene Demos:** [Beispiele](https://github.com/Chrisophy/KSG/tree/main/Demos)
---

## Inhalt

**Teil A – Grundlagen**

1. [Was du baust](#k1)
2. [Vorbereitung](#k2)
3. [Die Oberfläche im Überblick](#k3)
4. [Projekt anlegen](#k4)
5. [Mit einer Vorlage starten – und das Beispiel „Mein Kino-Hub“](#k5)
6. [Elemente hinzufügen](#k6)
7. [Auf der Bühne arbeiten](#k7)
8. [Die Live-Ansicht 👁](#k8)
9. [Eigenschaften einstellen](#k9)
10. [Aktionen beim Klick](#k10)
11. [Seiten anlegen und verlinken](#k11)
12. [Design](#k12)
13. [Werkzeuge](#k13)
14. [Addon-Bilder, Dateien und Einstellungen](#k14)
15. [Testen, Prüfen, Editor und Export](#k15)
16. [Installation in Kodi](#k16)

**Teil B – Bausteine**

17. [Widgets 🧩](#k17)
18. [Info-Widgets und Gruppen](#k18)
19. [Listen, Kachel-Raster und Karussell](#k19)
20. [Ein/Aus-Schalter](#k20)
21. [Regler](#k21)
22. [Textbox und Laufschrift](#k22)
23. [Videofenster, Visualisierung, RSS-Ticker](#k23)
24. [Modding pro Element](#k24)

**Teil C – Die Modding-Werkstatt**

25. [Überblick](#k25)
26. [Schalter](#k26)
27. [Bausteine](#k27)
28. [Werkzeuge](#k28)
29. [Seiten-Tuning](#k29)
30. [Tasten](#k30)
31. [Bedingungen](#k31)
32. [Inspektor und Links](#k32)
33. [Projekt-JSON](#k33)

**Teil D – Für Profis**

34. [Inhalt des ZIP](#k34)
35. [Kodi-IDs](#k35)
36. [pages.json](#k36)
37. [Python-Hooks (custom.py)](#k37)
38. [Direkt-Links und Favoriten](#k38)
39. [Merker, Zustände und Speicherorte](#k39)
40. [So füllen sich Widgets und Listen](#k40)

**Teil E – Rezepte**

41. [Zwölf Rezepte Schritt für Schritt](#k41)

**Teil F – Hilfe**

42. [Unterschiede zwischen Vorschau und Kodi](#k42)
43. [Fehlerbehebung und häufige Fragen](#k43)
44. [Tastenkürzel](#k44)

**Teil G – Titan-Modus: dein eigener Kodi-Skin**

45. [Was ist der Titan-Modus?](#k45)
46. [Grundlage laden](#k46)
47. [Farben, Hintergrund, Logo und Schrift](#k47)
48. [Hauptmenü und eigene Menüpunkte](#k48)
49. [Widgets im Skin](#k49)
50. [Layout: alles frei verschieben](#k50)
51. [Fenster (Video-OSD & Co.) und Profi-Reiter](#k51)
52. [Export und Installation](#k52)
    - 52a. [Andere Skins bearbeiten (Skin-Modus)](#k52a)

**Teil H – Fremd-Addon, Live-Browser und Kontextmenü**

53. [Ein vorhandenes Addon einbinden](#k53)
54. [Menüeinträge und Stile](#k54)
55. [Der Live-Browser 📂](#k55)
56. [Abhängigkeiten automatisch eintragen](#k56)
57. [Kontextmenü und Favoriten 🖱](#k57)
58. [Eigene Einträge in custom.py](#k58)

**Teil I – Lizenz**

59. [Lizenz und wie es weitergeht](#k59)

---

# Teil A – Grundlagen

<a id="k1"></a>

## 1. Was du baust

Der Generator erzeugt ein ganz normales **Kodi-Video-Addon** (`plugin.video.…`). Das Besondere: Beim Öffnen zeigt es nicht Kodis übliche Ordner-Ansicht, sondern **dein eigenes, gestaltetes Menü im Vollbild** – die Startseite heißt intern `home.xml`.

- Es ist **kein System-Skin**. Dein Kodi sieht danach genauso aus wie vorher – nur dein Addon hat ein eigenes Gesicht.
- Dein Menü kann **mehrere Seiten** haben, Filme abspielen, Kodi-Fenster öffnen, andere Addons starten, Schalter umlegen, Widgets mit deinen Filmen zeigen und vieles mehr.
- Wer das Addon verlässt, landet auf der **Kodi-Startseite**. Öffnet ein Button ein Kodi-Fenster oder ein Video, kommt man danach **zurück in dein Menü**.
- Du kannst ein **vorhandenes Addon** (ZIP) einbinden und in deinem Menü zeigen – mit eigenem Browser, **Kontextmenü und Favoriten** (siehe Teil H).

<a id="k2"></a>

## 2. Vorbereitung

| Du brauchst | Hinweis |
|---|---|
| Einen aktuellen Browser | Chrome, Edge, Firefox oder Safari – auf PC, Tablet oder Handy. |
| Internet beim Öffnen | Die Seite lädt ihr Design-Framework (Tailwind CSS) aus dem Netz. Deine Daten bleiben trotzdem im Browser. |
| Kodi 19, 20 oder 21 | Matrix, Nexus oder Omega. |
| Optional: Bibliothek in Kodi | Für Widgets wie „Neue Filme“ müssen deine Filme, Serien oder Musik in der Kodi-Bibliothek sein. |
| Optional: ZIP eines vorhandenen Addons | Für das Einbinden eines Fremd-Addons (siehe [Kapitel 53](#k53)). |

💡 **Dein Projekt wird automatisch im Browser gespeichert.** Für ein sicheres Backup nutze zusätzlich **💾 Speichern** (siehe [Kapitel 14](#k14)).

<a id="k3"></a>

## 3. Die Oberfläche im Überblick

### Am PC (breiter Bildschirm)

| Bereich | Inhalt |
|---|---|
| **Kopfzeile oben** | 🗑 Neu · ❓ So geht's · 📂 Vorlagen · 🧩 Widgets · 📦 Fremd-Addon · ⚡ Titan · ↩ Rückgängig · ↪ Wiederholen · ▶ Testen · ✔ Prüfen · 💻 Editor · 🛠 Modding · ⬇ ZIP exportieren · 🚪 Beenden |
| **Links** | Live-Ansicht-Schalter und die Bereiche 1 · Projekt, 2 · Hinzufügen, 3 · Design, 4 · Werkzeuge, 5 · Addon-Bilder & Dateien (dort auch 🧩 Fremd-Addon einbinden), 6 · Modding für Profis, 7 · ⚡ Titan-Modus, Projekt sichern |
| **Mitte** | Seiten-Leiste und die **Bühne** (1920×1080, so groß wie ein Full-HD-Fernseher) |
| **Rechts** | **Eigenschaften** des markierten Elements |

### Auf Handy und Tablet

- Die **Kopfzeile** ist eine Reihe, die du mit dem Finger **seitlich wischst**, um alle Knöpfe zu erreichen.
- Darunter wechselst du zwischen zwei Reitern: **📱 Vorschau & Seiten** (Bühne, Seiten, darunter die Eigenschaften) und **⚙️ Einstellungen & Werkzeuge** (alles, was am PC links steht).
- Wenn die große Vorschau nicht zu sehen ist, zeigt dir die **👁 Live-Ansicht** dein Menü trotzdem live (siehe [Kapitel 8](#k8)).

### Den Generator verlassen

Nutze **🚪 Beenden**. Bei „Zurück“ im Browser oder beim Schließen des Tabs fragt der Generator vorher nach, damit nichts verloren geht.

<a id="k4"></a>

## 4. Projekt anlegen

Im Bereich **1 · Projekt**:

| Feld | Bedeutung |
|---|---|
| **Wie soll es heißen?** | Name des Addons in Kodi. Daraus entsteht automatisch die **technische ID**, z.B. `plugin.video.meinkinohub`. |
| **Autor** | Steht in Kodi als Anbieter. |
| **Version** | Mit **＋** zählst du die letzte Stelle hoch (1.0.0 → 1.0.1). Erhöhe die Version bei jedem Update, damit Kodi die neue Fassung übernimmt. |
| **Kurzbeschreibung** | Text in Kodis Addon-Info. |
| **Lizenz** | Vorschlag: `GPL-2.0-or-later` – frei änderbar. |
| **Kodi-Version** | Matrix 19, Nexus 20 oder Omega 21. Bestimmt die benötigte Python-Version in der `addon.xml`. |

Unter **⚙ Erweiterte Addon-Angaben** findest du außerdem:

- **Webseite** und **Neu in dieser Version** (erscheinen in Kodi),
- **Begrüßung beim Start** – eine kurze Meldung, die beim Öffnen des Addons erscheint,
- **Zusätzliche Abhängigkeiten** – andere Addons, die Kodi mitinstallieren soll. Schnellknöpfe für `requests`, `beautifulsoup4`, `inputstreamhelper` und `routing` (nochmal klicken entfernt sie wieder). Module, die dein Python-Code oder ein eingebundenes Fremd-Addon braucht, trägt der Generator **selbst** ein (siehe [Kapitel 56](#k56)).

<a id="k5"></a>

## 5. Mit einer Vorlage starten – und das Beispiel „Mein Kino-Hub“

Über **📂 Vorlagen** startest du mit einem fertigen Gerüst. Seiten und Elemente werden dabei ersetzt; Bilder, Dateien, Addon-Einstellungen und Modding-Schalter bleiben erhalten. Von Hand geänderte Dateien aus dem 💻 Editor werden zurückgesetzt.

| Vorlage | Inhalt |
|---|---|
| ✨ **Beispiel zum Lernen: „Mein Kino-Hub“** | 5 fertige Seiten – ideal für Anfänger (siehe unten). |
| 🎬 Streaming-Hub | Startseite, Filme, Live TV |
| 📺 Live TV | Senderliste mit Abspiel-Buttons |
| 🎵 Musik-Player | Cover, Play, Weiter, Stopp, Fortschritt |
| 🛠 Profi-Menü | Liste, Bibliotheks-Listen, Schalter, Regler, Videofenster |
| 📄 Leer | Nur ein Button |

### Das Beispiel „Mein Kino-Hub“

Das Beispiel zeigt fast alles, was der Generator kann – und ist trotzdem leicht zu verstehen. Nach dem Laden erscheint eine kurze Einführung.

| Seite | Was du dort siehst |
|---|---|
| 🏠 **Start** | Großer Titel mit Animation, Begrüßungszeile, **Uhr-Widget** oben rechts, Menü mit sechs Buttons, die nacheinander hereinfahren, und zwei **Widgets**: „Neu in deiner Bibliothek“ (Poster) und „Weiterschauen“ (Breitbild). |
| **Filme** | **Kachel-Raster** mit sechs Bibliotheks-Befehlen (Alle Filme, Genres, Jahre, Sammlungen, Neu dazu, Aktualisieren) und das Widget „Heute vielleicht …“ mit zufälligen Filmen **und Infos** zum gewählten Titel. |
| **Live TV** | Button „Demo-Video abspielen“ (ein frei verfügbares Testvideo), TV-Programm, Senderliste, Aufnahmen, eine Textbox mit Anleitung und ein **Videofenster**. |
| **Musik** | Info-Widget **„Jetzt läuft“** (Cover, Titel, Zeit, Fortschritt, Steuer-Buttons), Party-Modus, Alben, Interpreten und das Widget „Neue Alben“. |
| **Info** | Eine **Dialog-Seite**: ein Fenster, hinter dem Kodi durchscheint, mit „Schließen“-Button. |

Das Beispiel bringt **eigene Farben** (Rot und Gold) und ein **gemaltes Hintergrundbild** mit. Heißt dein Projekt noch „Mein Kodi Projekt“, bekommt es den Namen „Mein Kino-Hub“.

💡 **So lernst du am schnellsten:** Ändere zuerst nur Texte, dann Farben, dann tausche ein Widget aus – und probiere nach jedem Schritt **▶ Testen**.

<a id="k6"></a>

## 6. Elemente hinzufügen

Im Bereich **2 · Hinzufügen**. Ein Klick legt das Element **in die Mitte der Bühne** – von dort ziehst du es an seinen Platz.

| Knopf | Ergebnis |
|---|---|
| 📚 **Befehlsliste** | Fertiger Button mit einem von 92 Kodi-Befehlen (siehe [Kapitel 10](#k10)). |
| 🧩 **Widgets** | Reihen wie im Kodi-Hauptmenü und Info-Widgets (siehe [Kapitel 17](#k17) und [18](#k18)). |
| 🖼 **Eigenes Bild einfügen** | Bilder vom Gerät, auch mehrere auf einmal. Mit oder ohne Funktion. |
| ➕ Button · 🔤 Text · 🖼 Poster-Platzhalter · ⬛ Fläche | Die Grundbausteine. |
| ▬ Fortschrittsbalken · 🎵 Cover | Zeigen in Kodi den Fortschritt bzw. das Bild des gerade laufenden Titels. |

**Schnell-Buttons** haben ihre Aktion schon eingestellt: 🎬 Filme, 📺 Live TV, 🎵 Musik (öffnen eine Seite), ⚙ Einstellungen, 🔧 Addon-Optionen, ⏯ Play/Pause, ⬅ Zurück.

**Live-Infos** sind Texte, die Kodi während der Nutzung selbst ausfüllt: 🕒 Uhrzeit, 📅 Datum, 🌡 Temperatur, 🎵 Läuft gerade, ⏱ Laufzeit, Uhrzeit mit Sekunden, Datum kurz, ☁ Wetter, 📍 Wetter-Ort, 🎤 Interpret, 🎬 Filmtitel, 💾 Freier Speicher, ⚙ CPU-Last, 🌐 IP-Adresse, ℹ Kodi-Version.

Weitere Bausteine (Liste, Schalter, Regler, Textbox, Videofenster, Visualisierung) stehen unter **6 · Modding für Profis** und in der 🛠 Modding-Werkstatt.

<a id="k7"></a>

## 7. Auf der Bühne arbeiten

| So geht's | Was passiert |
|---|---|
| **Antippen / Anklicken** | Markiert das Element (weißer Rahmen). Rechts bzw. unter der Vorschau erscheinen seine Eigenschaften. |
| **Ziehen** | Verschiebt das Element. Mit eingeschaltetem **Raster** rastet es ein (Standard 20 px). |
| **Weiße Ecke unten rechts ziehen** | Ändert die Größe. |
| **Pfeiltasten** | Verschieben um eine Rasterweite – mit Umschalt um 100 px. |
| **◀ ▲ ▼ ▶ unter „Position & Größe“** | Dasselbe per Knopf – ideal auf Handy und Tablet. |
| **X / Y / Breite / Höhe** | Punktgenau eintippen; die Änderung ist sofort sichtbar. |
| **Leere Stelle antippen** | Hebt die Markierung auf. |

- **🔒 Sperren** (unten in den Eigenschaften) schützt ein Element vor versehentlichem Verschieben.
- **⬆ nach vorn / ⬇ nach hinten** ändert, was über was liegt.
- **↔ mittig / ↕ mittig** setzt das Element in die Bildmitte.
- Teile eines **Info-Widgets** bewegen sich immer gemeinsam (siehe [Kapitel 18](#k18)).

<a id="k8"></a>

## 8. Die Live-Ansicht 👁

Die Live-Ansicht ist ein **kleines Fenster mit einem Live-Bild deiner Bühne**. Sie erscheint von selbst, sobald die große Vorschau nicht zu sehen ist – damit du jede Änderung sofort siehst.

### Wann sie erscheint

- Auf Handy und Tablet im Reiter **⚙️ Einstellungen & Werkzeuge** (z.B. beim Ändern von Farben oder Designs).
- Wenn du so weit nach unten scrollst, dass weniger als etwa die Hälfte der großen Vorschau sichtbar ist – z.B. bei den Eigenschaften unter der Bühne.
- In der **🛠 Modding-Werkstatt** und im Fenster **🎨 Hintergrund** einer Seite.

In anderen Fenstern (Editor, Befehlsliste, Vorlagen …) bleibt sie ausgeblendet, weil sie dort nichts zeigen würde.

### Bedienung

| Knopf / Geste | Wirkung |
|---|---|
| **Kopfzeile ziehen** | Fenster verschieben. Die Position wird gemerkt. |
| **⤢** | Größe umschalten: klein, mittel, groß. |
| **↗** | Zur großen Vorschau springen (schließt ein offenes Fenster und wechselt auf dem Handy den Reiter). |
| **✖** | Live-Ansicht ausblenden. Unten links erscheint dann der Knopf **👁 Live-Ansicht**, der sie wieder einschaltet. |
| **Element antippen** | Markiert es – auch in der Live-Ansicht. |
| **Element ziehen** | Verschiebt es direkt im kleinen Bild (Info-Widgets als Ganzes). |

Dauerhaft ein- oder ausschalten kannst du sie mit dem Schalter **👁 Live-Ansicht in Menüs** ganz oben in den Einstellungen oder in der Modding-Werkstatt unter **🎛 Schalter**.

💡 Im **▶ Testmodus** funktioniert auch die Live-Ansicht wie das echte Menü – Klicks lösen die Aktion aus.

<a id="k9"></a>

## 9. Eigenschaften einstellen

Was du einstellen kannst, hängt von der Art des Elements ab. Oben stehen immer 📋 Kopieren, ⧉ Duplizieren und 🗑 Löschen.

| Einstellung | Für | Hinweis |
|---|---|---|
| **Beschriftung / Text** | Button, Text, Poster, Schalter, Textbox | Über **➕ Live-Info einfügen** kommen Uhrzeit, Titel & Co. hinein. |
| **Symbol (Emoji)** | Button | Nur in der Vorschau sichtbar – Kodi-Schriften zeigen meist keine Emojis. |
| **Textausrichtung, Textfarbe** | Button, Text, Textbox, Schalter, Liste, Widget | |
| **Bild** | Bild, Poster | Vom Gerät oder als Adresse (`https://…`, `special://…` oder `$INFO[…]`). Ein Bild vom Gerät hat Vorrang. |
| **Bildanpassung** | Bild, Poster, Button-Bild | Ganzes Bild zeigen · Fläche füllen (Rand wird abgeschnitten) · Strecken |
| **Eigenes Bild als Button-Hintergrund** | Button | Der Button bekommt statt der Farbe ein Bild. |
| **Farbe** | fast alle | **Standard** setzt auf die Design-Farbe zurück. |
| **🔘 Form & Stil** | Button, Bild, Poster, Fläche, Cover, Liste, Schalter, Widget | Eckig, Abgerundet, Pille, Nur Rahmen, Glas – dazu Rundung (0–100 %), Rahmen-Dicke und -Farbe, Deckkraft. |
| **Position & Größe** | alle | Zahlen, ◀ ▲ ▼ ▶, mittig, nach vorn/hinten |
| **👁 Wann sichtbar?** | alle | Immer · nur wenn etwas läuft · nur wenn nichts läuft · nur bei Video · nur bei Musik · nur bei Pause · nur mit/ohne Internet · eigene Bedingung. Den **🧠 Baukasten** erklärt [Kapitel 31](#k31). |
| **🔒 Sperren** | alle | |
| **⚡ Was passiert beim Klick?** | alle außer Liste, Schalter, Regler, Widget | Siehe [Kapitel 10](#k10). |
| **🔐 Schutz** | alles mit Aktion | **PIN-Sperre** (1–8 Ziffern) und/oder **Sicherheitsfrage** mit Ja/Nein. |
| **🛠 Modding (Profis)** | alle | Siehe [Kapitel 24](#k24). |

⚠️ Der PIN ist ein **einfacher Schutz vor Kindern**, kein echtes Passwort – er steht lesbar in der `pages.json`.

<a id="k10"></a>

## 10. Aktionen beim Klick

Jedes Element kann eine Aktion bekommen – auch Texte, Bilder und Flächen. Dann ist es in Kodi mit Maus und Fernbedienung anklickbar und bekommt einen Fokus-Rahmen.

| Aktion | Was passiert in Kodi |
|---|---|
| Nichts (nur Optik) | – |
| Andere Seite öffnen | Wechselt zu einer deiner Seiten. |
| Anderes Addon öffnen | Öffnet z.B. `plugin://plugin.video.youtube/`. |
| Video / Stream abspielen | Spielt eine Adresse (`https://…`) oder Datei ab. |
| Play / Pause · Nächster Titel · Wiedergabe stoppen | Steuert die laufende Wiedergabe. |
| Zurück (vorherige Seite) | Eine Seite zurück. Was auf der Startseite passiert, legst du unter „⬅ Zurück auf der Startseite“ fest (siehe [Kapitel 26](#k26)). |
| Zur Startseite dieses Addons | Springt direkt zur Startseite – egal wie tief man ist. |
| Addon komplett schließen | Beendet das Addon (danach Kodi-Startseite). |
| Kodi-Einstellungen öffnen · Kodi beenden | |
| Einstellungen dieses Addons öffnen | Öffnet deine eigenen Optionen aus [Kapitel 14](#k14). |
| Datei aus diesem Addon abspielen | z.B. `resources/playlist.m3u` (vorher unter 📁 anlegen). |
| Kodi-Befehl | Ein Befehl aus der Befehlsliste oder selbst geschrieben. |
| Ordner im eigenen Browser öffnen (bleibt im Skin) | Zeigt einen Kodi-Pfad wie `plugin://plugin.video.xyz/` in deinem Live-Browser, ohne zu Kodis Ansicht zu wechseln (siehe [Kapitel 55](#k55)). |
| Python-Funktion | Eine Funktion aus `custom.py` (siehe [Kapitel 37](#k37)). |

### Die Befehlsliste 📚

92 fertige Kodi-Befehle in acht Gruppen: **Navigation** (Filme, Serien, Live TV, Favoriten, Suche, Dateimanager …), **Wiedergabe** (Spulen, Untertitel, Tonspur, Vollbild …), **Lautstärke**, **Einstellungen**, **System** (Bibliothek aktualisieren, Bildschirmfoto, Sleep-Timer, Neustart …), **Addons**, **Abspielen** und **Profi** (Eigenschaften setzen, Skin-Schalter, Fokus setzen, Container neu laden …).

- Suche oben nach einem Wort, z.B. „Filme“, „Lautstärke“ oder „Neustart“.
- **Einsetzen** gibt den Befehl dem markierten Element, **＋ Neuer Button** erzeugt einen fertigen Button.
- Befehle mit Platzhaltern wie `DEINE.ADDON.ID` musst du anpassen – ✔ Prüfen erinnert dich daran.

💡 Öffnet ein Befehl ein Kodi-Fenster (z.B. die Film-Bibliothek) oder ein Video, schließt sich dein Menü kurz und **kommt mit Zurück bzw. nach dem Video wieder** (abschaltbar in der Modding-Werkstatt). Befehle wie „Kodi-Startseite“, „Kodi beenden“ oder „Neustart“ beenden das Addon bewusst.

<a id="k11"></a>

## 11. Seiten anlegen und verlinken

Die **Seiten-Leiste** über der Bühne zeigt alle Seiten. Die erste Seite (🏠) ist immer die Startseite (`home.xml`).

| Knopf | Wirkung |
|---|---|
| **＋ Seite** | Neue Seite mit Überschrift und Zurück-Button. |
| **✏ Umbenennen** | |
| **🎨 Hintergrund** | Eigene Farbe oder eigenes Bild nur für diese Seite. **↺ Wie im Design** setzt zurück. |
| **◀ ▶** | Reihenfolge ändern (die Startseite bleibt vorn). |
| **🗑 Seite löschen** | Buttons, die dorthin führten, verlieren ihre Aktion. |

**Verlinken:** Gib einem Button die Aktion **Andere Seite öffnen** und wähle die Zielseite. Für den Rückweg sorgt ein Button mit **Zurück** – oder einfach die Zurück-Taste der Fernbedienung.

🪟 **Dialog-Seiten** legen sich als Fenster über Kodi (siehe [Kapitel 29](#k29)).

<a id="k12"></a>

## 12. Design

Im Bereich **3 · Design**:

- **10 fertige Designs:** Standard, Cyberpunk, Matrix, Sonnenuntergang, Hell, Netflix, Ozean, Wald, Violett, Monochrom.
- **Drei Farben:** Buttons, Fokus (Farbe des ausgewählten Elements) und Hintergrund.
- **🖼 Hintergrundbild** für alle Seiten (✖ entfernt es). Ohne eigene Fanart wird es auch als Fanart genutzt.
- **Übergang beim Seitenwechsel:** Einblenden, Hereinschieben, Heranzoomen oder Keiner.
- **Rundung aller Buttons:** 0 % = eckig, 100 % = Pille. Einzelne Elemente stellst du unter „Form & Stil“ anders ein.
- **Raster / Einrasten** ein- oder ausschalten.

💡 Mit eingeschalteter Live-Ansicht siehst du jede Design-Änderung sofort – auch auf dem Handy im Einstellungs-Reiter.

<a id="k13"></a>

## 13. Werkzeuge

Im Bereich **4 · Werkzeuge**:

| Werkzeug | Wirkung |
|---|---|
| 📐 Buttons mittig untereinander ordnen | Alle Buttons der Seite sauber in einer Spalte. |
| 📏 Alle Buttons so groß wie markierter | Einheitliche Größe. |
| ⧉ Diese Seite duplizieren | Kopie der ganzen Seite. |
| 🔲 Buttons im Raster anordnen … | Fragt nach der Spaltenzahl. |
| 🎨 Stil des markierten Buttons auf alle Buttons | Rundung, Rahmen, Deckkraft, Farben, Schrift, Animationen. |
| 📋 Kopieren / 📌 Einfügen | Auch zwischen Seiten. |
| 💻 Dateien von Hand bearbeiten | Öffnet den Editor (siehe [Kapitel 15](#k15)). |

Noch mehr Werkzeuge (Ausrichten, Verteilen, Spiegeln, Skalieren …) findest du in der Modding-Werkstatt ([Kapitel 28](#k28)).

<a id="k14"></a>

## 14. Addon-Bilder, Dateien und Einstellungen

### Icon, Fanart, Screenshots

| Bild | Format | Ohne eigenes Bild |
|---|---|---|
| **Icon** | quadratisch, wird auf 512×512 gebracht | Ein Icon mit dem Anfangsbuchstaben in deinen Farben |
| **Fanart** | 16:9, wird auf 1920×1080 gebracht | Dein Hintergrundbild oder ein Farbverlauf |
| **Screenshots** | bis zu 8 Stück | keine |

Alle drei kommen automatisch ins Addon **und** in die `addon.xml`.

### 📁 Ordner & Dateien verwalten

- Eigene **Ordner** anlegen (z.B. `resources/lib`) und **Dateien** hochladen (max. 4 MB pro Datei).
- **📝 Textdatei selbst schreiben** – mit Vorlagen für eine M3U-Playlist, eine Python-Hilfsdatei oder ein Änderungsprotokoll.
- Textdateien später mit **✎** bearbeiten.
- Reserviert sind die automatisch erzeugten Dateien (`addon.py`, `addon.xml`, `pages.json`, `resources/skins/…`). Diese änderst du im 💻 Editor.

### ⚙ Einstellungen deines Addons bauen

Lege Optionen an, die man in Kodi unter **Addon → Konfigurieren** ändern kann:

| Art | Startwert |
|---|---|
| Schalter (An/Aus) | „an“ oder „aus“ |
| Text | beliebiger Text |
| Zahl | z.B. 10 |
| Auswahlliste | Werte mit Komma getrennt, z.B. `Klein, Mittel, Groß` |

Daraus entsteht `resources/settings.xml`. Ein Button mit der Aktion **Einstellungen dieses Addons öffnen** öffnet sie, ein **🔘 Ein/Aus-Schalter** kann An/Aus-Optionen direkt im Menü umlegen. Im Code liest du eine Option mit `xbmcaddon.Addon().getSetting('ID')`.

### Projekt sichern

- **💾 Speichern** lädt dein komplettes Projekt als `.json`-Datei herunter – inklusive Bildern.
- **📥 Laden** öffnet so eine Datei wieder.
- Zusätzlich merkt sich der Browser dein Projekt automatisch. Ist sein Speicher voll, erscheint ein Hinweis – dann unbedingt über 💾 sichern.

<a id="k15"></a>

## 15. Testen, Prüfen, Editor und Export

### ▶ Testen

Im Testmodus verhält sich die Bühne wie dein Menü in Kodi: Buttons wechseln Seiten, Zurück funktioniert, Schalter lassen sich umlegen, Regler verstellen. Befehle, die nur Kodi ausführen kann, zeigt eine Meldung an („Kodi würde ausführen: …“). **✏ Bearbeiten** beendet den Testmodus.

### ✔ Prüfen

Findet unter anderem:

- Buttons ohne Aktion, fehlende Video-Adressen, Platzhalter in Befehlen,
- Seiten, die nicht erreichbar sind oder kein anklickbares Element haben,
- Widgets und Listen ohne Quelle,
- fehlende Bilder und Dateien, fehlerhafte eigene XML-Zeilen,
- doppelt belegte Tasten, ungültige PINs, ausgeschaltete Python-Hooks,
- bei Fremd-Addons: eine ZIP fehlt im Speicher dieses Geräts, es gibt noch keine Menüeinträge oder eine Adresse ist keine gültige Kodi-Adresse.

⚠️ **Warnungen** solltest du beheben, 💡 **Hinweise** sind nur Tipps. Beim Export erscheint die Liste automatisch, wenn es Warnungen gibt – du kannst aber trotzdem exportieren.

### 💻 Editor

Zeigt jede erzeugte Textdatei (`addon.py`, `addon.xml`, `home.xml`, `pages.json` …) und lässt dich sie von Hand ändern:

- **💾 Übernehmen** (oder Strg+S) speichert die Änderung – XML und JSON werden dabei auf Fehler geprüft.
- Geänderte Dateien tragen ein **✎**. Sie werden **genau so** exportiert und ändern sich nicht mehr, wenn du im Designer weiterarbeitest.
- **↺ Original wiederherstellen** holt die automatisch erzeugte Fassung zurück.

### ⬇ ZIP exportieren

Erzeugt `plugin.video.<name>.zip` und zeigt danach die Installations-Schritte.

<a id="k16"></a>

## 16. Installation in Kodi

1. ZIP-Datei auf das Kodi-Gerät kopieren (USB-Stick, Netzwerk, Download …).
2. Beim ersten Mal: **Einstellungen → System → Addons → Unbekannte Quellen** erlauben.
3. **Einstellungen → Addons → Aus ZIP-Datei installieren** und die Datei wählen.
4. Dein Addon steht unter **Addons → Video-Addons**. Beim Öffnen erscheint sofort dein Menü.

💡 **Update:** Version erhöhen (＋), neu exportieren und erneut aus der ZIP installieren. Hilft das nicht, das alte Addon vorher deinstallieren.

---

# Teil B – Bausteine

<a id="k17"></a>

## 17. Widgets 🧩

Widgets kennst du vom Kodi-Hauptmenü: **Reihen, die sich von selbst füllen** – mit deinen neuesten Filmen, angefangenen Serien oder Alben. Im Generator fügst du sie über **🧩 Widgets** (Kopfzeile oder Bereich 2 · Hinzufügen) ein.

### Die fertigen Widgets

| Gruppe | Widget | Inhalt | Darstellung |
|---|---|---|---|
| 🎬 Filme | 🆕 Neue Filme | Zuletzt hinzugefügte Filme | Poster |
| | ▶ Filme weiterschauen | Angefangene Filme, zuletzt geschaute zuerst | Breitbild |
| | 👀 Noch nicht gesehen | Ungesehene Filme, neueste zuerst | Poster |
| | 🎲 Zufällige Filme | Bei jedem Öffnen eine neue Mischung | Poster |
| | ⭐ Am besten bewertet | Nach Bewertung sortiert | Poster |
| 📺 Serien | 📺 Neue Folgen | Zuletzt hinzugefügte Folgen | Breitbild |
| | ⏯ Serien weiterschauen | Serien, die du gerade schaust | Poster |
| | 🎲 Zufällige Serien | Neue Mischung bei jedem Öffnen | Poster |
| 🎵 Musik | 💿 Neue Alben | Zuletzt hinzugefügte Alben | Quadratisch |
| | 🎵 Zuletzt gehört | Zuletzt gespielte Alben | Quadratisch |
| | 🎲 Zufällige Alben | Neue Musik-Mischung | Quadratisch |
| 🧰 Sonstiges | 📃 Video-Playlists | Deine gespeicherten Playlists | Liste |
| | 🧩 Inhalt aus einem Addon | Startliste eines anderen Video-Addons | Breitbild |
| | ✏ Eigene Quelle | Jeder Kodi-Pfad | Poster |

⚠️ Bibliotheks-Widgets brauchen Inhalte in der **Kodi-Bibliothek** (Quellen mit Scraper eingerichtet). Ohne Inhalte zeigt das Widget in Kodi „Hier ist noch nichts …“.

### Einstellungen eines Widgets

| Einstellung | Bedeutung |
|---|---|
| **Überschrift** | Steht über der Reihe. Leer = ohne Überschrift. |
| **Was soll das Widget zeigen?** | Eines der fertigen Widgets oder eine eigene Quelle. Die Überschrift passt sich an, solange du sie nicht selbst geändert hast. |
| **Kodi-Pfad anzeigen (Profis)** | Zeigt den echten Pfad. **✏ Pfad selbst ändern** macht daraus eine eigene Quelle. |
| **Quelle (Kodi-Pfad)** | Bei „Eigene Quelle“ und „Inhalt aus einem Addon“: z.B. `videodb://…`, `musicdb://…`, `plugin://…` oder eine `.xsp`-Playlist. |
| **Art der Medien** | Video, Musik, Bilder oder Dateien – wichtig für eigene Quellen. |
| **Darstellung** | 🎬 Poster (hochkant) · 🖼 Breitbild (16:9) · 💿 Quadratisch · 📋 Liste (untereinander) |
| **Max. Einträge** | Standard 20. |
| **Abstand** | Platz zwischen den Kacheln. |
| **Zeilenhöhe** | Nur bei „Liste“. |
| **Infos zum gewählten Titel zeigen** | Unter der Reihe erscheinen Titel, eine Info-Zeile (Jahr · Bewertung · Laufzeit · Genre · „45 % gesehen“, bei Folgen Serie und S01E05, bei Musik Interpret) und der Inhalt. |
| **Endlos blättern (Karussell)** | Am Ende geht es wieder von vorne los. |
| **Textfarbe, Farbe der Kacheln** | Die Kachelfarbe sieht man, bis die Bilder geladen sind. |
| **Form & Stil** | Rundung **jeder Kachel**, Rahmen, Deckkraft. |

💡 **Größe:** Die Bilder richten sich nach der **Höhe** des Widgets. Zieh die weiße Ecke nach unten – dann werden die Poster größer. Die Überschrift braucht 60 px, die Infos 150 px.

### So verhält sich ein Widget in Kodi

- Beim Öffnen der Seite holt das Addon die Einträge – mit Postern, Fanart oder Vorschaubild, je nach Darstellung.
- **Klick auf einen Film, eine Folge oder ein Lied** spielt ihn ab. **Klick auf einen Ordner** (z.B. eine Serie, ein Album, ein Addon-Ordner) öffnet ihn in Kodi.
- Danach kommt man – wie bei allen Kodi-Fenstern – wieder in dein Menü zurück.
- Ist ein Widget leer, springt der Startfokus automatisch auf das nächste bedienbare Element.

In der **Vorschau** siehst du Beispiel-Titel mit bunten Platzhaltern. Im **▶ Testmodus** meldet ein Klick, was Kodi tun würde.

<a id="k18"></a>

## 18. Info-Widgets und Gruppen

Info-Widgets sind **fertige Karten aus mehreren Teilen** (Fläche, Texte, Buttons …), die als **Gruppe** zusammengehören.

| Info-Widget | Inhalt |
|---|---|
| 🕒 **Uhr & Datum** | Große Uhrzeit und Datum auf einer Glas-Karte |
| 🌤 **Wetter** | Ort, Temperatur und Wetterlage (Kodi braucht dafür ein eingerichtetes Wetter-Addon) |
| ▶ **Jetzt läuft** | Cover, Titel, Zeit, Fortschritt und die Buttons Play/Pause, Weiter, Stopp – **nur sichtbar, wenn etwas läuft** |
| 💻 **System-Info** | CPU-Last, freier Speicher, IP-Adresse, Kodi-Version |

### So arbeitest du mit Gruppen

- **Ein beliebiges Teil ziehen** → die ganze Gruppe wandert mit. Die anderen Teile bekommen einen gestrichelten Rahmen.
- **Pfeiltasten, ◀ ▲ ▼ ▶, X/Y-Felder und „mittig“** bewegen ebenfalls die ganze Gruppe.
- **Größe, Text, Farbe, Schrift** stellst du **pro Teil** ein.
- In den Eigenschaften erscheint die Karte **🧩 Teil eines Info-Widgets** mit:
  - **⧉ Ganzes Widget** – dupliziert alle Teile,
  - **🗑 Ganzes Widget** – löscht alle Teile,
  - **✂ Lösen** – macht aus der Gruppe einzelne Elemente.
- Kopierst oder duplizierst du **ein einzelnes Teil**, ist die Kopie kein Teil der Gruppe mehr.

<a id="k19"></a>

## 19. Listen, Kachel-Raster und Karussell

Listen blättert man mit der Fernbedienung durch. Jeder Eintrag hat seine eigene Aktion.

| Einstellung | Möglichkeiten |
|---|---|
| **Art der Liste** | Liste (normal) · Kachel-Raster (panel) · Endlos-Karussell (wraplist) · Fester Fokus (fixedlist) |
| **Richtung** | Senkrecht oder waagerecht (nicht beim Kachel-Raster) |
| **Eintrag-Höhe, Eintrag-Breite, Abstand** | in Pixeln |
| **Inhalt** | **Eigene Einträge** oder **automatisch aus Kodi** |

**Eigene Einträge:** Titel, Zusatz rechts (optional), Bild (Adresse oder vom Gerät) und eine Aktion wie bei Buttons – inklusive 📚 Befehlsliste. Mit ↑ ↓ sortieren, ✖ löschen, **＋ Eintrag hinzufügen**.

**Automatisch aus Kodi:** Ein Kodi-Pfad plus Schnellknöpfe (Neue Filme, Neue Folgen, Alle Filme, Alle Serien, Serien weiterschauen, Neue Alben, Zuletzt gehört, Video-Playlists, Addon). Maximal 30 Einträge als Standard.

💡 **Liste oder Widget?** Für Inhalte aus der Bibliothek ist ein **Widget** meist die schönere Wahl: Es hat Überschrift, passende Bilder je Darstellung und auf Wunsch Infos zum Titel. Listen sind ideal für **eigene Einträge** mit eigenen Aktionen.

<a id="k20"></a>

## 20. Ein/Aus-Schalter

Ein echter Schalter, der sich seinen Zustand merkt – auch nach einem Neustart.

| Modus | Was er schaltet |
|---|---|
| **Eigener Merker** | Eine Kodi-Eigenschaft, z.B. `meinkinohub.kindermodus`. Damit blendest du andere Elemente ein oder aus (siehe [Kapitel 31](#k31)). |
| **Option dieses Addons** | Eine An/Aus-Option aus deinen Addon-Einstellungen. **＋ Neue An/Aus-Option dafür anlegen** erledigt das in einem Schritt. |
| **Kodi-Systemeinstellung** | Eine Kodi-Einstellung mit An/Aus-Wert, z.B. `services.webserver` (Vorschläge erscheinen beim Tippen). |

Zusätzlich kann der Schalter beim **Ein- und Ausschalten je einen Kodi-Befehl** ausführen, z.B. `Notification(Kindermodus,An,2000)`. Mit **Vorschau: eingeschaltet zeigen** legst du fest, wie er auf der Bühne aussieht. Auch Schalter lassen sich mit PIN oder Sicherheitsfrage schützen.

Die Bedingung für einen Merker lautet: `String.IsEqual(Window(Home).Property(NAME),1)` – der 📋-Knopf kopiert sie.

<a id="k21"></a>

## 21. Regler

Ein Regler wird in Kodi mit links/rechts bedient.

- **Lautstärke** – regelt Kodis Lautstärke.
- **Spulen** – springt im laufenden Video oder Lied (am besten mit „Wann sichtbar? → Nur wenn etwas läuft“).

In der Vorschau tippst du im Testmodus auf eine Stelle des Reglers.

<a id="k22"></a>

## 22. Textbox und Laufschrift

- **📝 Textbox:** mehrzeiliger Text mit Zeilenumbrüchen. Mit **Langen Text automatisch scrollen** läuft zu langer Text in Kodi langsam durch.
- **📰 Laufschrift:** Ein normaler Text mit der Option **Laufschrift, wenn der Text zu lang ist** (im 🛠 Modding des Elements). Dort gibt es auch **Mehrzeilig**.

<a id="k23"></a>

## 23. Videofenster, Visualisierung, RSS-Ticker

| Baustein | Zeigt in Kodi |
|---|---|
| 📺 **Videofenster** | Das laufende Video als Fenster im Menü (voreingestellt: nur sichtbar, wenn ein Video läuft). |
| 🌈 **Visualisierung** | Kodis Musik-Visualisierung (nur bei Musik). |
| 📡 **RSS-Ticker** | Nachrichten aus Kodis RSS-Feeds (in Kodi: Einstellungen → Oberfläche → RSS-Feeds einschalten). |

In der Vorschau siehst du jeweils einen Platzhalter.

<a id="k24"></a>

## 24. Modding pro Element

Jedes Element hat unten in den Eigenschaften den Bereich **🛠 Modding (Profis)**:

| Einstellung | Wirkung |
|---|---|
| **Kodi-ID** und **Fokus-Bedingung** | z.B. `Control.HasFocus(105)` – mit 📋 kopieren. |
| **Schrift** | Kodi-Schriftname aus dem aktiven Skin, z.B. `font10` (klein) bis `font45` (groß). |
| **Laufschrift / Mehrzeilig** | nur bei Texten |
| **✨ Animationen** | Einblenden, von links/rechts/oben/unten hereinfahren, Heranzoomen (mit Federn), Ausblenden beim Schließen, Pulsieren, Schweben, Drehen, **Wachsen, wenn ausgewählt** |
| **Verzögerung beim Erscheinen** | 0–2000 ms – so fahren Elemente nacheinander herein |
| **Kodi-Befehl bei Fokus / wenn Fokus weggeht** | z.B. `SetProperty(meinmenue.bild,filme,home)` |
| **Eigene XML-Zeilen** | Werden 1:1 in das Kodi-Control geschrieben (`<animation>`, `<enable>`, `<onclick>` …). ✔ Prüfen testet die Syntax. |

Animationen siehst du nur in Kodi, nicht in der Vorschau.

---

# Teil C – Die Modding-Werkstatt

<a id="k25"></a>

## 25. Überblick

Die **🛠 Modding-Werkstatt** (Kopfzeile oder Bereich 6) bündelt alle Profi-Funktionen in acht Reitern: 🎛 Schalter · 🧩 Bausteine · 🧰 Werkzeuge · 📄 Seiten-Tuning · ⌨ Tasten · 🧠 Bedingungen · 🔍 Inspektor & Links · 🧬 Projekt-JSON.

Alles ist optional und wirkt sofort. Während die Werkstatt offen ist, zeigt dir die **👁 Live-Ansicht** jede Änderung – und du kannst darin Elemente antippen, um sie z.B. als Vorlage für die Ausrichten-Werkzeuge zu markieren.

<a id="k26"></a>

## 26. Schalter

### 🖥 Im Generator

| Schalter | Wirkung |
|---|---|
| 🔢 Kodi-IDs auf der Bühne zeigen | Jedes Element zeigt seine Control-ID. |
| ➕ Hilfslinien | Mittellinien und Drittel-Raster. |
| 📺 Sicherer Bereich | Zeigt den Rand, den manche Fernseher abschneiden. |
| 👁 Live-Ansicht in Menüs | Siehe [Kapitel 8](#k8). |
| 📐 Rastergröße | 5, 10, 20, 40 oder 80 px – auch die Schrittweite der Pfeiltasten. |

### ✨ Optik in Kodi

| Schalter | Wirkung |
|---|---|
| 🔍 Fokus-Zoom | Ausgewählte Buttons und anklickbare Elemente wachsen ein Stück (101–125 %). |
| 🎞 Nacheinander einblenden | Alle anklickbaren Elemente gleiten beim Öffnen einer Seite nacheinander herein. |
| 🌑 Textschatten | Bessere Lesbarkeit auf hellen Bildern. |
| 🔤 Standard-Schrift | Für alle Texte ohne eigene Schrift (Standard `font13`). |
| 🎯 Textfarbe bei Fokus | Schrift auf ausgewählten Buttons, Schaltern und Listeneinträgen. |
| 🟢 Farbe „Schalter AN“ | |

### 🧭 Verhalten in Kodi

| Schalter | Wirkung |
|---|---|
| 🏠 Beenden führt zur Kodi-Startseite | Wer das Addon verlässt, landet auf der Kodi-Startseite statt in Kodis Video-Ansicht. *(Standard: an)* |
| ↩ Nach Kodi-Fenstern zurück ins Menü | Nach Kodi-Fenstern, anderen Addons und Videos öffnet sich dein Menü wieder. *(Standard: an)* |
| ⬅ Zurück auf der Startseite | **Schließt das Addon** (Standard) · **Erst beim zweiten Zurück schließen** – beim ersten Mal erscheint „Zum Verlassen noch einmal Zurück drücken“ · **Schließt das Addon nie** – verlassen nur über einen Button mit „Addon komplett schließen“. Auf Unterseiten geht Zurück immer eine Seite zurück. Auch direkt in den Einstellungen über Bereich 6 zu finden. |
| ❓ Beim Verlassen nachfragen | „Addon wirklich verlassen?“ auf der Startseite. |
| 🧠 Letzte Seite merken | Das Addon öffnet sich dort, wo man es verlassen hat. |
| 🔗 Direkt-Links erlauben | Jede Seite lässt sich direkt öffnen (siehe [Kapitel 38](#k38)). *(Standard: an)* |
| 🖱 Kontextmenü (lange drücken, Rechtsklick, Taste C) | Eigenes Kontextmenü im fertigen Addon (siehe [Kapitel 57](#k57)). *(Standard: an)* |
| 🚀 Autostart-Option einbauen | Erzeugt `service.py` und die Option „Beim Kodi-Start automatisch öffnen“. Einstellbar: Wartezeit nach dem Start und ob die Option nach der Installation schon an ist. |
| 🎵 Hintergrundmusik | Spielt beim Öffnen Musik oder einen Radio-Stream – auf Wunsch nur, wenn gerade nichts läuft, und mit Stopp beim Verlassen. |

### 🐍 Für Profis

| Schalter | Wirkung |
|---|---|
| 🐍 Python-Hooks | Eigene Python-Funktionen als Aktion (siehe [Kapitel 37](#k37)). |
| 🐞 Ausführliches Kodi-Log | Schreibt jeden Seitenwechsel und Schalter ins Kodi-Log. |

<a id="k27"></a>

## 27. Bausteine

Ein Klick fügt den Baustein auf der aktuellen Seite ein: Liste, Kachel-Raster, Karussell, **Widget „Neue Filme“**, **Widget „Weiterschauen“**, **Widget aus Addon**, **✨ Alle Widgets …**, Ein/Aus-Schalter, Lautstärke-Regler, Spul-Regler, Textbox, Laufschrift, Videofenster, Visualisierung, RSS-Ticker, Große Uhr, Wetter-Zeile und Pulsierender Hinweis.

<a id="k28"></a>

## 28. Werkzeuge

**Am markierten Element ausrichten** – wirkt auf alle nicht gesperrten Elemente **derselben Art** auf der Seite:

- Links, Mitte, Rechts, Oben, Mitte, Unten
- Gleichmäßig verteilen (waagerecht oder senkrecht, ab drei Elementen)
- Gleiche Breite, Höhe oder beides

**Ganze Seite:** Spiegeln (links ↔ rechts), alles aufs Raster, alles ins Bild holen, Seite duplizieren, alles sperren/entsperren, alles um X/Y verschieben, alles skalieren (von der Bildmitte aus).

Gesperrte Elemente bleiben unverändert. Alles lässt sich mit ↩ Rückgängig zurücknehmen.

<a id="k29"></a>

## 29. Seiten-Tuning

| Einstellung | Wirkung |
|---|---|
| 🪟 **Als Dialog öffnen** | Die Seite legt sich über das, was gerade in Kodi zu sehen ist – ideal für Pop-up-Menüs. Mit **Abdunkeln** (0–100 %) stellst du ein, wie stark der Hintergrund gedimmt wird. |
| 🎯 **Startfokus** | Welches Element beim Öffnen ausgewählt ist. Automatisch = oben links. |
| 🔗 **Direkt-Link** | Adresse und Befehl, um genau diese Seite zu öffnen. |
| ▶ **Befehle beim Öffnen** / ⏹ **beim Schließen** | Ein Kodi-Befehl pro Zeile (`<onload>` / `<onunload>`). |
| 🧬 **Eigene Controls (XML)** | Wird am Ende der Seite eingefügt – für eigene Gruppen, Labels, Bilder, Variablen-Tricks. |

<a id="k30"></a>

## 30. Tasten

Lege fest, was eine Taste der Fernbedienung oder Tastatur **auf allen Seiten** macht: Kontextmenü, Info, Pause, Play, Play/Pause, Stopp, Nächster/Vorheriger Titel, Bild hoch/runter, Menü-Taste, Ziffern 0–9 – oder eine **eigene Aktions-ID** aus dem Kodi-Wiki („Action IDs“). Jede Taste bekommt eine Aktion wie ein Button.

⚠️ „Zurück“ (Aktions-IDs 10 und 92) ist bewusst gesperrt, damit man das Addon immer verlassen kann. Kodi führt die normale Funktion einer Taste eventuell zusätzlich aus.

💡 Mit eingeschaltetem 🖱 Kontextmenü öffnet **Taste C** (Aktions-ID 117) das eigene Kontextmenü des Addons ([Kapitel 57](#k57)).

<a id="k31"></a>

## 31. Bedingungen

Der **🧠 Bedingungs-Baukasten** hilft beim Feld „👁 Wann sichtbar?“.

- **Schreibweise:** `+` = UND, `|` = ODER, `!` = NICHT, `[ ]` = Klammer.
- **29 fertige Bedingungen** in den Gruppen Wiedergabe, System, Zeit, Gerät, Bibliothek und Wetter & TV – z.B. „Video läuft“, „5 Min. keine Eingabe“, „Abends 18–23 Uhr“, „Dezember“, „Android“, „Filme vorhanden“, „TV-Aufnahme läuft“.
- **Deine Schalter:** „🟢 Kindermodus ist AN“ / „⚪ … ist AUS“ für jeden Merker.
- **Fokus auf dieser Seite:** „🎯 Filme“ ergibt `Control.HasFocus(ID)`.
- **🧪 Prüfen** testet Klammern und Verknüpfungen, **✅ Übernehmen** setzt die Bedingung beim markierten Element.

Beispiel: `Player.HasVideo + !Player.Paused` = „nur wenn ein Video läuft und nicht pausiert ist“.

<a id="k32"></a>

## 32. Inspektor und Links

Zeigt alle Seiten mit Dateiname, Seiten-ID und Favoriten-Befehl sowie jedes Element mit **Kodi-ID, Art, Name, Aktion und Sichtbarkeit**. 🎯 springt direkt zum Element auf der Bühne.

<a id="k33"></a>

## 33. Projekt-JSON

Das komplette Projekt (ohne Bilddaten) als JSON – zum Ansehen, Kopieren, Formatieren und Ändern. Seiten-Hintergrundbilder stehen als `§BILD§` darin und bleiben erhalten. **💾 Übernehmen** prüft das JSON und übernimmt es; Seiten-Änderungen lassen sich mit ↩ Rückgängig zurücknehmen.

⚠️ Sichere dein Projekt vorher mit **💾 Speichern**.

---

# Teil D – Für Profis

<a id="k34"></a>

## 34. Inhalt des ZIP

```text
plugin.video.<projektname>/
├── addon.xml                 Name, Version, Abhängigkeiten, Icon, Fanart, Screenshots
├── addon.py                  Startet das Menü, führt Aktionen aus, füllt Listen und Widgets
├── pages.json                Seiten, Aktionen, Listen, Widgets, Schalter, Tasten, Optionen
├── icon.png
├── fanart.jpg
├── service.py                nur mit Autostart oder eingebundenem Fremd-Addon
├── resources/
│   ├── settings.xml          nur mit eigenen Addon-Optionen oder Autostart
│   ├── screenshot-01.jpg …   bis zu 8
│   ├── bundled/<id>.zip      nur mit Fremd-Addon: die unveränderte ZIP, wird beim Installieren entpackt
│   ├── lib/custom.py         nur mit Python-Hooks oder Fremd-Addon (wird mit Beispielen angelegt)
│   └── skins/Default/
│       ├── 1080i/
│       │   ├── home.xml      Startseite
│       │   └── page_1.xml …  weitere Seiten in der Reihenfolge der Seiten-Leiste
│       └── media/
│           ├── white.png, background.jpg, bg_page_<n>.jpg
│           ├── img_<id>.png/.jpg          deine Bilder
│           ├── round_<r>.png, ring_<r>_<b>.png, mask_<b>x<h>_<r>.png   Rundungen, Rahmen, Bild-Masken
│           └── kfe_sw_*.png, kfe_sbar.png, kfe_snib.png                Schalter und Regler
└── (deine eigenen Ordner und Dateien)
```

Das Addon ist ein `xbmc.python.pluginsource` mit `<provides>video</provides>`. Jede Seite läuft als `xbmcgui.WindowXML` – Dialog-Seiten als `WindowXMLDialog`.

<a id="k35"></a>

## 35. Kodi-IDs

Die IDs ergeben sich aus der **Reihenfolge der Elemente auf ihrer Seite** (Index ab 0):

| Element | Control-ID |
|---|---|
| Bedienbare Controls: Button, Liste, Schalter, Regler, **Widget** | `100 + Index` |
| Andere Elemente **mit Aktion** (Bild, Text, Fläche …) | Anzeige `100 + Index`, darüber ein unsichtbarer Button `1000 + Index` (der bekommt den Fokus) |
| Reine Anzeige-Elemente | `100 + Index` |
| Rahmen (bei Rahmen-Dicke > 0) | `2000 + Index` |
| Bild-Hintergrund eines Buttons | `4000 + Index` |
| Seitenhintergrund | `99` |

Mit **🔢 Kodi-IDs auf der Bühne zeigen** oder im **🔍 Inspektor** siehst du alle IDs.

⚠️ **⬆ nach vorn / ⬇ nach hinten**, Löschen und Einfügen ändern die Reihenfolge – und damit die IDs. Prüfe danach Bedingungen wie `Control.HasFocus(…)` und `SetFocus(…)`.

<a id="k36"></a>

## 36. pages.json

Die `pages.json` steuert das Verhalten des Addons. Ein gekürztes Beispiel:

```json
{
  "start": "home",
  "welcome": "Willkommen im Kino-Hub!",
  "pages": [
    { "id": "home", "name": "Start", "file": "home.xml", "dlg": false, "focus": 105, "ids": [105, 111, 106] }
  ],
  "actions": {
    "home": { "105": { "k": "page", "v": "filme" }, "110": { "k": "exit", "ask": "Kino-Hub wirklich verlassen?" } }
  },
  "lists": {
    "home": { "111": { "dir": "videodb://recentlyaddedmovies/", "media": "video", "max": 20, "w": 1, "style": "poster" } }
  },
  "switches": {},
  "keys": {},
  "close": ["activatewindow", "playmedia", "…"],
  "noreturn": ["activatewindow(home", "quit", "…"],
  "bundles": [],
  "browse": "",
  "opts": { "home_exit": true, "return_menu": true, "confirm_exit": false, "remember": false, "deeplinks": true, "ctx": true, "hooks": false, "debug": false, "bgm": "", "bgm_idle": true, "bgm_stop": true }
}
```

| Schlüssel | Bedeutung |
|---|---|
| `pages[].focus` / `ids` | Startfokus und alle bedienbaren IDs der Seite (für die Fokus-Reserve bei leeren Widgets) |
| `actions` | Aktion je Control-ID: `page`, `back`, `home`, `exit`, `cmd` (mit `c` = Befehl, `close` = Menü vorher schließen), `py` (Python-Funktion), optional `pin` und `ask`. Bei Listen: `k: "list"` mit `items`. Zusätzlich `browse` (Ordner im Live-Browser öffnen, `v` = Kodi-Pfad) |
| `lists` | Eigene Einträge als Liste – oder ein Objekt mit `dir`, `media`, `max`. **Widgets** haben zusätzlich `w: 1` und `style` |
| `switches` | Modus `m` (`flag`, `addon`, `kodi`), Schlüssel `k`, Befehle `on` / `off` |
| `keys` | Aktion je Kodi-Aktions-ID |
| `close` / `noreturn` | Befehle, vor denen sich das Menü schließt bzw. nach denen das Addon endet |
| `bundles` | Eingebundene Fremd-Addons (ID, Pfad der ZIP, Abhängigkeiten) – werden beim Start entpackt und eingeschaltet |
| `browse` | ID der Browser-Seite (Seite mit einer Live-Browser-Liste), die Ordner aus Fremd-Addons anzeigt |
| `opts` | Die Schalter aus der Modding-Werkstatt, z.B. `ctx` für das Kontextmenü |

<a id="k37"></a>

## 37. Python-Hooks (custom.py)

Schalte in der Modding-Werkstatt **🐍 Python-Hooks** ein. Dann entsteht `resources/lib/custom.py` mit Beispielen (`hallo`, `zufallsfilm`, `nachfragen`). Eine eigene `custom.py` unter 📁 ersetzt die Vorlage.

**Als Aktion:** Wähle bei einem Element **Python-Funktion** und trage den Funktionsnamen ein, z.B. `zufallsfilm`. Jede Funktion bekommt das geöffnete Menü-Fenster:

```python
def meine_funktion(window):
    # ... dein Code ...
    return 'page:filme'   # optional
```

| Rückgabe | Wirkung |
|---|---|
| `'back'` | eine Seite zurück |
| `'home'` | zur Startseite des Addons |
| `'exit'` | Addon schließen |
| `'page:ID'` | zu einer Seite springen (Seiten-ID siehe Seiten-Tuning oder Inspektor) |
| `'browse:PFAD'` | einen Kodi-Pfad im Live-Browser zeigen, z.B. `'browse:plugin://plugin.video.xyz/'` |
| jeder andere Text | wird als Kodi-Befehl ausgeführt, z.B. `'PlayMedia("…")'` |
| `None` | nichts weiter |

**Automatisch aufgerufen**, wenn vorhanden: `on_start()`, `on_page(window, page_id)` bei jeder geöffneten Seite und `on_exit()`.

**Kontextmenü erweitern:** `kontextmenue(window, info)` gibt eine Liste von `(Beschriftung, Rückgabe)` zurück – die Rückgabe gilt wie in der Tabelle oben (siehe [Kapitel 57](#k57)).

Fehler in `custom.py` landen im Kodi-Log, Kodi zeigt zusätzlich eine Meldung.

<a id="k38"></a>

## 38. Direkt-Links und Favoriten

Mit **🔗 Direkt-Links erlauben** lässt sich jede Seite direkt öffnen:

```text
plugin://plugin.video.meinkinohub/?page=filme
RunPlugin(plugin://plugin.video.meinkinohub/?page=filme)
```

- Statt der Seiten-ID funktioniert auch der **Seitenname** (Groß-/Kleinschreibung egal).
- Die fertigen Links stehen im **🔍 Inspektor** und im **📄 Seiten-Tuning**.
- Als Kodi-Favorit in `userdata/favourites.xml`:

```xml
<favourite name="Meine Filme">RunPlugin(plugin://plugin.video.meinkinohub/?page=filme)</favourite>
```

Auch Skins mit eigenen Menüpunkten oder andere Addons können so direkt auf eine Unterseite springen. Die Startseite liegt dabei immer darunter – „Zurück“ führt dorthin.

<a id="k39"></a>

## 39. Merker, Zustände und Speicherorte

| Was | Wo |
|---|---|
| Schalter-Merker | `userdata/addon_data/plugin.video.<name>/state.json` unter `flags` – beim Start als Eigenschaft im Home-Fenster gesetzt, abfragbar mit `String.IsEqual(Window(Home).Property(NAME),1)` |
| Letzte Seite (wenn „merken“ an) | dieselbe `state.json` unter `last` |
| Addon-Optionen | `userdata/addon_data/plugin.video.<name>/settings.xml` |
| Kodi-Einstellungen (Schalter-Modus „Kodi“) | werden über JSON-RPC (`Settings.SetSettingValue`) direkt in Kodi geändert |

Weil Merker als Home-Eigenschaft gesetzt sind, kannst du sie auch in deinem Kodi-Skin oder in anderen Addons abfragen – sobald das Addon nach einem Kodi-Start einmal geöffnet wurde.

<a id="k40"></a>

## 40. So füllen sich Widgets und Listen

Beim Öffnen einer Seite fragt `addon.py` jede Bibliotheks-Liste und jedes Widget über Kodis JSON-RPC ab:

```text
Files.GetDirectory  directory=<Pfad>  media=<video|music|pictures|files>
                    properties=[title, thumbnail, art, year, rating, plot, runtime, genre,
                                season, episode, showtitle, artist, resume]
                    limits={start: 0, end: <Max. Einträge>}
```

Kennt eine ältere Kodi-Version einen Teil der Abfrage nicht, versucht das Addon es ohne `limits` und zuletzt mit der einfachen Abfrage (`title`, `thumbnail`, `art`). Das Widget erscheint dann trotzdem – nur ohne Zusatz-Infos.

**Bilder je Darstellung** (das erste vorhandene gewinnt):

| Darstellung | Reihenfolge |
|---|---|
| Poster | `poster` → `tvshow.poster` → `season.poster` → `thumb` |
| Breitbild | `landscape` → bei Folgen `thumb`, sonst `fanart` → `tvshow.fanart` → `thumb` |
| Quadratisch, Liste | `thumb` → `poster` → `icon` |

**Was jeder Eintrag mitbringt** – nutzbar in eigenen XML-Zeilen:

| Info | Inhalt |
|---|---|
| `ListItem.Label` | Titel |
| `ListItem.Label2` | Jahr bzw. `S01E05` bei Folgen |
| `ListItem.Art(thumb)` | das passende Bild |
| `ListItem.Property(kfe.meta)` | z.B. `2024 · ★ 7,8 · 112 Min. · Abenteuer · 45 % gesehen` |
| `ListItem.Property(kfe.plot)` | Inhaltsangabe |

Von außerhalb des Widgets: `$INFO[Container(ID).ListItem.Property(kfe.meta)]`.

**Bibliotheks-Widgets** nutzen intelligente Listen im Pfad, wie die Kodi-Skins auch – z.B. „Filme weiterschauen“:

```text
videodb://movies/titles/?xsp=<URL-kodiertes JSON>
{"order":{"direction":"descending","ignorefolders":0,"method":"lastplayed"},
 "rules":{"and":[{"field":"inprogress","operator":"true","value":[]}]},"type":"movies"}
```

Eigene Varianten baust du am einfachsten als **intelligente Playlist in Kodi** und trägst deren Pfad ein (siehe Rezept 11).

---

# Teil E – Rezepte

<a id="k41"></a>

## 41. Zwölf Rezepte Schritt für Schritt

### Rezept 1: Kindersicherung mit Schalter

1. Füge über die Modding-Werkstatt (🧩 Bausteine) einen **Ein/Aus-Schalter** ein und nenne ihn „Kindermodus“. Modus: **Eigener Merker**.
2. Gib dem Schalter unter **🔐 Schutz** einen PIN, z.B. `1234` – so können Kinder ihn nicht einfach ausschalten.
3. Markiere einen Button, den Kinder nicht sehen sollen → **👁 Wann sichtbar?** → **🧠 Baukasten** → „⚪ Kindermodus ist AUS“ → **✅ Übernehmen**.
4. Optional: ein Text „Kindermodus aktiv“ mit „🟢 Kindermodus ist AN“.

In der Vorschau ist alles sichtbar – in Kodi blenden sich die Elemente je nach Schalter ein und aus.

### Rezept 2: Startseite wie im Kodi-Hauptmenü

1. Lege links eine Spalte mit Menü-Buttons an (z.B. über die 📚 Befehlsliste).
2. **🧩 Widgets → Neue Filme**. Breite und Position so ziehen, dass das Widget rechts neben den Buttons steht.
3. Darunter **Filme weiterschauen** und **Neue Folgen**. Tipp: Ein Widget mit ⧉ duplizieren und nur „Was soll das Widget zeigen?“ ändern.
4. Bei einem Widget **Infos zum gewählten Titel zeigen** einschalten.
5. Im **📄 Seiten-Tuning** den Startfokus auf den ersten Menü-Button setzen.

### Rezept 3: Pop-up-Menü als Dialog

1. **＋ Seite** „Schnellmenü“ anlegen.
2. Modding-Werkstatt → **📄 Seiten-Tuning** → **🪟 Als Dialog öffnen**, Abdunkeln z.B. 60 %.
3. Eine **⬛ Fläche** als Fenster in die Mitte, Form & Stil „Glas“ oder eigene Farbe.
4. Darauf die Buttons – und einen Button „Schließen“ mit der Aktion **Zurück**.
5. Auf der Startseite: Button „Schnellmenü“ mit **Andere Seite öffnen** – oder unter **⌨ Tasten** die Menü-Taste damit belegen.

### Rezept 4: Favorit direkt auf eine Unterseite

1. Modding-Werkstatt → 🎛 Schalter → **🔗 Direkt-Links erlauben** (Standard: an).
2. **🔍 Inspektor** → beim Eintrag der Seite den Befehl kopieren, z.B. `RunPlugin(plugin://plugin.video.meinkinohub/?page=filme)`.
3. In Kodi in `userdata/favourites.xml` eintragen (siehe [Kapitel 38](#k38)) oder in deinem Skin als eigenen Menüpunkt hinterlegen.

### Rezept 5: Zufallsfilm-Button

1. Modding-Werkstatt → 🎛 Schalter → **🐍 Python-Hooks** an.
2. Button „Überrasch mich“ → Aktion **Python-Funktion** → `zufallsfilm`.
3. Fertig – die Funktion steckt schon in der erzeugten `custom.py`.

Ohne Python geht es auch: **🧩 Widget „Zufällige Filme“**.

### Rezept 6: Radio im Hintergrund

1. Modding-Werkstatt → 🎛 Schalter → **🎵 Hintergrundmusik** an.
2. Die Adresse eines Radio-Streams eintragen – oder eine eigene Datei unter 📁 hochladen und ihren Pfad eintragen, z.B. `resources/musik.mp3`.
3. „Nur starten, wenn gerade nichts läuft“ und „Beim Verlassen des Addons stoppen“ nach Wunsch.

### Rezept 7: Begrüßung je nach Tageszeit

1. Drei Texte anlegen: „Guten Morgen“, „Guten Tag“, „Guten Abend“.
2. Jedem unter **👁 Wann sichtbar? → Eigene Bedingung** eine Zeit geben:
   - `System.Time(05:00,12:00)`
   - `System.Time(12:00,18:00)`
   - `[System.Time(18:00) | System.Time(00:00,05:00)]`
3. Alle drei auf dieselbe Stelle setzen (gleiche X/Y-Werte oder 🧰 Werkzeuge → Links/Oben ausrichten).

💡 In der Vorschau liegen sie übereinander – in Kodi ist immer nur einer sichtbar.

### Rezept 8: Infotext zum ausgewählten Button

1. Unter dem Menü für jeden Button einen Text anlegen, z.B. „Alle deine Filme auf einen Blick“.
2. Text markieren → **🧠 Baukasten** → **Fokus auf dieser Seite** → „🎯 Filme“ → ✅ Übernehmen. Das ergibt `Control.HasFocus(ID)`.
3. Alle Infotexte an dieselbe Stelle setzen.

⚠️ Die IDs hängen von der Reihenfolge ab ([Kapitel 35](#k35)) – nach „nach vorn/hinten“ im Inspektor kontrollieren.

### Rezept 9: Autostart für ein Kiosk-Menü

1. Modding-Werkstatt → 🎛 Schalter → **🚀 Autostart-Option einbauen**, Wartezeit z.B. 5 Sekunden, **Nach Installation schon an**.
2. **❓ Beim Verlassen nachfragen** einschalten.
3. Dem Beenden-Button einen **PIN** geben.

Die Option „Beim Kodi-Start automatisch öffnen“ steht danach in den Addon-Einstellungen und lässt sich dort jederzeit abschalten.

### Rezept 10: Widget aus einem anderen Addon

1. **🧩 Widgets → Inhalt aus einem Addon**.
2. Unter „Quelle“ die Adresse des Addons eintragen: `plugin://<addon-id>/`. Die ID findest du in Kodi in der Addon-Info oder als Ordnername im Kodi-Ordner `addons`.
3. Darstellung wählen (Breitbild passt zu den meisten Video-Addons).

⚠️ Das andere Addon wird bei jedem Öffnen der Seite gefragt. Addons, die eine Anmeldung brauchen oder langsam laden, verzögern deine Seite.

### Rezept 11: Eigene intelligente Playlist als Widget

1. In Kodi: **Videos → Playlists → Neue intelligente Playlist**, Regeln festlegen (z.B. „Genre ist Animation“) und als „Kinderfilme“ speichern.
2. Im Generator: **🧩 Widgets → Eigene Quelle**.
3. Quelle: `special://profile/playlists/video/Kinderfilme.xsp`, Art der Medien: Video, Darstellung: Poster.

### Rezept 12: Uhr- und Wetter-Ecke

1. **🧩 Widgets → Uhr & Datum** – die Karte an eine beliebige Stelle ziehen (alle Teile wandern mit).
2. **🧩 Widgets → Wetter** darunter setzen.
3. In Kodi ein Wetter-Addon einrichten (**Einstellungen → Dienste → Wetter**), sonst bleiben die Wetter-Texte leer.
4. Farben pro Teil anpassen – z.B. die Datumszeile in deiner Fokusfarbe.

---

# Teil F – Hilfe

<a id="k42"></a>

## 42. Unterschiede zwischen Vorschau und Kodi

| Thema | Vorschau im Generator | In Kodi |
|---|---|---|
| Emojis | sichtbar | in den meisten Kodi-Schriften nicht vorhanden |
| Schrift | an die Elementhöhe angepasst | die gewählte Kodi-Schrift (Standard `font13`) |
| Sichtbarkeit („Wann sichtbar?“) | alles immer sichtbar | Bedingungen steuern die Anzeige |
| Animationen | nicht zu sehen | laufen |
| Widgets | Beispiel-Titel mit bunten Platzhaltern | echte Inhalte aus Bibliothek oder Addon |
| Info-Widgets, Live-Infos | Beispielwerte (Uhrzeit echt) | echte Werte |
| Videofenster, Cover, Fortschritt, Visualisierung | Platzhalter | echte Wiedergabe |
| Befehle | werden im Testmodus nur angezeigt | werden ausgeführt |
| Live-Ansicht 👁 | Hilfe beim Bearbeiten | gibt es nur im Generator |

<a id="k43"></a>

## 43. Fehlerbehebung und häufige Fragen

**Mein Menü ist nach einem Update noch das alte.**
Version erhöhen (＋), neu exportieren und erneut aus der ZIP installieren. Hilft das nicht: altes Addon deinstallieren und neu installieren.

**Zurück wirft mich aus dem Addon.**
Auf der Startseite schließt Zurück das Addon – so ist es voreingestellt. Unter **⬅ Zurück auf der Startseite** (Einstellungen über Bereich 6 oder 🛠 Modding → Schalter) wählst du „Erst beim zweiten Zurück schließen“ oder „Schließt das Addon nie“. Bei „nie“ brauchst du einen Button mit **Addon komplett schließen** – fehlt er, exportiert der Generator zur Sicherheit „Erst beim zweiten Zurück schließen“, damit niemand festsitzt.

**Nach dem Beenden lande ich in Kodis Video-Ansicht.**
Modding-Werkstatt → 🎛 Schalter → **🏠 Beenden führt zur Kodi-Startseite** einschalten und neu exportieren.

**Nach einem Kodi-Fenster komme ich nicht ins Menü zurück.**
**↩ Nach Kodi-Fenstern zurück ins Menü** muss an sein. Befehle wie „Kodi-Startseite“ (`ActivateWindow(home)`), „Kodi beenden“ oder „Neustart“ beenden das Addon absichtlich. Manche Addons öffnen mehrere Ebenen – dann mehrmals Zurück drücken.

**Das Widget oder die Liste bleibt leer („Hier ist noch nichts …“).**
Sind die Inhalte in der Kodi-Bibliothek? Stimmt der Pfad (bei eigenen Quellen und Addons)? Ist das andere Addon installiert? Im Kodi-Log stehen Fehler der Abfrage (mit 🐞 Ausführliches Kodi-Log noch genauer).

**Das Widget zeigt keine Bilder oder keine Infos.**
Bilder kommen aus deiner Bibliothek – fehlen dort Poster oder Fanart, bleibt die Kachel einfarbig. Fehlen nur die Infos, nutzt deine Kodi-Version die einfache Abfrage (siehe [Kapitel 40](#k40)).

**Die Installation aus der ZIP klappt nicht.**
„Unbekannte Quellen“ erlauben (Einstellungen → System → Addons). Die ZIP nicht entpacken und nicht umbenennen.

**Funktioniert der Generator ohne Internet?**
Deine Daten bleiben immer im Browser. Für die Darstellung lädt die Seite aber Tailwind CSS aus dem Netz – ohne Internet sieht sie ungestaltet aus.

**„Browser-Speicher voll“.**
Große Bilder füllen den Speicher des Browsers. Sichere dein Projekt mit **💾 Speichern** als Datei und entferne nicht genutzte große Bilder.

**Die Schrift ist in Kodi kleiner oder größer als in der Vorschau.**
Kodi nutzt die Schriften des aktiven Skins. Stelle im 🛠 Modding des Elements eine andere Schrift ein (z.B. `font27`, `font37`, `font45`) oder ändere die Standard-Schrift in der Modding-Werkstatt.

**Meine Emojis fehlen in Kodi.**
Die meisten Kodi-Schriften haben keine Emojis. Das Feld „Symbol (Emoji)“ ist darum nur für die Vorschau gedacht.

**Ein Schalter im Modus „Kodi-Einstellung“ bewirkt nichts.**
Die Einstellung muss einen An/Aus-Wert haben und die ID muss stimmen (Vorschläge erscheinen beim Tippen). Manche Einstellungen wirken erst nach einem Neustart oder sind gesperrt – das Kodi-Log zeigt den Grund.

**Meine Python-Funktion tut nichts.**
Sind die **🐍 Python-Hooks** an? Gibt es die Funktion in `custom.py` genau so (Groß-/Kleinschreibung)? Fehler stehen im Kodi-Log, Kodi zeigt außerdem eine Meldung.

**Eine Taste ist doppelt belegt.**
Nur die letzte Belegung zählt – ✔ Prüfen weist darauf hin.

**Meine `Control.HasFocus`-Bedingung stimmt nicht mehr.**
Die IDs hängen von der Reihenfolge der Elemente ab ([Kapitel 35](#k35)). Prüfe sie im 🔍 Inspektor und baue die Bedingung neu.

**Änderungen aus dem Designer kommen nicht im ZIP an.**
Die Datei wurde im 💻 Editor von Hand geändert (✎). Sie wird dann genau so exportiert. Im Editor **↺ Original wiederherstellen**.

**Kodi meldet „Menü konnte nicht geladen werden“.**
Meist stimmt etwas in eigenen XML-Zeilen nicht. ✔ Prüfen zeigt fehlerhafte XML-Stellen; Details stehen im Kodi-Log.

**Die Live-Ansicht verdeckt etwas – oder erscheint nicht.**
Zieh sie am Kopf an eine freie Stelle oder mach sie mit ⤢ kleiner. ✖ blendet sie aus, der Knopf **👁 Live-Ansicht** unten links holt sie zurück. Sie erscheint nur, wenn die große Vorschau verdeckt ist ([Kapitel 8](#k8)).

**Wie verschiebe ich ein Teil eines Info-Widgets einzeln?**
Teil markieren → **✂ Lösen**. Danach sind alle Teile einzeln beweglich.

**Kann ich den Hintergrund des Beispiels ersetzen?**
Ja: 3 · Design → **🖼 Hintergrundbild** wählen (oder mit ✖ entfernen). Einzelne Seiten bekommen über **🎨 Hintergrund** ein eigenes Bild.

**Beim langen Drücken auf einen Button fliege ich aus dem Addon.**
Das war ein Fehler früherer Fassungen: Kodi macht aus langem Drücken einen Rechtsklick und schickt davor ein künstliches „Zurück“. Das fertige Addon erkennt das jetzt und öffnet das Kontextmenü, statt sich zu schließen. Neu exportieren und neu installieren. Mehr dazu in [Kapitel 57](#k57).

**Das Kontextmenü fehlt.**
Ist **🖱 Kontextmenü** in der Modding-Werkstatt an? Kodi selbst blendet in Addon-Fenstern sein eigenes Kontextmenü aus – darum bringt das Addon ein eigenes mit, das du mit langem Drücken, Rechtsklick oder Taste C öffnest.

**`No module named 'bs4'` (oder `requests`, `feedparser` …).**
Kodi installiert ein Python-Modul nur, wenn es in der `addon.xml` des Addons als `<import>` steht. Der Generator trägt es für dein Addon und für eingebundene Fremd-Addons selbst ein ([Kapitel 56](#k56)). Danach neu exportieren und installieren.

**Ein eingebundenes Fremd-Addon fehlt nach dem Neuladen des Generators.**
Die ZIP liegt nur im Speicher des Browsers (IndexedDB), nicht in der Projekt-Datei. Wähle sie unter **📦 Fremd-Addon** erneut aus. ✔ Prüfen weist darauf hin.

**Im Live-Browser lässt sich ein Eintrag nicht öffnen oder startet sofort ein Video.**
Der Browser erkennt Ordner und Videos an Kodis Verzeichnis-Abfrage. Liefert die Kodi-Version die Angabe „abspielbar“ nicht mit (ältere Versionen), behandelt das Addon den Eintrag als abspielbar. Nutze dann im Kontextmenü **In Kodis Ansicht öffnen** ([Kapitel 55](#k55)).

**Wo finde ich das Kodi-Log?**

| System | Pfad |
|---|---|
| Windows | `%APPDATA%\Kodi\kodi.log` |
| Linux | `~/.kodi/temp/kodi.log` |
| LibreELEC / CoreELEC | `/storage/.kodi/temp/kodi.log` |
| Android | `Android/data/org.xbmc.kodi/files/.kodi/temp/kodi.log` |
| macOS | `~/Library/Logs/kodi.log` |

<a id="k44"></a>

## 44. Tastenkürzel

| Taste | Wirkung |
|---|---|
| Pfeiltasten | markiertes Element (bzw. ganzes Info-Widget) um eine Rasterweite verschieben (Standard 20 px) |
| Umschalt + Pfeiltasten | um 100 px verschieben |
| Entf / Rücktaste | markiertes Element löschen |
| Strg + C / Strg + V | kopieren / einfügen (auch auf anderen Seiten) |
| Strg + D | duplizieren |
| Strg + Z | rückgängig |
| Strg + Y oder Strg + Umschalt + Z | wiederholen |
| Strg + S | Projekt speichern – im Editor: Datei übernehmen |
| Tab (im Editor) | einrücken |
| Strg + Z / Strg + Y (im Titan-Modus) | Änderungen im Titan-Modus rückgängig machen / wiederholen (auch ↶ ↷ oben rechts) |

Auf dem Mac gilt **Cmd** statt Strg. Auf Handy und Tablet nutzt du die Knöpfe ◀ ▲ ▼ ▶, ⧉, 🗑 und ↩ ↪.

---

# Teil G – Titan-Modus: dein eigener Kodi-Skin

<a id="k45"></a>

## 45. Was ist der Titan-Modus?

Mit dem Titan-Modus baust du einen **echten Kodi-Skin** – also das Aussehen von **ganz Kodi**, nicht nur von deinem Addon. Heraus kommt ein installierbarer Skin `skin.<name>`.

**Stufe A (jetzt verfügbar): Estuary umbauen.** Grundlage ist Estuary, der offizielle Standard-Skin von Kodi. Alles, was Estuary kann – Bibliothek, Ansichten, Player, Einstellungen, Dialoge – funktioniert weiter. Darüber legst du dein eigenes Design: Farben, Hintergrund, Logo, Schrift, Hauptmenü, eigene Menüpunkte und Widgets.

- **Öffnen:** **⚡ Titan** in der Kopfzeile oder **7 · ⚡ Titan-Modus** in den Einstellungen.
- **Aufbau:** links (auf dem Handy oben) eine **Live-Vorschau im Estuary-Stil**, rechts neun Reiter (bei fremden Skins vier, siehe Kapitel 52a): 🧬 Basis · 🎨 Farben · 📋 Hauptmenü · 🧩 Widgets · 📐 Layout · 🖼 Bilder & Schrift · 🪟 Fenster · 🔧 Profi · 📦 Export.
- Auf dem Handy bleibt die Vorschau beim Scrollen oben stehen – du siehst jede Änderung sofort.
- Alle Titan-Einstellungen gehören zu deinem Projekt und werden mit **💾 Speichern** mitgesichert.

<a id="k46"></a>

## 46. Grundlage laden (Reiter 🧬 Basis)

| Einstellung | Bedeutung |
|---|---|
| **Kodi-Version** | 19 Matrix, 20 Nexus, 21 Omega oder 22 Piers. Ein Skin passt immer nur zu **einer** Kodi-Version – wähle die deines Geräts. |
| **Name, Version, Autor** | Aus dem Namen entsteht die ID, z.B. `skin.titankino`. Für Updates die Version mit ＋ erhöhen. |
| **Sprachen** | Deutsch + Englisch (kleinere ZIP) oder alle Sprachen von Estuary. |

**So kommt Estuary in den Generator:**

- **⬇ Estuary laden (offiziell von Kodi):** lädt die passende Fassung direkt aus dem offiziellen Kodi-Archiv auf GitHub (rund 900 Dateien, etwa 10 MB). Danach bleibt sie im Browser gespeichert. Passiert auch automatisch beim ersten Export.
- **📦 Eigene Skin-ZIP:** die Alternative ohne Internet. Packe den Ordner `skin.estuary` deiner Kodi-Installation als ZIP und lade ihn hoch. Die Kodi-Version wird dabei automatisch erkannt.

| System | Ordner von Estuary |
|---|---|
| Windows | `C:\Program Files\Kodi\addons\skin.estuary` |
| Linux, LibreELEC | `/usr/share/kodi/addons/skin.estuary` |
| macOS | `/Applications/Kodi.app/Contents/Resources/Kodi/addons/skin.estuary` |
| Android | steckt in der App – hier bitte „⬇ Estuary laden“ nutzen |

💡 GitHub erlaubt ohne Anmeldung 60 Abfragen pro Stunde – ein Laden braucht nur zwei davon. **🗑 Zwischenspeicher leeren** löscht die gespeicherten Fassungen wieder.

⚠️ Andere Skins als Estuary lassen sich hochladen, dann klappen aber nur Farben und Schrift sicher.

<a id="k47"></a>

## 47. Farben, Hintergrund, Logo und Schrift

### Reiter 🎨 Farben

15 fertige **Farbwelten** (⚡ Titan plus die 14 Farben von Estuary) und **🔗 Wie mein Addon-Design**. Danach jede Farbe einzeln:

| Farbe | Wirkt auf |
|---|---|
| ✨ Akzent / Fokus | ausgewählte Menüpunkte, Buttons, Rahmen, Regler |
| 🌌 Hintergrund | färbt das Hintergrundbild von Estuary ein |
| 🔷 Muster (mit Deckkraft) | das feine Muster über dem Hintergrund |
| 🪟 Fenster & Dialoge | Menüs, Info-Fenster, Einstellungen |
| ⭐ Markiert / Gesehen | Häkchen, Markierungen, Hinweise |
| 🔤 Text / 🔡 Text gedimmt | Schrift und Zweitzeilen |

### Reiter 🖼 Bilder & Schrift

- **Hintergrund:** Estuary-Muster in deinen Farben – oder ein **eigenes Bild** mit Regler zum Abdunkeln. **🔗 Wie im Addon** übernimmt das Hintergrundbild aus dem Designer.
- **Logo oben links:** ersetzt das Kodi-Logo auf der Startseite (PNG mit durchsichtigem Hintergrund im Querformat).
- **Knöpfe über dem Menü:** Ausschalten-Menü, Einstellungen und Suche einzeln ein- oder ausblenden.
- **Schriftgröße:** 80–130 % für den ganzen Skin.
- **Eigene Schrift:** TTF oder OTF bis 3 MB – ersetzt die normale Schrift (Noto Sans). Achte darauf, dass du die Schrift weitergeben darfst, z.B. von Google Fonts.
- **Icon & Fanart des Skins:** automatisch in deinen Farben, wie dein Addon (inklusive Screenshots) oder die Originale von Estuary.

<a id="k48"></a>

## 48. Hauptmenü und eigene Menüpunkte

Im Reiter **📋 Hauptmenü** steht jeder Menüpunkt von Estuary als Zeile:

- **Schalter** = anzeigen oder ausblenden, **↑ ↓** = Reihenfolge,
- **Name** – leer lassen, dann zeigt Kodi den Original-Namen in deiner Sprache,
- **Symbol** – eines der 17 Estuary-Symbole oder ein **eigenes Bild** (wird auf 95×95 gebracht; weiße Symbole auf durchsichtigem Grund wirken am besten).

„Disc“ erscheint in Kodi nur bei eingelegter Disc, „Spiele“ nur, wenn Spiele in Kodi aktiviert sind.

### Eigene Menüpunkte (bis zu 9)

**＋ Mein Addon als Menüpunkt** legt sofort einen Punkt an, der dein Addon aus dem Designer öffnet. **＋ Eigener Menüpunkt** kann noch mehr:

| Klick-Aktion | Was passiert |
|---|---|
| Mein Addon öffnen | öffnet dein Addon mit seinem eigenen Menü |
| Eine Seite meines Addons | springt direkt auf eine Unterseite (dafür im 🛠 Modding „Direkt-Links erlauben“ an lassen) |
| Anderes Addon öffnen | ID wie `plugin.video.youtube` oder eine `plugin://…`-Adresse |
| Kodi-Befehl | aus der 📚 Befehlsliste oder selbst geschrieben |
| Nichts | nur zum Anzeigen von Widgets |

💡 Wie die Menüpunkte **aussehen und wo sie stehen** – als Liste, als einzelne Buttons, waagerecht oder senkrecht –, stellst du im Reiter 📐 Layout ein ([Kapitel 50](#k50)).

💡 **Die perfekte Kombi:** Addon im Designer bauen, im Skin einen Menüpunkt „Mein Addon“ anlegen – fertig ist dein eigenes Kodi von vorne bis hinten. Installiere dafür **beide** ZIPs.

<a id="k49"></a>

## 49. Widgets im Skin

Im Reiter **🧩 Widgets** wählst du oben den Menüpunkt. Bei den Estuary-Punkten entscheidest du:

- **Wie Estuary** – die Reihen bleiben wie im Original (Kategorien, Weiterschauen, Neu …),
- **Eigene Widgets** – deine Reihen ersetzen die von Estuary. Eigene Menüpunkte haben immer eigene Widgets.

Pro Menüpunkt bis zu **9 Widgets**. Jedes hat:

| Einstellung | Möglichkeiten |
|---|---|
| **Quelle** | dieselben 14 Quellen wie im Designer: Neue Filme, Filme weiterschauen, Noch nicht gesehen, Zufällige Filme, Am besten bewertet, Neue Folgen, Serien weiterschauen, Zufällige Serien, Neue Alben, Zuletzt gehört, Zufällige Alben, Video-Playlists, Inhalt aus einem Addon, Eigene Quelle |
| **Überschrift** | leer = Name der Quelle |
| **Darstellung** | 🎬 Poster · 🖼 Breitbild · 💿 Quadratisch · 📋 Kategorien |
| **Kodi-Pfad, Art der Medien** | nur bei „Eigene Quelle“ und „Inhalt aus einem Addon“ |

Die Widgets füllt **Kodi selbst** – mit den bewährten Widget-Bausteinen von Estuary. Das ist schnell, braucht kein Python, zeigt beim Laden den Kodi-Kreisel und blendet leere Reihen aus. In Kodi geht es mit **→** vom Menü in die Widgets und mit **←** zurück.

<a id="k50"></a>

## 50. Layout: alles frei verschieben

Im Reiter **📐 Layout** machst du Estuary wirklich zu deinem. Hier legst du fest, **wo** die Teile des Skins stehen – nicht nur, wie sie aussehen.

| Was du verschieben kannst | Hinweis |
|---|---|
| Logo und Uhr | ziehen und in der Größe ändern |
| Knöpfe über dem Menü | Ausschalten-Menü, Einstellungen, Suche |
| **Hauptmenü** | als Liste oder als einzelne Buttons (siehe unten) |
| **Widget-Bereich** | bewegt sich als Ganzes; ausblenden schaltet alle Widgets auf einmal ab |
| Player-Leiste | die Steuerleiste bei der Wiedergabe |
| Dunkle Seitenfläche | die Fläche von Estuary, dort wo sonst das Menü steht |

### Das Hauptmenü: Liste oder einzelne Buttons

- **Liste (wie Estuary):** Das Menü bleibt eine Liste und lässt sich nur als Ganzes verschieben.
- **Einzelne Buttons:** Jeder Menüpunkt ist ein eigener Button, den du **frei platzierst** – senkrecht, waagerecht, im Kreis, wie du magst. Fertige Anordnungen setzen die Buttons mit einem Klick in eine Reihe oder Spalte. Die **Reihenfolge** im Reiter 📋 Hauptmenü bestimmt dabei nur die Liste, die **Lage** legst du hier fest.

### Eigene Elemente als Dekoration

Wie im Addon-Designer: Element hinzufügen, an die gewünschte Stelle ziehen, an der Ecke die Größe ändern. Das geht mit **eigenen Bildern**, Flächen und Texten. Texte können Live-Infos zeigen (Uhrzeit, Wetter, „Läuft gerade“ …).

| Einstellung | Wirkung |
|---|---|
| **Ebene** | Das Element liegt hinter oder vor Menü und Widgets. |
| **Nur bei Menüpunkt** | Kodi zeigt das Element nur bei einem bestimmten Menüpunkt. |
| **Eigener Hintergrund für …** | Ein Menüpunkt bekommt sein eigenes Hintergrundbild. |

### Wie der Generator das baut

- Jedes verschobene Element packt er in eine **unsichtbare Gruppe mit Versatz**. Estuary selbst wird nicht umgeschrieben.
- Einzelne Menü-Buttons und Knöpfe baut er als eigene Bedienelemente nach und **verbindet die Pfeiltasten nach ihrer Lage**.
- Überlappen sich Hauptmenü und Widget-Bereich, gibt der Export einen Hinweis.

⚠️ Die Vorschau zeigt Estuary nur **angenähert**. Prüfe die Lage einmal in Kodi, besonders bei freien Anordnungen.

💡 **Rückgängig:** Oben rechts machen **↶ ↷** (oder Strg+Z / Strg+Y) Änderungen im Titan-Modus rückgängig und wiederholen sie.

<a id="k51"></a>

## 51. Fenster (Video-OSD & Co.) und Profi-Reiter

### Reiter 🪟 Fenster

Hier bearbeitest du die einzelnen Fenster des Skins – zum Beispiel das **Video-OSD** (das Bedienfeld, das beim Film mit OK/Enter erscheint), die Zeitleiste, Dialoge, die Musik-Ansicht oder die Einstellungen. Der Reiter braucht die geladene Estuary-Grundlage (Reiter 🧬 Basis); ist sie noch nicht da, bietet er den Download an.

| Bereich | Wofür |
|---|---|
| **Katalog** | Die wichtigsten Fenster mit Name und Beschreibung, in Gruppen (Video-Wiedergabe, Musik, Live-TV, Bibliothek, Dialoge, Einstellungen, Grundbausteine). Angezeigt wird nur, was deine Estuary-Version wirklich enthält. Neben dem Namen steht, ob du die Datei geändert hast (✎), Knöpfe ausgeblendet sind (👁) oder der Generator sie angepasst hat (●). |
| **👁 Bedienelemente: ausblenden, verschieben, vergrößern** | Listet alle Elemente der gewählten Datei mit fester Nummer, auch Gruppen und Knopfreihen. Beim Video-OSD tragen die bekannten Knöpfe ihren Namen (z.B. #601 Zurückspulen, #603 Stopp, #606 Vorspulen). Ein Haken blendet das Element aus (der Generator setzt `<visible>false</visible>`). Hinter **⚙** stellst du je Element ein: **Rechts/links und unten/oben** in Pixeln, **Größe** in Prozent, **Farbe**, **Reihenfolge** (↑ ↓ innerhalb der Geschwister) und **Sichtbarkeit je nach eigener Skin-Einstellung**. Verschieben und Vergrößern wirken über eine Animation nur auf die Darstellung, nicht auf die Bedien-Reihenfolge. Wer eine ganze Knopfreihe verschieben will, stellt die Gruppe ein (z.B. #201 beim Video-OSD). Der Rest der Datei bleibt unverändert und wird bei jedem Bauen neu angewendet. |
| **🖼 Vorschau (Skizze)** | Zeichnet die Elemente der Datei als Kästchen mit Nummer: Ausgeblendetes fehlt, Verschobenes steht am neuen Platz, Elemente mit Skin-Einstellung sind unten aufgelistet. Die Skizze ist **geschätzt** – Größen und Plätze, die Estuary über Bausteine festlegt, kennt der Generator nicht genau. Sie ersetzt keinen Test in Kodi. |
| **🖼 Bilder in diesem Fenster** | Listet alle Bilder, die die Datei verwendet (z.B. die Knopf-Symbole des Video-OSD), mit Vorschau, Maßen und den Nummern der Elemente. **🖼 Tauschen** ersetzt ein Bild durch ein eigenes (PNG oder JPG, max. 2,5 MB). Das neue Bild bekommt den Pfad des Originals; ist „Auf die Größe des Originals bringen“ an, wird es unter Beibehaltung des Seitenverhältnisses eingepasst (Rand transparent bzw. schwarz bei JPG). Es erscheint auch unter 🔧 Profi → Eigene Dateien, **↺** stellt das Original wieder her. Bilder anderer Formate (GIF, WebP) tauschst du über Eigene Dateien mit dem passenden Pfad. |
| **⚙ Eigene Skin-Einstellungen** | Lege Schalter an (z.B. „Stopp-Knopf im Video-OSD ausblenden“). Der Generator erzeugt dafür das Fenster **Skin-Optionen** (`xml/Custom_NUMMER_TitanOptionen.xml`) mit An/Aus-Knöpfen; **＋ Menüpunkt „Skin-Optionen“** legt einen Hauptmenüpunkt dafür an. Verknüpfe einen Schalter über ⚙ → Sichtbarkeit mit einem Element: Es ist ausgeblendet, solange der Schalter **An** steht. Kodi speichert die Schalter selbst (`Skin.ToggleSetting`, `Skin.HasSetting`), du musst den Skin dafür nicht neu bauen. Löschst du einen Schalter, löst der Generator die Verknüpfungen auf. |
| **Text von Hand ändern** | Der komplette XML-Text der Datei. **💾 Meine Fassung speichern** ersetzt die Datei **komplett** (ungültiges XML wird nicht gespeichert); spätere Änderungen im Generator wirken an dieser Datei dann nicht mehr, und das Ausblenden dort auch nicht. **↺ Zurück zur erzeugten** nimmt es zurück, **⤺ Estuary-Original** setzt die unveränderte Estuary-Datei ein, **🔍 Vergleich mit Estuary** zeigt jede Abweichung. |
| **📂 Alle weiteren Fenster-Dateien** | Alle übrigen `xml/`-Dateien von Estuary, mit Filter. Dateien außerhalb von `xml/` (Farben, Sprache, Bilder) erreichst du über den Reiter 🔧 Profi. |
| **＋ Neues eigenes Fenster** | Legt `xml/Custom_NUMMER_Name.xml` aus einer Vorlage an: Hinweis-Fenster, Schnellmenü mit vier Knöpfen oder Info-Anzeige zum laufenden Titel. Kodi hat für eigene Fenster die Nummern 1100–1199 vorgesehen; vergebene Nummern lehnt der Generator ab. Schrift, Farben und die weiße Grundfläche übernimmt er aus deinem Skin. Geöffnet wird das Fenster mit `ActivateWindow(NUMMER)`; **＋ Menüpunkt im Hauptmenü** legt dafür gleich einen Menüpunkt an. |

💡 Nach Änderungen an Farben, Menü oder Layout zeigt der Reiter beim nächsten Öffnen automatisch die neu erzeugte Fassung.

⚠️ Das Ausblenden, Verschieben, die Skin-Einstellungen und die Vorlagen sind im Generator mit einer Test-Fassung von Estuary geprüft, aber **noch nicht auf einem echten Kodi-Gerät**. Prüfe den Skin nach dem Bauen am besten zuerst in Kodi auf dem PC. Wenn Estuary in einer neueren Version Elemente umbaut, kann eine Nummer fehlen – der Generator meldet das dann beim Bauen als Warnung.

### Reiter 🔧 Profi

Der Reiter **🔧 Profi** ist für Kodi-Bastler. Alles hier wird bei jedem Bauen automatisch angewendet.

| Bereich | Wofür |
|---|---|
| **Vergleichen und von Hand ändern** | **▶ Skin berechnen und vergleichen** zeigt, welche Dateien der Generator an Estuary geändert hat (geänderte und neue). Tippe eine Datei an, sieh den Unterschied und ändere sie. **💾 Meine Fassung speichern** ersetzt die Datei **komplett** – spätere Änderungen im Generator wirken an dieser Datei dann nicht mehr. ● = vom Generator geändert, ✎ = von dir überschrieben, **↺ Zurück zur erzeugten** nimmt es zurück. |
| **Suchen und ersetzen** | Regeln wirken nach dem Umbau auf die Textdateien des Skins. Datei = Pfad oder Muster mit `*` (z.B. `xml/Home.xml` oder `xml/*.xml`), optional als Regex. **🔍 Treffer zählen** prüft die Regel vorher. Beispiel: Schriftart `font37` → `font30` in `xml/Home.xml`. |
| **Eigene Dateien** | Packe beliebige Dateien in den Skin – Bilder (nach `media/titan/`), Schriften, XML-Includes, Sounds. Den Pfad im Skin kannst du ändern. Eine gleichnamige Datei von Estuary wird ersetzt. |
| **Widgetreihen ausblenden** | **📋 Reihen aus Estuary lesen** zeigt die Reihen deiner Estuary-Version. Mit einem Häkchen blendest du einzelne aus. Gilt für Menüpunkte mit „Wie Estuary“. |
| **Profile** | Lege mehrere komplette Varianten unter eigenem Namen ab (z.B. „Wohnzimmer“, „Kiosk“, „Minimal“) und schalte mit einem Klick um. Sie liegen im Speicher dieses Browsers; zum Weitergeben nimmst du **📄 Datei**. |
| **Titan-Projekt exportieren/importieren** | Sichert das komplette Titan-Projekt (Layout, Bilder, Regeln, Dateien) als JSON – zum Weitergeben, Sichern oder für verschiedene Varianten. |

<a id="k52"></a>

## 52. Export und Installation

Im Reiter **📦 Export** prüft der Generator deine Einstellungen (fehlende Namen, Befehle, Pfade, überlappende Layout-Bereiche …) und wendet dabei auch deine Layout- und Profi-Einstellungen an. Mit **⚡ Skin-ZIP bauen** entsteht die Datei `skin.<name>-<version>.zip` (rund 5 MB).

1. ZIP auf das Kodi-Gerät kopieren.
2. **Einstellungen → Addons → Aus ZIP-Datei installieren**.
3. Kodi fragt, ob du zum neuen Skin wechseln willst → **Ja**. Danach „Änderung beibehalten?“ → **Ja**. Bestätigst du nicht, schaltet Kodi nach ein paar Sekunden von selbst zurück – so kann nichts schiefgehen.
4. **Zurück zu Estuary:** Einstellungen → Oberfläche → Skin → Skin → Estuary.

- **Update:** Version erhöhen (🧬 Basis), neu bauen, erneut installieren.
- **Skin-Einstellungen** (Einstellungen → Oberfläche → Skin → Konfigurieren) sind die von Estuary und werden für deinen Skin getrennt gespeichert.

**Wenn etwas hakt:**

| Problem | Lösung |
|---|---|
| Installation meldet fehlende Abhängigkeiten | Die gewählte Kodi-Version passt nicht zum Gerät – in 🧬 Basis ändern und neu bauen. |
| Eigener Menüpunkt tut nichts | Ist dein Addon installiert? Bei Seiten-Links „Direkt-Links erlauben“ prüfen. |
| Ein Widget bleibt leer | Inhalte in der Bibliothek vorhanden? Pfad korrekt? Leere Reihen blendet Kodi aus. |
| Hintergrund zu dunkel oder zu hell | Regler „Abdunkeln“ unter 🖼 Bilder & Schrift. |

<a id="k52a"></a>

## 52a. Andere Skins bearbeiten (Skin-Modus)

Der Titan-Modus kann mehr als Estuary: Du kannst die ZIP **jedes Kodi-Skins** laden (getestet mit **Bello 10**) und seine **Fenster** umbauen. Farben, Hauptmenü, Widgets und Layout sind dabei Sache des Skins selbst – dafür hat jeder Skin eigene Einstellungen in Kodi. Der Generator erkennt, wo die Fenster-Dateien liegen (Ordner `xml`, `720p`, `1080i` …), und lässt alles andere unverändert.

**So geht es:**

1. **⚡ Titan → 🧬 Basis → 🎭 „Skin-ZIP laden (Skin-Modus)“** und die ZIP des Skins wählen (z. B. den Ordner aus `addons` deiner Kodi-Installation als ZIP packen oder die Skin-ZIP aus dem Netz). Lädst du über „📦 Eigene Skin-ZIP“ einen Skin, der nicht wie Estuary aufgebaut ist, schaltet der Generator von selbst in den Skin-Modus.
2. Oben rechts bleiben vier Reiter: **🧬 Basis · 🪟 Fenster · 🔧 Profi · 📦 Export**. Links siehst du Name, Version, Autor, Lizenz, Auflösung und die Zusatz-Addons des Skins.
3. **🧬 Basis:** Name, Version und Autor der Anpassung festlegen. Der neue Skin bekommt eine **neue ID** (z. B. `skin.bello10mod`), damit er neben dem Original installiert werden kann.
4. **🪟 Fenster:** Wie in Kapitel 51 – Knöpfe ausblenden, verschieben, vergrößern, umfärben, Bilder tauschen, XML ändern, neue Fenster, eigene Skin-Schalter.
5. **📦 Export:** **⚡ Skin-ZIP bauen** erzeugt `skin.<neue-id>-<version>.zip`. Installation wie in Kapitel 52.

**Was anders ist als bei Estuary:**

| Thema | Im Skin-Modus |
|---|---|
| **Bausteine (Includes)** | Fremde Skins legen die Knöpfe ihrer Fenster meist in Include-Dateien (bei Bello z. B. `IncludesOSD.xml`). Der Generator setzt ein Fenster mit allen Bausteinen zusammen und zeigt jedes Element mit dem Zusatz **„in Datei …“**. Ausblenden und Verschieben wirken dort, wo das Element wirklich steht – also **in allen Fenstern, die denselben Baustein benutzen**. |
| **Bedingte Varianten** | Hat ein Fenster mehrere Stile (z. B. Bello-OSD „Stil 1/Stil 2“), werden alle Varianten aufgelistet; die Skizze zeigt nur die erste. |
| **Elemente mit berechneter Nummer** | Kommt die Nummer eines Elements erst aus einem Parameter des Bausteins, kann es nicht einzeln geändert werden (es fehlt in der Liste). |
| **Fensternummern** | Neue Fenster und das Fenster „Skin-Optionen“ bekommen eine freie Nummer (1100–1199), die der Skin nicht schon benutzt. Die Größen der Vorlagen passen sich der Auflösung des Skins an. |
| **Menüpunkt für ein neues Fenster** | Das Hauptmenü gehört dem Skin. Lege den Menüpunkt dort selbst an (bei vielen Skins: Skin-Einstellungen → Hauptmenü bearbeiten) mit dem Befehl `ActivateWindow(NUMMER)`. |
| **Einstellungen und Menü des Originals** | Wegen der neuen ID startet der Skin mit seinen Standardwerten; Einstellungen und selbst gebautes Hauptmenü des Originals werden nicht übernommen. |
| **Zwei Projekte** | Dein Estuary-Projekt und dein Skin-Projekt bleiben getrennt gespeichert. Mit **↩ Zurück zum Estuary-Modus** bzw. **↪ Weiter mit „…“** wechselst du hin und her; lädst du einen anderen Skin, beginnt das Skin-Projekt neu (der Generator fragt vorher). |

**Lizenz beachten:** Ein veränderter Skin bleibt eine Abwandlung des Originals – es gilt dessen Lizenz (Bello z. B. CC BY-NC-SA: Namensnennung, nicht kommerziell, Weitergabe unter gleichen Bedingungen). Der Generator trägt den Original-Autor in die `addon.xml` ein, legt `ANPASSUNG.txt` bei, ergänzt `changelog.txt` und lässt die `LICENSE.txt` unverändert. Im Reiter 📦 Export stehen die Lizenz und die nötigen Zusatz-Addons als Hinweis.

---

---

# Teil H – Fremd-Addon, Live-Browser und Kontextmenü

<a id="k53"></a>

## 53. Ein vorhandenes Addon einbinden

Du hast schon ein Addon – etwa eines, das du selbst geschrieben hast – und willst es in einem eigenen Menü zeigen? Dann bindest du seine ZIP ein, statt alles neu zu bauen.

**So geht's:**

1. Öffne **📦 Fremd-Addon** in der Kopfzeile (oder in Bereich 5 · Addon-Bilder & Dateien → **🧩 Fremd-Addon einbinden (ZIP)**).
2. **＋ Addon-ZIP wählen.** Mehrere ZIPs sind möglich, z.B. das Addon und ein benötigtes Modul. Die Reihenfolge ist die der Einrichtung.
3. Der Generator liest das Addon und zeigt eine Karte: Name, ID, Version, Größe, Art (Plugin, Script oder Sonstiges) und was es **braucht** (Abhängigkeiten).
4. Lege fest, welche Menüeinträge du übernimmst und in welchem Stil sie erscheinen ([Kapitel 54](#k54)).
5. Exportiere dein Addon wie gewohnt und installiere es in Kodi.

**Was in Kodi passiert:**

- Die ZIP liegt **unverändert** im Ordner `resources/bundled/` deines Addons.
- Beim Start wird sie nach `special://home/addons/` **entpackt und eingeschaltet**. Fehlende Abhängigkeiten stößt das Addon zur Installation an. Das erledigt der Startcode des Addons zusammen mit einem kleinen Hintergrunddienst (`service.py`).
- Dein Menü ist danach die Oberfläche für das Fremd-Addon.

⚠️ **Die ZIP liegt nur im Browser-Speicher dieses Geräts.** Beim Projekt-Export als JSON ist sie nicht enthalten. Auf einem neuen Gerät oder nach dem Löschen des Browser-Speichers wählst du sie erneut aus. ✔ Prüfen warnt dich davor.

⚠️ **Lizenz:** Das Fremd-Addon behält seine eigene Lizenz. Gib dein Addon nur weiter, wenn du das eingebundene Addon weitergeben darfst.

<a id="k54"></a>

## 54. Menüeinträge und Stile

Der Generator liest den Code des Fremd-Addons und schlägt Einträge vor, die sich als Button eignen: Ordner, Wiedergabe-Adressen, Plugin-Befehle und Scripts.

| Angabe | Bedeutung |
|---|---|
| **Parameter-Name** (z.B. `mode` oder `action`) | Bestimmt die Adressen neuer Einträge, z.B. `plugin://plugin.video.xyz/?mode=search`. |
| **Eintrag** | Beschriftung, Art und Adresse. Nur Einträge mit Beschriftung werden übernommen. |
| **Nicht als Button geeignet** | Manche Aktionen brauchen Angaben aus der vorherigen Liste (z.B. welches Video). Der Generator listet sie auf, bietet sie aber nicht als Button an. |
| **Rubriken** | Steht im Addon eine feste Liste (z.B. `CATEGORIES = {"Politik": …}`) oder eine Schleife, die daraus Menüeinträge baut, übernimmt der Generator jede Rubrik **mit allen Parametern** als eigenen Eintrag (z.B. `?mode=list&feed=…&title=Politik&page=1`). Das ist eine Vermutung aus dem Code – prüfe die Liste vor dem Übernehmen. |
| **Weitere erkannte Muster** | Listen aus Tupeln (`MENU = [("Neu", "new", "icon.png"), …]`, auch mit `for name, mode, icon in MENU`), Listen aus Wörterbüchern mit festen Werten (mindestens zwei, z.B. `{'title': 'Politik', 'mode': 'list', 'feed': '…'}`), Verteiler-Tabellen (`ROUTES = {'live': show_live, …}`; liest die Funktion weitere Parameter, gilt der Pfad als „nicht als Button geeignet“), Pfade mit `@plugin.route('/movies')` (ohne Platzhalter) und **Menüs aus JSON-Dateien des Addons** (Listen von Objekten mit Titel und `url`, oder mit dem Modus-Schlüssel, optional mit Unterobjekt `params`). Titel und Bild-Schlüssel (`icon`, `thumb` …) werden nicht als Parameter übernommen. Auch hier gilt: Vermutung aus dem Code, bitte prüfen. |

**Stile** – so erscheinen die Einträge in deinem Menü:

| Stil | Aussehen |
|---|---|
| 📂 **Live-Browser (empfohlen)** | Eine Liste, in der Ordner aufgehen, Zurück eine Ebene hochgeht und Videos direkt starten (siehe [Kapitel 55](#k55)). |
| ▦ Kachel-Raster | Einträge als Kacheln |
| ☰ Liste | Einträge als Liste |
| 🧮 Taschenrechner | Tasten wie ein Taschenrechner |
| 🐧 Linux-Desktop | Symbole wie auf einem Desktop |

Bei den Button-Stilen wird die **Browser-Seite automatisch mit angelegt**, damit Ordner in deinem Skin aufgehen.

**Kodierte Adressen:** Manche Addons und Kodis Favoriten schreiben Adressen verschlüsselt, z.B. `feed=https%3a%2f%2f…` oder mit `&amp;` statt `&`. Der Generator entschlüsselt solche Adressen beim Einlesen und bringt sie in eine einheitliche Form; das fertige Addon macht dasselbe beim Öffnen von Ordnern, Direkt-Links und beim Vergleichen mit Favoriten. Dadurch greifen Einträge mit mehreren Parametern, und Favoriten werden auch dann wiedererkannt, wenn Groß- und Kleinschreibung der Kodierung abweicht.

<a id="k55"></a>

## 55. Der Live-Browser 📂

Der Live-Browser zeigt den Inhalt eines Addons **in deinem eigenen Menü** – Kodis Ordneransicht taucht nicht auf.

| Bedienung | Was passiert |
|---|---|
| Ordner anklicken | Der Inhalt erscheint in der Liste. |
| **Zurück** | Eine Ebene hoch. Auf der obersten Ebene geht es wie gewohnt weiter (Seite zurück oder Addon verlassen). |
| Video anklicken | Es startet sofort. |
| Langes Drücken, Rechtsklick, Taste C | Kontextmenü mit Favoriten ([Kapitel 57](#k57)). |

**Aufbau:** Die Browser-Seite enthält eine Liste „Automatisch aus Kodi“. Das Addon fragt dafür Kodis `Files.GetDirectory` ab und füllt die Liste mit Titel, Bild und Beschreibung. Ob ein Eintrag ein **Ordner** oder ein **Video** ist, liest es aus der Antwort. Fehlt diese Angabe (ältere Kodi-Version), behandelt das Addon den Eintrag als abspielbar. Für eigene XML-Zeilen setzt der Browser die Fenster-Eigenschaften `kfe.title` (aktueller Ordner) und `kfe.depth` (Tiefe) sowie je Eintrag `kfe.plot` (Beschreibung).

**Jeder Button kann Ordner öffnen:** Wähle die Aktion **Ordner im eigenen Browser öffnen (bleibt im Skin)** und trage einen Kodi-Pfad ein, z.B. `plugin://plugin.video.xyz/`.

💡 Wer Kodis Originalansicht braucht, nutzt im Kontextmenü **In Kodis Ansicht öffnen**.

<a id="k56"></a>

## 56. Abhängigkeiten automatisch eintragen

Kodi installiert ein Python-Modul nur, wenn es in der **`addon.xml` des Addons als `<import>`** steht. Fehlt der Eintrag, kommt beim Start `No module named 'bs4'` oder Ähnliches. Der Generator übernimmt das:

- Er liest die Python-Dateien deines Addons und der eingebundenen Fremd-Addons und erkennt die verwendeten Module.
- Er trägt die passenden Kodi-Module in die `addon.xml` deines Addons ein. Eigene Module (eine Datei `name.py` oder ein Ordner mit `__init__.py`) brauchen keinen Eintrag.
- Die Abhängigkeiten, die das Fremd-Addon selbst in seiner `addon.xml` nennt, werden ebenfalls berücksichtigt. Das Fremd-Addon selbst wird nicht doppelt eingetragen.

| Im Code | Kodi-Modul |
|---|---|
| `bs4` | `script.module.beautifulsoup4` |
| `soupsieve` | `script.module.soupsieve` |
| `requests` | `script.module.requests` |
| `feedparser` | `script.module.feedparser` |
| `six`, `simplejson`, `dateutil`, `html5lib`, `chardet`, `idna`, `urllib3`, `certifi` | `script.module.<name>` |
| `routing`, `xmltodict`, `inputstreamhelper`, `pytz`, `arrow`, `m3u8`, `websocket`, `pyxbmct`, `unidecode`, `simplecache` | `script.module.<name>` |
| `kodi_six`, `yaml`, `Cryptodome`, `socks` | `script.module.kodi-six`, `script.module.pyyaml`, `script.module.pycryptodome`, `script.module.pysocks` |

Unter **⚙ Erweiterte Addon-Angaben → Zusätzliche Abhängigkeiten** ([Kapitel 4](#k4)) siehst du, was automatisch dazukommt, und kannst eigene ergänzen.

<a id="k57"></a>

## 57. Kontextmenü und Favoriten 🖱

Kodi blendet sein eigenes Kontextmenü in Addon-Fenstern aus. Darum bringt das fertige Addon ein **eigenes** mit.

**Öffnen:** langes Drücken (Touch), Rechtsklick oder **Taste C**.

| Eintrag | Menü zeigt |
|---|---|
| **Ordner im Live-Browser** | Öffnen · Als Favorit speichern · In Kodis Ansicht öffnen · Beschreibung anzeigen |
| **Video** | Abspielen · Zur Wiedergabeliste hinzufügen · Als Favorit speichern |
| **Artikel** | Ausführen (Kodi kann Artikel nicht als Favorit speichern) |
| **Button** | Ausführen · bei Seiten und Ordnern zusätzlich Als Favorit speichern |
| **Immer** | Dieses Menü als Favorit speichern · Kodi-Favoriten öffnen · Einstellungen dieses Addons (falls vorhanden) |
| **Schon gespeicherter Favorit** | „aus Favoriten entfernen“ statt „speichern“ |

**Favoriten:** Ein gespeicherter **Ordner** öffnet sich später direkt in **deinem** Skin an genau dieser Stelle. Ein gespeicherter **Menüpunkt** springt auf die Seite (siehe [Kapitel 38](#k38)). Die Favoriten findest du in Kodi unter **Favoriten**. Voraussetzung für Ordner-Favoriten: Die Browser-Seite muss im Addon vorhanden sein.

**Abschalten:** 🛠 Modding → 🎛 Schalter → **🖱 Kontextmenü** (Standard: an).

**Erweitern:** Mit `kontextmenue(window, info)` in `custom.py` ([Kapitel 58](#k58)).

### Langes Drücken im Hauptmenü

Kodi macht aus langem Drücken einen **Rechtsklick**. Wenn kein Element den Rechtsklick annimmt, macht Kodi daraus ein „Zurück“ und schließt das Fenster. Damit das Addon nicht beim langen Drücken verlassen wird, wartet es bei einem „Zurück“ **ohne Tastencode** kurz (rund 0,4 Sekunden). Folgt direkt ein Rechtsklick, öffnet es das Kontextmenü und verwirft das „Zurück“. Echte Zurück-Tasten (Fernbedienung, Esc, Handy-App) funktionieren unverändert.

⚠️ Ein künstliches „Zurück“ ohne Tastencode, etwa per JSON-RPC, wird dadurch um rund 0,4 Sekunden verzögert.

<a id="k58"></a>

## 58. Eigene Einträge in custom.py

Mit eingebundenem Fremd-Addon legt der Generator `resources/lib/custom.py` an (im 💻 Editor sichtbar). Der Bereich „EINGEBUNDENE ADDONS“ ist **dein Bereich**:

| Teil | Zweck |
|---|---|
| `MENUE` | Liste deiner Einträge: `(Beschriftung, Art, Adresse)` |
| `befehl(art, ziel, fenster)` | Führt einen Eintrag aus |
| `menue(window)` | Zeigt die Einträge als Auswahl |
| `eintrag_N_…` | Je Eintrag eine Funktion, die du als Aktion **Python-Funktion** verwenden kannst |

**Arten** in `MENUE`:

| Art | Wirkung |
|---|---|
| `'ordner'` | Liste im eigenen Browser öffnen (bleibt im Skin) |
| `'abspielen'` | Adresse direkt abspielen |
| `'plugin'` | Plugin-Befehl ausführen (`RunPlugin`) |
| `'addon'` | Addon starten (Adresse = Addon-ID) |

**Rückgabewerte** der Funktionen: `browse:<Pfad>`, `page:<ID>`, `back`, `home`, `exit` oder ein Kodi-Befehl (siehe [Kapitel 37](#k37)).

**Kontextmenü erweitern:**

```python
def kontextmenue(window, info):
    # info: page, control, label, path, folder des gewählten Eintrags
    return [
        ('Im Browser suchen', 'browse:plugin://plugin.video.xyz/?mode=search'),
        ('Zur Startseite', 'home'),
    ]
```

Die zurückgegebenen Einträge erscheinen im Kontextmenü, die Rückgabe wirkt wie bei einer Aktion.

---

# Teil I – Lizenz

<a id="k59"></a>

## 59. Lizenz und wie es weitergeht

Estuary stammt von **phil65 und Team Kodi**: der Code steht unter der **GPL-2.0**, die Grafiken unter **CC BY-SA 4.0**. Ein daraus gebauter Skin steht deshalb automatisch unter denselben freien Lizenzen. Die Lizenztexte (`LICENSE.txt`) und ein Hinweis auf die Grundlage (`TITAN.txt`) liegen in jeder Skin-ZIP. Du darfst deinen Skin weitergeben – er muss dann aber frei bleiben und Estuary nennen.

Der **Generator selbst** bleibt unter der IT('s) Possible Freeware-Lizenz geschützt ([LICENSE](LICENSE)).

**Fremd-Addons behalten ihre eigene Lizenz.** Bindest du ein Addon als ZIP ein, wird es unverändert mitgeliefert. Gib solche Addons nur weiter, wenn die Lizenz des Addons das erlaubt.

**Als Nächstes – Stufe B:** eigene Fenster von Grund auf, angefangen mit der Startseite aus dem Designer als echte Skin-Startseite.

---

```text
Kodi Video-Addon Generator v9.0 Pro – Copyright (c) 2026 Team IT('s) Possible
Handbuch · Stand 2026.10.23. Alle Rechte vorbehalten.

Kostenlos für die Kodi-Community, aber nicht Open Source. Ohne schriftliche Erlaubnis
verboten: Verkaufen, Vermieten oder Anbieten gegen Bezahlung, Einbau von Werbung,
Bereitstellen auf anderen Seiten oder in App-Stores, Verbreiten veränderter Fassungen
und das Entfernen von Copyright-Hinweisen. Die mit dem Generator gebauten Addons
gehören ihren Erstellern.

Die Nutzung erfolgt auf eigene Gefahr, ohne Gewähr und ohne Haftung.
Es gilt die IT('s) Possible Freeware-Lizenz (Datei LICENSE).
```
