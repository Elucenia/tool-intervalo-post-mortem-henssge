<!-- ELUCENIA technical documentation · intervalo-post-mortem-henssge · en · no clinical/professional/rights approval -->

# Postmortem interval from temperature (Henssge)

[conditions, sources and permissions](https://elucenia.org/en/tools/intervalo-post-mortem-henssge)

## How to use

Use the tool in the portal or open index.html through a local HTTP server. Select the language, complete the fields and calculate.

## Inputs and units

### Deep rectal temperature

`tr`

°C · range: 5–42

### Ambient temperature (local mean)

`ta`

°C · range: -10–35

### Body weight

`peso`

kg · range: 1–250

### Weight correction factor (1.0 = naked, dry body in still air)

`fc`

optional · range: 0.3–3

## Method edition

Henssge: technical equation of Otatsume et al. 2024 (up to 23 °C: 5/4 and 1/4; above 23 °C: 10/9 and 1/9); numerical bisection; the 1988 original was not read in full

## Documented formula

Standardized temperature: Q = (Trectal − Tambient) / (37.2 − Tambient).

Ambient temperature up to 23 °C: Q = 1.25 × eBt − 0.25 × e5Bt. Ambient temperature above 23 °C: Q = (10/9) × eBt − (1/9) × e10Bt.

B = −1.2815 × (factor × weight)−0.625 + 0.0284. Time t (hours) is found by numerically solving the equation, as in the nomogram.

## Limits and population

The Henssge estimate depends on the cooling model and a rectal measurement, with environmental conditions and correction factors defined in the version. It is not an exact time of death. The numerical solution and uncertainty must match the case conditions and source; the original abstract does not allow all these criteria to be confirmed. This variant declares the technical equation of Otatsume and colleagues, 2024, whose equations 1–4 were read on page 2 of the article: A = 5/4 for ambient temperature up to 23 °C and A = 10/9 above 23 °C. The coefficient 10/9 is used as a fraction, without replacing it with 1.11. The B term, the factor applied to weight, the input limits and the numerical solution remain those of this interface. The 2019 publication prints 1.11 and 0.11, a different ambient-temperature boundary and a different placement of the correction factor; that edition is retained as a comparison, not as proof of full equivalence. The 1988 original was not read in full. This check does not approve an individual time of death, selection of correction factors, uncertainty, the confidence interval or forensic use.

## References

- [Henssge C. Death time estimation in case work. I. The rectal temperature time of death nomogram. Forensic Sci Int, 1988.](https://doi.org/10.1016/0379-0738(88)90168-5)

- [Henssge C, Madea B. Estimation of the time since death in the early post-mortem period. Forensic Sci Int, 2004.](https://doi.org/10.1016/j.forsciint.2004.04.051)

- [Schweitzer W, Thali MJ. Computationally approximated solution for the equation for Henssge's time of death estimation. BMC Med Inform Decis Mak, 2019.](https://doi.org/10.1186/s12911-019-0920-y)

- [Otatsume et al.2024, technical equations1–4, printedp2; not full original1988 nomogram review.](https://miyazaki-u.repo.nii.ac.jp/record/2000525/files/1-s2.0-S1752928X2300152X-main.pdf)

## Reproduce the technical tests

Run node test.cjs in the root directory of this repository to repeat the recorded synthetic cases. Original inputs, expectations and tolerances are preserved. Technical tests do not constitute clinical validation.

```sh
node test.cjs
```

tool.json contains sources, edition and review scope. examples.json retains synthetic inputs and expectations; results.json records the obtained results.

[Record and references](../tool.json) · [JavaScript code](../calculator.js) · [Reference cases](../examples.json) · [results.json](../results.json)

## Review and conditions of use

Independent clinical review has not been performed.

This interface is an authorial translation, not an official or certified edition. Independent clinical review, professional language review and instrument rights clearance have not been performed.

Formula or classification result. Interpretation, care and applicability depend on professional assessment and the selected source.

## License and attribution

Apache-2.0 applies only to ELUCENIA code. Rights to instruments, publications, translations and data remain with their respective holders. Preserve LICENSE and NOTICE.

ELUCENIA · Felipe Guedes · Copyright © 2026

## Documented results

The information below preserves the method outputs for synthetic examples. It does not constitute independent clinical validation.

### 1

Death about 10 h ago (point estimate of the model)

| Result details | |
| --- | --- |
| Equation used | environment up to 23 °C (1,25 / 0,25) |
| Corrected weight (factor × weight) | 70.0 kg |
| Cooling constant B | -0.0617 h⁻¹ |
| Standardized temperature Q | 0.663 |

The narrowest 95% confidence interval of the method is ±2,8 h, under standard conditions (factor 1). With correction factors, long intervals, or unstable environment, the limits are wider: read the limits on the original nomogram.


### 2

Death about 6 h 1 min ago (model point estimate)

| Result details | |
| --- | --- |
| Equation used | ambient temperature above 23 °C (10/9 / 1/9) |
| Corrected weight (factor × weight) | 80.0 kg |
| Cooling constant B | -0.0544 h⁻¹ |
| Standardized temperature Q | 0.797 |

The narrowest 95% confidence interval of the method is ±2,8 h, under standard conditions (factor 1). With correction factors, long intervals, or unstable environment, the limits are wider: read the limits on the original nomogram.

