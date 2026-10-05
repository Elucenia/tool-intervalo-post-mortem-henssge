<!-- ELUCENIA technical documentation · intervalo-post-mortem-henssge · de · no clinical/professional/rights approval -->

# Postmortales Intervall anhand der Temperatur (Henssge)

[Bedingungen, Quellen und Berechtigungen](https://elucenia.org/de/werkzeuge/intervalo-post-mortem-henssge)

## Verwendung

Verwenden Sie das Werkzeug im Portal oder öffnen Sie index.html über einen lokalen HTTP-Server. Wählen Sie die Sprache, füllen Sie die Felder aus und berechnen Sie das Ergebnis.

## Eingaben und Einheiten

### Tiefe Rektaltemperatur

`tr`

°C · Bereich: 5–42

### Umgebungstemperatur (örtlicher Mittelwert)

`ta`

°C · Bereich: -10–35

### Körpergewicht

`peso`

kg · Bereich: 1–250

### Gewichtskorrekturfaktor (1,0 = nackter, trockener Körper in ruhender Luft)

`fc`

optional · Bereich: 0,3–3

## Fassung der Methode

Henssge: technische Gleichung von Otatsume et al. 2024 (bis 23 °C: 5/4 und 1/4; über 23 °C: 10/9 und 1/9); numerische Bisektion; das Original von 1988 wurde nicht vollständig gelesen

## Dokumentierte Formel

Standardisierte Temperatur: Q = (Trektal − TUmgebung) / (37,2 − TUmgebung).

Umgebung bis 23 °C: Q = 1,25 × eBt − 0,25 × e5Bt. Umgebung über 23 °C: Q = (10/9) × eBt − (1/9) × e10Bt.

B = −1,2815 × (Faktor × Gewicht)−0,625 + 0,0284. Die Zeit t (Stunden) wird durch numerische Lösung der Gleichung wie im Nomogramm ermittelt.

## Grenzen und Population

Die Henssge-Schätzung hängt vom Abkühlungsmodell und einer rektalen Messung mit den in der Version festgelegten Umweltbedingungen und Korrekturfaktoren ab. Sie liefert keinen exakten Todeszeitpunkt. Numerische Lösung und Unsicherheit müssen zu Fallbedingungen und Quelle passen; das Originalabstract erlaubt keine Bestätigung all dieser Kriterien. Diese Variante nennt die technische Gleichung von Otatsume und Mitarbeitern aus dem Jahr 2024, deren Gleichungen 1–4 auf Seite 2 des Artikels gelesen wurden: A = 5/4 bei Umgebungstemperaturen bis 23 °C und A = 10/9 über 23 °C. Der Koeffizient 10/9 wird als Bruch verwendet und nicht durch 1,11 ersetzt. Der Term B, der auf das Gewicht angewandte Faktor, die Eingabegrenzen und die numerische Lösung bleiben die dieser Oberfläche. Die Veröffentlichung von 2019 druckt 1,11 und 0,11 sowie eine andere Umgebungstemperaturgrenze und eine andere Position des Korrekturfaktors; diese Ausgabe bleibt als Vergleich dokumentiert und dient nicht als Nachweis vollständiger Gleichwertigkeit. Das Original von 1988 wurde nicht vollständig gelesen. Die Prüfung genehmigt weder den individuellen Todeszeitpunkt noch die Auswahl der Korrekturfaktoren, die Unsicherheit, das Konfidenzintervall oder den rechtsmedizinischen Einsatz.

## Referenzen

- [Henssge C. Death time estimation in case work. I. The rectal temperature time of death nomogram. Forensic Sci Int, 1988.](https://doi.org/10.1016/0379-0738(88)90168-5)

- [Henssge C, Madea B. Estimation of the time since death in the early post-mortem period. Forensic Sci Int, 2004.](https://doi.org/10.1016/j.forsciint.2004.04.051)

- [Schweitzer W, Thali MJ. Computationally approximated solution for the equation for Henssge's time of death estimation. BMC Med Inform Decis Mak, 2019.](https://doi.org/10.1186/s12911-019-0920-y)

- [Otatsume et al.2024, technical equations1–4, printedp2; not full original1988 nomogram review.](https://miyazaki-u.repo.nii.ac.jp/record/2000525/files/1-s2.0-S1752928X2300152X-main.pdf)

## Technische Tests reproduzieren

Führen Sie node test.cjs im Stammverzeichnis dieses Repositorys aus, um die dokumentierten synthetischen Fälle zu wiederholen. Ursprüngliche Eingaben, erwartete Ergebnisse und Toleranzen bleiben erhalten. Technische Tests stellen keine klinische Validierung dar.

```sh
node test.cjs
```

tool.json enthält Quellen, Ausgabe und Umfang der Überprüfung. examples.json bewahrt die synthetischen Eingaben und erwarteten Ergebnisse; results.json dokumentiert die tatsächlich erhaltenen Ergebnisse.

[Eintrag und Referenzen](../tool.json) · [JavaScript-Code](../calculator.js) · [Referenzfälle](../examples.json) · [results.json](../results.json)

## Überprüfung und Nutzungsbedingungen

Eine unabhängige klinische Prüfung wurde nicht durchgeführt.

Diese Benutzeroberfläche ist eine selbst erstellte Übersetzung und keine offizielle oder zertifizierte Ausgabe. Eine unabhängige klinische Überprüfung, eine professionelle sprachliche Prüfung und eine Klärung der Rechte an den Instrumenten wurden nicht durchgeführt.

Ergebnis der Formel oder Klassifikation. Interpretation, Vorgehen und Anwendbarkeit hängen von der fachlichen Beurteilung und der ausgewählten Quelle ab.

## Lizenz und Urheberangaben

Apache-2.0 gilt nur für den ELUCENIA-Code. Die Rechte an Instrumenten, Veröffentlichungen, Übersetzungen und Daten verbleiben bei den jeweiligen Rechteinhabern. Bewahren Sie LICENSE und NOTICE auf.

ELUCENIA · Felipe Guedes · Copyright © 2026
