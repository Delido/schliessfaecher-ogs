# Speichern und Sichern

## Wo liegen die Daten?

Die HTML-Datei ist **nur das Programm** und enthält keine Fächer. Eure Daten liegen an
zwei Orten:

1. **In einer Datei** neben der HTML – meist `Schliessfaecher_Daten.json`
2. **Im Browser** – als zusätzliche Kopie

Beides zusammen ist praktisch: Fehlt die Datei, hilft der Browser. Sind die Browserdaten
gelöscht, hilft die Datei.

## Freigabe {#freigabe}

Beim Öffnen per Doppelklick darf der Browser aus Sicherheitsgründen **die Schreiberlaubnis
nicht dauerhaft merken**. Sie muss deshalb nach jedem Browserstart einmal erteilt werden:
oben auf **Datei freigeben** klicken.

!!! info "Das ist kein Fehler"
    Es ist eine Sicherheitsregel des Browsers für Dateien, die per Doppelklick geöffnet
    werden (`file://`). Wer sie umgehen will, kann die Datei über einen lokalen Webserver
    ausliefern – siehe [Technik](technik.md#webserver).

Solange nicht freigegeben ist, läuft die App im **Nur-Ansicht-Modus**: Alles ist sichtbar
und durchsuchbar, nur Ändern ist gesperrt. So kann nichts verloren gehen.

Wurden beide Stände unterschiedlich geändert – etwa weil an einem anderen Rechner gearbeitet
wurde – fragt die App nach, welcher gelten soll.

## Sicherungskopien

Über **Mehr → Sicherungskopie speichern** entsteht eine datierte Datei
`schliessfaecher_JJJJ-MM-TT.json`.

!!! tip "Wann sinnvoll?"
    Vor größeren Änderungen, zum Schuljahreswechsel, und ansonsten gelegentlich. Wenn
    30 Tage keine Sicherung gemacht wurde, erinnert die App oben mit einem grauen Hinweis.

**Mehr → Sicherung laden** liest so eine Kopie wieder ein.

## Nach Excel exportieren

**Mehr → Als CSV für Excel** erzeugt eine Tabelle mit allen Fächern: Gruppe, Schrank, Fach,
Schloss, Status, Name, Schlüssel, Notiz und wer das Fach vorher hatte.

Die Datei ist auf deutsches Excel abgestimmt (Semikolon als Trenner) und lässt sich per
Doppelklick öffnen.

Ist gerade ein Filter gesetzt, enthält die Datei nur diese Fächer – praktisch für eine
Liste pro Gruppe. Der Dateiname endet dann auf `_auswahl`.

!!! warning "Nur zum Auswerten"
    Die CSV-Datei kann **nicht** zurückgelesen werden. Änderungen in Excel kommen nicht in
    die App zurück. Zum Wiederherstellen dient immer die JSON-Sicherung.

## Mehrere Rechner

Die App ist für **einen führenden Rechner** gedacht. Arbeiten zwei Personen gleichzeitig
an verschiedenen Rechnern, überschreibt die zuletzt geladene Sicherung die andere.

Soll der Stand weitergegeben werden: **Sicherungskopie speichern**, Datei übertragen, am
anderen Rechner **Sicherung laden**.

## Ganz von vorn beginnen

**Mehr → Neu beginnen** löscht den Stand im Browser und die Verbindung zur Datei. Die
Dateien im Ordner bleiben unangetastet.

Danach startet die App leer und man kann eine Sicherung einlesen. Nützlich, um zu prüfen,
ob eine Sicherungskopie im Ernstfall wirklich trägt.
