# TimYClock JS

Browserbasierte Neuauflage von [TimYClock](https://github.com/JuergenSu/TimYClock): eine rote LED-Matrix-Uhr mit 64 × 8 Punkten, Uhrzeit und Laufschrift. **Keine Hardware, keine Bibliotheken und kein Backend nötig.**

## Start

`index.html` direkt im Browser öffnen oder auf einem beliebigen statischen Webserver bereitstellen. Die Anzeige benötigt keine Internetverbindung.

## Konfiguration

Direkt am **Anfang von `index.html`** den Block `const CONFIG = { ... }` bearbeiten:

| Eigenschaft | Bedeutung |
| --- | --- |
| `mode` | `1`: Uhrzeit, `2`: Text, `3`: Uhrzeit + Text, `4`: Uhrzeit + Geburtstage |
| `text` | Frei definierter Laufschrifttext für Modus 2 und 3 |
| `birthdays` | Namen und Geburtstag (`day`, `month`) für Modus 4 |
| `timeZone` | Zeitzone, standardmäßig `Europe/Berlin` |
| `scrollEveryMinutes` | Abstand in Minuten zwischen Laufschriften, standardmäßig 2 |
| `scrollStepMs` | Zeit pro Pixelverschiebung, standardmäßig 75 ms |
| `brightness` | Helligkeit der roten LED-Simulation von 0.1 bis 1.0 |
| `ledColor` | Farbe der LEDs im Hex-Format |
| `leapDayBirthday` | Geburtstag am 29. Februar im Nicht-Schaltjahr: `feb28` oder `mar1` |

Es gibt bewusst **keine Einstellungsoberfläche**. Nach dem Ändern der HTML-Datei genügt ein Neuladen des Browsers.

## Bedienung

- Die Uhr orientiert sich an der Systemzeit des Geräts und berücksichtigt die eingestellte Zeitzone einschließlich Sommerzeit.
- Mit der Schaltfläche **Vollbild**, der Taste **F** oder Doppelklick auf das Display wird der Vollbildmodus ein- oder ausgeschaltet. **Esc** beendet ihn.
- Die Berechnung der verbleibenden Tage berücksichtigt echte Kalenderjahre und Schaltjahre.
- Die Anzeige nutzt ein Canvas mit eigenem 5×7-Pixelfont, acht simulierten 8×8-Modulen und animierten Leuchtpunkten.

## Deployment

Das Repository enthält nur `index.html` und diese README. Für GitHub Pages muss das Repository öffentlich oder ein geeigneter Pages-Plan vorhanden sein; alternativ kann die Datei auf jedem anderen Webserver liegen.
