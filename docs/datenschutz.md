# Datenschutz

Die App verarbeitet Namen von Kindern – also personenbezogene Daten. Deshalb ist sie
bewusst so gebaut, dass diese Daten das Gerät nie verlassen.

## Keine Verbindung nach außen

**Die Seite stellt keine einzige Verbindung ins Internet her.**

- keine Schriften von Google Fonts
- keine CDNs, keine externen Skripte oder Stylesheets
- keine Analyse- oder Tracking-Dienste
- kein `fetch`, kein `XMLHttpRequest`, keine WebSockets

Verwendet werden ausschließlich **Systemschriften**. Damit entsteht auch keine Übertragung
der IP-Adresse an Dritte, die nach der Rechtsprechung zu Google Fonts
(LG München I, Urteil vom 20.01.2022, [3 O 17493/20](https://openjur.de/u/2387278.html))
problematisch wäre.

Die App funktioniert vollständig offline. Man kann das selbst prüfen: Netzwerkkabel ziehen
beziehungsweise WLAN abschalten – die App läuft unverändert weiter.

## Wo die Daten gespeichert werden

Ausschließlich lokal:

| Ort | Inhalt |
|---|---|
| JSON-Datei im Ordner | der vollständige Datenbestand |
| Browser (localStorage) | dieselben Daten als zweite Kopie |
| Browser (IndexedDB) | nur der Verweis auf die Datei, keine Inhalte |

Nichts davon wird übertragen, ausgewertet oder an Dritte weitergegeben.

## Was ihr trotzdem bedenken solltet

!!! warning "Die Datei ist unverschlüsselt"
    Die JSON-Datei kann jeder öffnen, der Zugriff auf den Ordner hat. Legt sie deshalb
    dorthin, wo auch die bisherige Liste lag – nicht in einen öffentlich geteilten Ordner.

- **Zugriffsrechte** auf den Ordner so eng wie möglich setzen
- **Sicherungskopien** ebenso behandeln wie die Hauptdatei
- Bei OneDrive oder ähnlichen Diensten prüfen, ob die Synchronisierung euren Vorgaben
  entspricht
- **Nicht mehr benötigte Daten löschen** – etwa Kinder, die die Einrichtung verlassen
  haben. Auch der Belegungsverlauf lässt sich pro Fach löschen.

## Dieses Repository

Das öffentliche Repository enthält **keine echten Personendaten**. Die mitgelieferte
`beispieldaten.json` ist frei erfunden ("Kind 01" bis "Kind 60").

Die beiliegende `.gitignore` verhindert, dass echte Datendateien versehentlich mit
hochgeladen werden – sie sperrt `Schliessfaecher_Daten.json`, alle
`schliessfaecher_*.json`, Office-Dateien und Bilder.
