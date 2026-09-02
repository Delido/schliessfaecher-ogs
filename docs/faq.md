# Häufige Fragen

??? question "Warum muss ich die Datei nach jedem Browserstart neu freigeben?"

    Weil die Datei per Doppelklick geöffnet wird (`file://`). In diesem Fall darf der
    Browser die Schreiberlaubnis aus Sicherheitsgründen nicht dauerhaft speichern – das
    ist eine Regel des Browsers, kein Fehler der App.

    Wer das vermeiden will, liefert die Datei über einen lokalen Webserver aus; unter
    `http://localhost` merkt sich der Browser die Freigabe dauerhaft. Siehe
    [Technik](technik.md#webserver).

??? question "Ich habe die Datendatei gelöscht – trotzdem sind alle Daten noch da?"

    Die App speichert zusätzlich im Browser. Solange dieser Speicher besteht, sind die
    Daten dort erhalten und werden beim nächsten Verbinden wieder in die Datei geschrieben.

    Für einen echten Neuanfang: **Mehr → Neu beginnen**.

??? question "Kann ich die App auf mehreren Rechnern gleichzeitig nutzen?"

    Ansehen ja, gemeinsam bearbeiten nicht. Es gibt keinen Abgleich zwischen Rechnern –
    wer zuletzt speichert, überschreibt den anderen Stand.

    Praktikabel ist: ein Rechner führt die Liste, der Stand wird bei Bedarf über
    **Sicherungskopie speichern** weitergegeben.

??? question "Funktioniert die App in Firefox?"

    Ja, aber ohne automatisches Speichern in eine Datei – Firefox unterstützt die dafür
    nötige Schnittstelle nicht. Dort muss man **Sicherungskopie speichern** und
    **Sicherung laden** von Hand nutzen.

    Für den vollen Funktionsumfang eignen sich Microsoft Edge und Google Chrome.

??? question "Kann ich Änderungen aus Excel zurückspielen?"

    Nein. Der CSV-Export ist zum Auswerten und Ausdrucken gedacht. Ein Rückimport würde
    Verlauf, Defekt- und Personal-Kennzeichnung verlieren – ein stiller Datenverlust wäre
    schlimmer als die fehlende Bequemlichkeit.

    Zum Übertragen zwischen Rechnern dient die JSON-Sicherung.

??? question "Unsere Schränke haben eine andere Aufteilung als 3×4 – geht das?"

    Ja. Beim Anlegen gibt man an, wie viele Fächer **nebeneinander** liegen; eine Vorschau
    zeigt das Ergebnis sofort. Möglich ist alles von einer einzelnen Reihe bis zu zwölf
    Fächern nebeneinander.

    Bei bestehenden Schränken lässt sich die Anordnung über **Bearbeiten** ändern.

??? question "Wie viele Fächer verträgt die App?"

    Getestet mit gut 200 Fächern ohne merkliche Verzögerung. Auch einige Tausend sollten
    problemlos laufen, da alles im Arbeitsspeicher gehalten wird.

??? question "Die Auswertung meldet gleiche Schlossnummern – ist das ein Fehler?"

    Nicht unbedingt. Gleiche Schlossnummern können durchaus richtig sein: bei
    gleichschließenden Schlössern, oder wenn Nummernkreise je Gruppe oder Lieferung
    getrennt geführt werden.

    Die App weist nur darauf hin, damit man es einmal am Schrank abgleichen kann –
    sie behauptet nicht, dass etwas falsch ist. Stimmt die Nummer, kann der Hinweis
    einfach stehen bleiben.

??? question "Ein Kind hat zwei Fächer – geht das?"

    Ja. Die App verhindert das nicht. In der **Auswertung** unter *Prüfen* wird allerdings
    darauf hingewiesen, wenn derselbe Name in mehreren Fächern steht – das kann richtig
    sein (zwei Kinder gleichen Namens) oder ein Versehen.

??? question "Was passiert bei einem Namenswechsel?"

    Einfach den Namen im Fach ändern. Der alte Name wandert automatisch in den Verlauf
    („Vorher in diesem Fach") mit Datum.

??? question "Kann man die App anpassen?"

    Ja – es ist eine einzelne HTML-Datei mit lesbarem CSS und JavaScript, MIT-lizenziert.
    Farben und Texte stehen im `<style>`- beziehungsweise `<script>`-Block am Anfang
    der Datei.
