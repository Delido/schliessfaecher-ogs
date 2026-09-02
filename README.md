# Schließfächer OGS

Eine einzelne HTML-Datei zur Verwaltung von Schließfächern in einer Offenen Ganztagsschule
(OGS), Kita oder einem Verein. Doppelklick genügt – keine Installation, kein Server,
kein Internet.

Entstanden als Ersatz für eine gewachsene Word-Tabelle: Die häufigste Frage im Alltag ist
*„Welches Fach ist noch frei?"*, und die sollte sich mit einem Blick beantworten lassen.

## Auf einen Blick

- **Schrankansicht** – die Fächer stehen genau wie am echten Schrank (3 Spalten, 4 Reihen),
  grün = frei, orange = belegt, grau = defekt
- **Suche und Filter** nach Name, Fach-, Schloss- oder Schranknummer
- **Listenansicht** als sortierbare Tabelle
- **Auswertung** mit Belegung pro Gruppe, freien Plätzen und offenen Punkten
- **Schlüsselverwaltung** als Soll/Ist – auch drei, vier oder fünf Schlüssel pro Fach
- **Verlauf**: wer hatte das Fach vorher? (hilfreich, wenn ein Schlüssel fehlt)
- **Defekte Fächer** zählen nicht als frei
- **Personal-Fächer** (Ersatzschlüssel, Technik) getrennt von den Kindern gezählt
- **Rückgängig** für die letzten 20 Schritte, auch für gelöschte Schränke
- **CSV-Export** für Excel, **Druckansicht** für den Aushang
- Helle und dunkle Ansicht, Hilfe direkt in der App

## Loslegen

1. `Schliessfaecher.html` herunterladen und per Doppelklick öffnen
2. Beim ersten Start eine der drei Optionen wählen – zum Ausprobieren
   `beispieldaten.json` über **Sicherungskopie einlesen** laden
3. Über **Datei verbinden** eine eigene Datendatei anlegen; ab dann wird
   jede Änderung automatisch dort gespeichert

## Wo liegen die Daten?

Die HTML-Datei ist **nur das Programm** und enthält keine Fächer.

Die Daten liegen in einer JSON-Datei neben der HTML (z. B. `Schliessfaecher_Daten.json`)
und zusätzlich im Browser. Beim Speichern nutzt die App die File System Access API –
verfügbar in Chrome und Edge. In Firefox funktioniert die App ebenfalls, dort muss
man die Sicherungskopien allerdings von Hand speichern und laden.

**Hinweis zum Browser:** Wird die Datei per Doppelklick geöffnet (`file://`), darf der
Browser die Schreiberlaubnis aus Sicherheitsgründen nicht dauerhaft merken – sie muss
nach jedem Browserstart einmal erteilt werden. Bis dahin läuft die App im Nur-Ansicht-Modus,
damit keine Änderungen verloren gehen. Wer das vermeiden will, liefert die Datei über
einen lokalen Webserver aus.

## Datenschutz

Dieses Repository enthält **keine echten Personendaten**. Die mitgelieferte
`beispieldaten.json` ist frei erfunden.

Die App verarbeitet Namen von Kindern – also personenbezogene Daten. Sie werden
ausschließlich lokal gespeichert und niemals irgendwohin übertragen; die App hat keinerlei
Netzwerkfunktion. Wer sie einsetzt, sollte dennoch die eigenen Datenschutzvorgaben prüfen
und die Datendateien nicht versehentlich in ein öffentliches Repository legen –
die beiliegende `.gitignore` verhindert das für die üblichen Dateinamen.

## Technik

Reines HTML, CSS und JavaScript ohne Abhängigkeiten oder Build-Schritt. Eine Datei,
rund 90 KB. Schriften kommen von Google Fonts, mit Systemschriften als Rückfallebene –
offline funktioniert alles, es sieht nur etwas anders aus.

## Lizenz

MIT – siehe [LICENSE](LICENSE).
