# Schließfächer OGS

Eine einzelne HTML-Datei zur Verwaltung von Schließfächern in einer Offenen Ganztagsschule
(OGS), Kita oder einem Verein. Doppelklick genügt – keine Installation, kein Server,
kein Internet.

Entstanden als Ersatz für eine gewachsene Word-Tabelle: Die häufigste Frage im Alltag ist
*„Welches Fach ist noch frei?"*, und die sollte sich mit einem Blick beantworten lassen.

## Herunterladen

**[⬇ Schliessfaecher.html – Version 1.0](https://github.com/Delido/schliessfaecher-ogs/releases/latest/download/Schliessfaecher.html)**

Das ist die komplette Anwendung: eine Datei, Doppelklick genügt. Alles andere in diesem
Repository ist Quelltext und Dokumentation und wird nicht benötigt.

Zum Ausprobieren zusätzlich
[beispieldaten.json](https://github.com/Delido/schliessfaecher-ogs/releases/latest/download/beispieldaten.json)
(84 erfundene Fächer) – in der App über *Mehr → Sicherung laden* einlesen.

📖 **Anleitung: <https://delido.github.io/schliessfaecher-ogs/>**

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

1. Datei per Doppelklick öffnen
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
ausschließlich lokal gespeichert und niemals irgendwohin übertragen.

**Die Seite stellt keine einzige Verbindung nach außen her.** Keine Schriften von Google
Fonts, keine CDNs, keine Analyse-Skripte, kein `fetch`. Es werden ausschließlich
Systemschriften verwendet. Damit entsteht auch keine Übertragung der IP-Adresse an Dritte,
die nach der Rechtsprechung zu Google Fonts (LG München I, 3 O 17493/20) problematisch wäre.
Die App funktioniert vollständig offline.

Wer sie einsetzt, sollte dennoch die eigenen Datenschutzvorgaben prüfen und die Datendateien
nicht versehentlich in ein öffentliches Repository legen – die beiliegende `.gitignore`
verhindert das für die üblichen Dateinamen.

## Technik

Reines HTML, CSS und JavaScript ohne Abhängigkeiten, Build-Schritt oder externe
Ressourcen. Eine Datei, rund 90 KB, komplett offline lauffähig.

## Lizenz

MIT – siehe [LICENSE](LICENSE).
