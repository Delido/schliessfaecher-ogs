# Technik

## Aufbau

Eine einzelne HTML-Datei, rund 90 KB, ohne Abhängigkeiten und ohne Build-Schritt:

- **HTML** für die Struktur
- **CSS** mit Custom Properties für Farben, helle und dunkle Ansicht
- **JavaScript** ohne Framework – kein React, kein jQuery, nichts nachzuladen

Es gibt keine externen Ressourcen. Die Datei lässt sich kopieren, per Mail verschicken
oder auf einen USB-Stick legen und läuft überall.

## Datenformat

Die Daten liegen als JSON-Array vor. Ein Fach sieht so aus:

```json
{
  "id": "100001",
  "gruppe": "Bärengruppe",
  "schrank": "1002",
  "fach": "100001",
  "schloss": "50001",
  "name": "Kind 01",
  "defekt": false,
  "personal": false,
  "heim": "",
  "schlSoll": 2,
  "schlDa": 2,
  "notiz": "",
  "verlauf": [
    { "name": "Kind 02", "von": "2025-08-01", "bis": "2026-07-31" }
  ]
}
```

Beim Laden werden fehlende Felder automatisch ergänzt, ältere Sicherungen bleiben also
lesbar.

## Speicherung

| Technik | Wofür |
|---|---|
| File System Access API | Schreiben in die JSON-Datei (Chrome, Edge) |
| `localStorage` | zweite Kopie im Browser |
| IndexedDB | Verweis auf die Datei, damit die Freigabe Neustarts überlebt |

## Über einen Webserver ausliefern {#webserver}

Wer die wiederkehrende Freigabe vermeiden will, liefert die Datei lokal aus. Unter
`http://localhost` speichert der Browser die Erlaubnis dauerhaft.

Mit Python (auf den meisten Rechnern vorhanden):

```bat
cd Pfad\zum\Ordner
python -m http.server 8000
```

Danach im Browser `http://localhost:8000/Schliessfaecher.html` öffnen.

!!! note
    Ein Konsolenfenster muss dabei offen bleiben. Für den gelegentlichen Gebrauch ist der
    Doppelklick meist bequemer.

## Browser-Unterstützung

| Browser | Ansicht | Automatisch in Datei speichern |
|---|---|---|
| Microsoft Edge | ✓ | ✓ |
| Google Chrome | ✓ | ✓ |
| Firefox | ✓ | – (Sichern/Laden von Hand) |
| Safari | ✓ | – (Sichern/Laden von Hand) |

## Mitarbeiten

Der Quelltext liegt auf [GitHub](https://github.com/Delido/schliessfaecher-ogs).
Fehlerberichte und Vorschläge sind willkommen – am besten als Issue.

Zum Ändern genügt ein Texteditor: Datei öffnen, anpassen, im Browser neu laden.
