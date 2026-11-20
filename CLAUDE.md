# FOEDIMA-Auswertung

Auswertungshilfe für zwei FÖDiMA-Standortbestimmungen (PIKAS/DZLM), die Joshua jeweils zweimal durchführt (Messung 1 und 2):
**Multiplikation ZR 100 (OV100M)** und **Addition ZR 100 (OV100A)**, je 6 Aufgaben. Eine HTML-Datei, läuft nur lokal im Browser.

## Dateien

- `index.html` – die App (Doppelklick oder online). Vanilla JS, keine Abhängigkeiten, kein Build.
- `pdf/standort1-multiplikation.pdf`, `pdf/standort2-addition.pdf` – die Original-Arbeitsblätter, nach denen die Aufgabenliste gebaut ist.

## Bedienung / Logik

- Eingabetabelle: Aufgaben untereinander, Kinder nebeneinander (je Kind zwei Spalten: Messung 1 / 2), Fehler/Prozent/Veränderung oben.
  Pro Teilaufgabe ein Feld: leer → ✓ richtig → ✗ falsch → leer.
- Leer = nicht bewertet und zählt nicht mit. Prozent richtig = richtig / (richtig + falsch). Fehler = Anzahl ✗.
- Veränderung = Prozentpunkte (Messung 2 minus Messung 1), nicht relative Prozent.
- Ansichten: Eingabe (Tabelle), Pro Kind (mit Druckblatt), Klasse & Aufgaben (Balken je Aufgabe, Überblick, CSV-Export).
- Aufgaben stehen im Objekt `TESTS` oben im Skript (id, Beschriftung, Lösung). Neue Standortbestimmung = neuer Eintrag dort.
- Daten: `localStorage` im Browser (Schlüssel `foedima-auswertung-v1`), dazu „Sichern/Laden“ als JSON-Datei.
  Achtung: andere Browser oder anderer Dateipfad = andere Daten → regelmäßig sichern.

## Hosting

GitHub Pages: Repo `edutoolz/foedima` (Remote `git@github-edutoolz:edutoolz/foedima.git`), Adresse https://edutoolz.github.io/foedima/ . Veröffentlichen: `git push`.
Die App sendet nichts, Namen und Ergebnisse bleiben im Browser (localStorage). `pdf/` (Original-Blätter PIKAS/DZLM) ist in `.gitignore`, nie committen.

## Offen

- Die Lösungs-Hinweise bei „passende Aufgabe finden“ sind Beispiele, keine Musterlösung.
- Aufgaben wurden von den PDFs abgetippt; Zahlen einmal gegen das Blatt prüfen.
