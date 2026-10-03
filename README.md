# Sauerstoffgehalt der Luft

Simulation zur Bestimmung des Sauerstoffgehalts der Luft mit der
**ChemZ-Technik** — zwei Luer-Lock-Spritzen und ein Dreiwegehahn statt
Bunsenbrenner.

## Was hier liegt

| Datei | Inhalt |
|---|---|
| `sauerstoff-sim-a.html` | die Web-App für ein Bricks-Code-Element |
| `sauerstoff-sim-a - Kopie.html` | ältere Fassung, siehe unten |
| `3_Wege_Hahn.svg` / `.png` | Abbildung Dreiwegehahn |
| `Luer_Lock_Spritzen_-Experimente.svg`, `luerlock-spritze.svg` / `.png` | Abbildungen Spritzen |
| `Anordnung der App Elemente.png` | Entwurf des Aufbaus |

## Zwei Fassungen nebeneinander

`sauerstoff-sim-a - Kopie.html` ist 3,5 KB kleiner und unterscheidet sich
inhaltlich. **Zu klären, ob sie noch gebraucht wird** — seit dem 03.10.2026
steht dieser Ordner unter Versionskontrolle, alte Stände sind also auch ohne
zweite Datei erhalten. Bei der Rutherford-App wurde derselbe Fall so
aufgelöst: alte Varianten gelöscht, Historie behalten.

## Stand (03.10.2026)

| Prüfung | Ergebnis |
|---|---|
| `standardcheck.py` (F1–F14) | **ohne Befund**, beide Fassungen |
| Ladeprobe im Browser | bestanden |
| Sichtprüfung hell und dunkel | steht aus |
| Didaktische Prüfung | steht aus |
| Zielgruppe | nicht dokumentiert |

Diese App war schon vor dem 03.10.2026 weitgehend standardkonform — sie trug
als einzige bereits das vollständige Wurzelmuster mit `document.currentScript`.

## Was am 03.10.2026 geändert wurde

- zwei `1px`-Angaben → `0.1rem`
- `@media (max-width: 600px)` → `37.5rem` (in Media Queries gilt
  1 rem = 16 px, nicht die Theme-Basis von 10 px — Standards §3.1)
- Die Begründung, warum hier **kein** Theme-Observer nötig ist, steht jetzt
  auch maschinenlesbar als `/* kein-theme-observer: … */` im Quelltext. Die
  Render-Schleife läuft dauerhaft und liest die Farben bei jedem Durchlauf
  neu; ein Observer wäre redundant. Das Prüfskript meldete den fehlenden
  Observer vorher als Hinweis, obwohl die Entscheidung richtig und im
  Quelltext begründet war.

## Prüfung vor einer Veröffentlichung

Werkzeuge liegen zentral in `C:\Users\grego\.claude\Standards`:

```
python werkzeuge/standardcheck.py "<Datei>.html"     # Form, F1–F14
bash   werkzeuge/sichtpruefung.sh "<Datei>.html"     # sechs Bilder + Überlaufmessung
```

## Urheber und Lizenz

Erstellt von Gregor von Borstel und David Weninger, entwickelt mit
Unterstützung von Claude (Anthropic), CC BY-SA 4.0
