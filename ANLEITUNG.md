# 📖 Anleitung – Kodi Skin Generator

So baust du dein eigenes Kodi-Menü in wenigen Minuten. Du brauchst keine Programmierkenntnisse.

---

## Bevor du startest

- Öffne die Datei `kodi_skin_generator_v6.html` per Doppelklick in deinem Browser (Chrome, Edge, Firefox oder Safari).
- Du brauchst eine Internetverbindung, damit das Tool seine Bausteine laden kann.
- Dein Projekt wird automatisch im Browser gemerkt. Für ein sicheres Backup nutze **💾 Speichern**.

**Wichtig vorab: Skin oder Addon?**
Wenn du zum ersten Mal etwas baust, wähle **🔌 Addon**. Es ist der einfachste Weg und funktioniert zuverlässig. Ein **🎨 Skin** ersetzt die komplette Kodi-Oberfläche und enthält nur die Seiten, die du selbst baust.

---

## Schritt 1 – Projekt benennen

Links unter **1 · Projekt**:

1. **Name** eingeben, z.B. „Mein Streaming Hub“. Die technische ID wird automatisch erzeugt.
2. **Skin** oder **Addon** wählen.
3. Autor, Version, Kurzbeschreibung und Lizenz ausfüllen. Die Beschreibung erscheint später in Kodi.
4. Die **Kodi-Version** auswählen (19 Matrix, 20 Nexus oder 21 Omega). Du findest sie in Kodi unter *Einstellungen → System → Systeminformationen*.

**Tipp:** Oben im Menü findest du unter **📂 Vorlagen** fertige Startpunkte (Streaming-Hub, Live TV, Musik-Player). Das spart Arbeit.

---

## Schritt 2 – Elemente hinzufügen

Unter **2 · Hinzufügen**:

| Element | Wofür |
|---|---|
| ➕ **Button** | Klickbarer Menüpunkt |
| 🔤 **Text** | Überschrift oder Beschriftung |
| 🖼 **Poster** | Platzhalter für Bilder (nur im Skin sichtbar) |
| ⬛ **Fläche** | Farbiger Hintergrundblock (nur im Skin sichtbar) |

Ein neues Element erscheint in der Mitte der Leinwand.

- **Verschieben:** mit Finger oder Maus ziehen.
- **Größe ändern:** an der weißen Ecke unten rechts ziehen.
- **Genau einstellen:** rechts bei *Eigenschaften* Position und Größe eintippen.
- **Löschen:** 🗑 rechts oder Entf-Taste. **Duplizieren:** ⧉ oder Strg+D.
- **Fehler gemacht?** **↩ Rückgängig** oder Strg+Z.

---

## Schritt 3 – Buttons mit Aktionen belegen

Klicke einen Button an. Rechts erscheint der Kasten **⚡ Was passiert beim Klick?**

### Der einfache Weg: Befehlsliste

1. Auf **📚 Aus Befehlsliste wählen** tippen.
2. Oben ein Wort eingeben (z.B. „Filme“, „Lautstärke“, „Neustart“) oder eine Kategorie wählen.
3. Bei dem passenden Eintrag auf **Einsetzen** tippen. Beschriftung und Symbol werden automatisch gesetzt.
4. Du hast keinen Button markiert? Dann tippe auf **＋ Neuer Button**, es entsteht ein fertiger Button mit dem Befehl.

### Weitere Aktionen im Auswahlmenü

| Aktion | Was du eintragen musst |
|---|---|
| Andere Seite öffnen | Die Zielseite aus der Liste wählen |
| Anderes Addon öffnen | Adresse, z.B. `plugin://plugin.video.youtube/` |
| Video / Stream abspielen | Internet-Adresse (`https://…`) oder Dateipfad |
| Play/Pause, Nächster Titel, Stopp, Zurück, Einstellungen, Kodi beenden | nichts, funktioniert sofort |
| Kodi-Befehl | Befehl aus der Liste oder selbst eingetragen (für Fortgeschrittene) |

**Achtung bei Platzhaltern:** Manche Befehle brauchen noch deine Angaben, z.B. `RunAddon(DEINE.ADDON.ID)` oder `PlayMedia(https://)`. Ersetze den Platzhalter im Feld unter der Aktion. Die Funktion **✔ Prüfen** warnt dich, wenn einer übrig ist.

---

## Schritt 4 – Mehrere Seiten bauen

Über der Leinwand siehst du die Seiten-Leiste.

1. **＋ Seite** legt eine neue Seite an (mit Titel und Zurück-Button).
2. Auf der Startseite einen Button erstellen und als Aktion **Andere Seite öffnen** wählen.
3. **✏ Umbenennen**, **⧉ Diese Seite duplizieren** (links bei Werkzeuge) und **🗑 Seite löschen** helfen beim Aufräumen.

Jede Seite sollte einen **Zurück**-Button haben, sonst kommst du nicht mehr zurück.

---

## Schritt 5 – Design anpassen

Unter **3 · Design**:

- **Farbthemen** mit einem Tipp übernehmen.
- Eigene Farben für **Buttons**, **Fokus** (der Button, auf dem die Fernbedienung gerade steht) und **Hintergrund** wählen.
- **🖼 Hintergrundbild** wählen. Es wird passend zugeschnitten. Mit ✖ entfernst du es wieder.

Unter **4 · Werkzeuge**:

- **📐 Buttons mittig untereinander ordnen** macht in einem Klick eine saubere Liste.
- **📏 Alle Buttons so groß wie markierter** vereinheitlicht die Größe.

---

## Schritt 6 – Icon, Fanart und Screenshots

Unter **5 · Bilder & Dateien**:

| Bild | Wofür | Tipp |
|---|---|---|
| **Icon** | kleines Bild in der Addon-Liste | möglichst quadratisch |
| **Fanart** | großes Hintergrundbild in der Addon-Info | Querformat 16:9 |
| **Screenshots** | Bilder in der Addon-Beschreibung | bis zu 8 Stück |

Du musst nichts weiter tun: Die Bilder werden automatisch in die ZIP gepackt und in der `addon.xml` eingetragen. Wählst du nichts aus, erzeugt das Tool ein einfaches Icon und Fanart für dich.

---

## Schritt 7 – Eigene Ordner und Dateien (optional)

Über **📁 Ordner & Dateien verwalten**:

1. **Ordner anlegen:** Namen eingeben, z.B. `resources/lib`, dann **＋ Ordner**.
2. **Dateien hinzufügen:** Zielordner im Auswahlfeld wählen, dann **＋ Dateien hinzufügen**. Maximal 4 MB pro Datei.
3. **Textdatei schreiben:** unter „📝 Textdatei selbst schreiben“ Namen und Inhalt eintragen, z.B. eine `settings.xml`.
4. Mit **✖** entfernst du einzelne Einträge. Beim Löschen eines Ordners verschwindet auch sein Inhalt.

Die `addon.xml` kannst du nicht selbst hinzufügen, sie wird immer automatisch erzeugt.

---

## Schritt 8 – Testen, prüfen, exportieren

1. **▶ Testen:** Im Testmodus kannst du Buttons anklicken. Seitenwechsel funktionieren, andere Aktionen zeigen den Kodi-Befehl an. Mit **✏ Bearbeiten** geht es zurück.
2. **✔ Prüfen:** Das Tool listet auf, was noch fehlt. ⚠️ sind echte Probleme, 💡 sind Hinweise.
3. **&lt;/&gt; Code:** Hier siehst du die erzeugten Dateien, z.B. die `addon.xml`. Nur für Neugierige.
4. **⬇ ZIP exportieren:** Die ZIP-Datei wird heruntergeladen. Bei Warnungen fragt das Tool vorher nach.

---

## Schritt 9 – In Kodi installieren

1. ZIP-Datei auf das Gerät kopieren, auf dem Kodi läuft.
2. In Kodi: **Einstellungen → System → Addons → Unbekannte Quellen** erlauben (einmalig).
3. **Einstellungen → Addons → Aus ZIP-Datei installieren**, die ZIP auswählen.
4. **Addon:** zu finden unter *Addons → Video-Addons*.
5. **Skin:** *Einstellungen → Oberfläche → Skin* und deinen Skin auswählen. Kodi fragt, ob du den Skin behalten willst. Wenn etwas nicht stimmt, wartet einfach ab, dann springt Kodi zum alten Skin zurück.

---

## Projekt sichern und weitermachen

- **💾 Speichern** lädt eine JSON-Datei mit deinem kompletten Projekt herunter (inklusive Bildern und Dateien).
- **📥 Laden** holt es wieder zurück, auch auf einem anderen Gerät.
- Mach vor größeren Änderungen eine Sicherung.

---

## Tastenkürzel

| Taste | Wirkung |
|---|---|
| Pfeiltasten | Element um 20 Pixel verschieben |
| Umschalt + Pfeiltasten | Element um 100 Pixel verschieben |
| Entf | Element löschen |
| Strg + D | Element duplizieren |
| Strg + Z | Rückgängig |

---

## Häufige Fragen

**Warum sehe ich meine Emojis in Kodi nicht?**
Viele Kodi-Schriften haben keine Emojis. Sie sind nur in der Vorschau im Tool sichtbar. Die Beschriftung funktioniert immer.

**Meine Poster und Flächen fehlen im Addon.**
Das ist normal. Ein Addon zeigt nur Menü-Einträge. Poster und Flächen gibt es nur im Skin.

**Ein Button macht in Kodi nichts.**
Prüfe die Aktion mit **✔ Prüfen**. Bei „Live TV“ oder „TV-Programm“ muss ein PVR-Addon installiert sein, bei „YouTube starten“ das YouTube-Addon.

**Das Tool meldet „ZIP-Bibliothek nicht geladen“.**
Du bist vermutlich offline. Verbinde dich mit dem Internet und lade die Seite neu.

**Meine Bilder verschwinden nach dem Neuladen.**
Der Browser-Speicher ist voll. Nutze **💾 Speichern** als Backup und **📥 Laden**, um weiterzumachen. Kleinere Bilder helfen.

**Ich habe einen Fehler gemacht, ohne es zu merken.**
Nutze **↩ Rückgängig**. Für Seiten und Elemente funktioniert das mehrfach. Bilder, Dateien und Projekteinstellungen sind davon ausgenommen.

**Wo finde ich weitere Kodi-Befehle?**
Im Kodi-Wiki unter „List of built-in functions“. Trage sie bei der Aktion **Kodi-Befehl** ein.
