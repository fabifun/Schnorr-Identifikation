# Paper: Schnorr-Identifikation

## Direkt anfangen

1. Diesen Ordner `schnorr-paper` in VS Code öffnen (oder `schnorr-paper.code-workspace`).
2. Die empfohlene Erweiterung **LaTeX Workshop** installieren.
3. `main.tex` öffnen; den Inhalt in `sections/01-einleitung.tex` usw. schreiben.
4. In der Befehlspalette **LaTeX Workshop: Build LaTeX project** ausführen.
5. Mit **LaTeX Workshop: View LaTeX PDF file** die Vorschau öffnen.

Beim Speichern wird automatisch gebaut. Das PDF entsteht unter `build/main.pdf`.

## Voraussetzung

Auf diesem Rechner wurden weder `latexmk`, `pdflatex` noch `biber` im PATH
oder unter `/Library/TeX/texbin` gefunden. Eine PDF-Kompilierung konnte deshalb
bei der Erstellung nicht geprüft werden.

Für macOS eine vollständige TeX-Distribution wie [MacTeX](https://www.tug.org/mactex/)
installieren; danach VS Code neu starten. Die Konfiguration berücksichtigt
`/Library/TeX/texbin`. Benötigt werden pdfLaTeX, latexmk, Biber und die in
`main.tex` geladenen Pakete. Die VS-Code-Erweiterung allein enthält diese nicht.

Alternativ im Terminal im Projektordner:

```sh
latexmk -pdf -interaction=nonstopmode -file-line-error -synctex=1 -outdir=build main.tex
```

## Aufbau und Umfang

Die Gliederung folgt dem Themenvorschlag der Mail: Problemstellung → Gruppen
und diskreter Logarithmus → mathematisches Protokoll → Praxis/Aufwand →
Vor- und Nachteile/Einsatzbedingungen → Fazit.

Die Mail enthält keine verbindliche Seitenzahl, Formatvorgabe oder bestätigte
Annahme des Themenvorschlags. A4, 11 pt und 2,5 cm Rand sind neutrale Defaults.
Das Rechenbeispiel ist optional; bei knapperem Umfang kann es zugunsten
quellenbelegter Anwendungsfälle entfallen. Eine kurze Sicherheits- und
Aufwandsdiskussion bleibt sinnvoll.

Blaue Schreibhinweise sind Arbeitsaufträge, kein ausformulierter Papertext.
Die Formeln und Notation bieten einen konsistenten Ausgangspunkt. Das Paper
soll ansonsten selbst geschrieben werden. Begriffe vor Verwendung erklären;
kurze Korrektheitsbeweise selbst ausführen, längere Beweise präzise referenzieren.

## Schreiben und Zitieren

- Quellen: `literatur.bib`; zitieren mit `\cite{schnorr1991}` oder
  mit genauer Stelle `\cite[Abschnitt~2]{schnorr1991}` (Stelle vorher prüfen).
- Querverweise: `\label{sec:name}` und `\ref{sec:name}`.
- Weitere Quellen für Angriffskomplexität und konkrete Anwendungen ergänzen.
- RFC 8235 behandelt eine nichtinteraktive Variante; diese nicht mit dem
  interaktiven Identifikationsprotokoll gleichsetzen.
- In der gewählten Notation gilt `y = g^x`, `s = r + cx mod q` und `g^s = t y^c`.
  Im endlichen Körper: Gruppenelemente modulo p, Exponenten modulo q.
- Die Startliteratur wird durch `\nocite` angezeigt, auch ohne Textzitat.
  Vor Abgabe diese Zeile entfernen und nur tatsächlich verwendete Quellen zitieren.

## Vor der Abgabe

Alle `\todo{...}` abarbeiten, optionale Teile bereinigen, Quellenstellen prüfen,
Datum anpassen und `\entwurftrue` auf `\entwurffalse` setzen. Das Ausblenden
ersetzt nicht das Abarbeiten der Hinweise. PDF auf Umbrüche, Literatur und
unaufgelöste Referenzen prüfen.
