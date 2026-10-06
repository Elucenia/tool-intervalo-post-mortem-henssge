<!-- ELUCENIA technical documentation · intervalo-post-mortem-henssge · it · no clinical/professional/rights approval -->

# Intervallo post mortem dalla temperatura (Henssge)

[condizioni, fonti e autorizzazioni](https://elucenia.org/it/strumenti/intervalo-post-mortem-henssge)

## Come usare

Usi lo strumento nel portale oppure apra index.html tramite un server HTTP locale. Selezioni la lingua, compili i campi ed esegua il calcolo.

## Dati di ingresso e unità

### Temperatura rettale profonda

`tr`

°C · intervallo: 5–42

### Temperatura ambiente (media locale)

`ta`

°C · intervallo: -10–35

### Peso corporeo

`peso`

kg · intervallo: 1–250

### Fattore di correzione del peso (1,0 = corpo nudo, asciutto, in aria ferma)

`fc`

facoltativo · intervallo: 0,3–3

## Edizione del metodo

Henssge: equazione tecnica di Otatsume et al. 2024 (fino a 23 °C: 5/4 e 1/4; oltre 23 °C: 10/9 e 1/9); bisezione numerica; l’originale del 1988 non è stato letto integralmente

## Formula documentata

Temperatura standardizzata: Q = (Trettale − Tambiente) / (37,2 − Tambiente).

Ambiente fino a 23 °C: Q = 1,25 × eBt − 0,25 × e5Bt. Ambiente sopra 23 °C: Q = (10/9) × eBt − (1/9) × e10Bt.

B = −1,2815 × (fattore × peso)−0,625 + 0,0284. Il tempo t (ore) si ottiene risolvendo numericamente l’equazione, come nel nomogramma.

## Limiti e popolazione

La stima di Henssge dipende dal modello di raffreddamento e da una misurazione rettale, con condizioni ambientali e fattori di correzione definiti nella versione. Non è un’ora esatta della morte. La soluzione numerica e l’incertezza devono corrispondere alle condizioni del caso e alla fonte; l’abstract originale non consente di confermare tutti questi criteri. Questa variante dichiara l’equazione tecnica di Otatsume e collaboratori del 2024, le cui equazioni 1–4 sono state lette a pagina 2 dell’articolo: A = 5/4 per temperature ambientali fino a 23 °C e A = 10/9 oltre 23 °C. Il coefficiente 10/9 viene usato come frazione, senza sostituirlo con 1,11. Il termine B, il fattore applicato al peso, i limiti di input e la soluzione numerica restano quelli di questa interfaccia. La pubblicazione del 2019 riporta 1,11 e 0,11, una diversa soglia della temperatura ambientale e una diversa posizione del fattore di correzione; tale edizione resta registrata come confronto, non come prova di equivalenza integrale. L’originale del 1988 non è stato letto integralmente. La verifica non approva l’ora di morte individuale, la scelta dei fattori di correzione, l’incertezza, l’intervallo di confidenza né l’uso peritale.

## Riferimenti

- [Henssge C. Death time estimation in case work. I. The rectal temperature time of death nomogram. Forensic Sci Int, 1988.](https://doi.org/10.1016/0379-0738(88)90168-5)

- [Henssge C, Madea B. Estimation of the time since death in the early post-mortem period. Forensic Sci Int, 2004.](https://doi.org/10.1016/j.forsciint.2004.04.051)

- [Schweitzer W, Thali MJ. Computationally approximated solution for the equation for Henssge's time of death estimation. BMC Med Inform Decis Mak, 2019.](https://doi.org/10.1186/s12911-019-0920-y)

- [Otatsume et al.2024, technical equations1–4, printedp2; not full original1988 nomogram review.](https://miyazaki-u.repo.nii.ac.jp/record/2000525/files/1-s2.0-S1752928X2300152X-main.pdf)

## Riprodurre i test tecnici

Esegua node test.cjs nella cartella principale di questo repository per ripetere i casi sintetici registrati. Gli input, i risultati attesi e le tolleranze originali sono conservati. I test tecnici non costituiscono validazione clinica.

```sh
node test.cjs
```

tool.json contiene le fonti, l’edizione e l’ambito della revisione. examples.json conserva gli input e i risultati attesi dei casi sintetici; results.json registra i risultati ottenuti.

[Scheda e riferimenti](../tool.json) · [Codice JavaScript](../calculator.js) · [Casi di riferimento](../examples.json) · [results.json](../results.json)

## Revisione e condizioni d’uso

Non è stata effettuata una revisione clinica indipendente.

Questa interfaccia è una traduzione realizzata dagli autori, non un’edizione ufficiale o certificata. Non sono state eseguite la revisione clinica indipendente, la revisione linguistica professionale né la verifica delle autorizzazioni relative ai diritti sugli strumenti.

Risultato della formula o classificazione. Interpretazione, condotta e applicabilità dipendono dalla valutazione professionale e dalla fonte selezionata.

## Licenza e attribuzione

Apache-2.0 si applica solo al codice di ELUCENIA. I diritti su strumenti, pubblicazioni, traduzioni e dati restano ai rispettivi titolari. Conservi LICENSE e NOTICE.

ELUCENIA · Felipe Guedes · Copyright © 2026

## Risultati documentati

Le informazioni seguenti conservano gli output del metodo per esempi sintetici. Non costituiscono una validazione clinica indipendente.

### 1

Morte circa 10 h fa (stima puntuale del modello)

| Dettagli del risultato | |
| --- | --- |
| Equazione utilizzata | ambiente fino a 23 °C (1,25 / 0,25) |
| Peso corretto (fattore × peso) | 70,0 kg |
| Costante di raffreddamento B | -0,0617 h⁻¹ |
| Temperatura standardizzata Q | 0,663 |

L’intervallo di confidenza del 95% più stretto del metodo è di ±2,8 h, in condizioni standard (fattore 1). Con fattori di correzione, intervalli lunghi o ambiente instabile, i limiti sono più ampi: leggere i limiti nel nomogramma originale.


### 2

Morte circa 6 h 1 min fa (stima puntuale del modello)

| Dettagli del risultato | |
| --- | --- |
| Equazione utilizzata | temperatura ambiente oltre 23 °C (10/9 / 1/9) |
| Peso corretto (fattore × peso) | 80,0 kg |
| Costante di raffreddamento B | -0,0544 h⁻¹ |
| Temperatura standardizzata Q | 0,797 |

L’intervallo di confidenza del 95% più stretto del metodo è di ±2,8 h, in condizioni standard (fattore 1). Con fattori di correzione, intervalli lunghi o ambiente instabile, i limiti sono più ampi: leggere i limiti nel nomogramma originale.

