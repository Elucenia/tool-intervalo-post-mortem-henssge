<!-- ELUCENIA technical documentation · intervalo-post-mortem-henssge · es · no clinical/professional/rights approval -->

# Intervalo post mortem por temperatura (Henssge)

[condiciones, fuentes y permisos](https://elucenia.org/es/herramientas/intervalo-post-mortem-henssge)

## Cómo usar

Utilice la herramienta en el portal o abra index.html mediante un servidor HTTP local. Seleccione el idioma, complete los campos y calcule.

## Entradas y unidades

### Temperatura rectal profunda

`tr`

°C · intervalo: 5–42

### Temperatura ambiente (media local)

`ta`

°C · intervalo: -10–35

### Peso corporal

`peso`

kg · intervalo: 1–250

### Factor de corrección del peso (1,0 = cuerpo desnudo, seco, en aire quieto)

`fc`

opcional · intervalo: 0,3–3

## Edición del método

Henssge: ecuación técnica de Otatsume et al. 2024 (hasta 23 °C: 5/4 y 1/4; por encima de 23 °C: 10/9 y 1/9); bisección numérica; el original de 1988 no se leyó íntegramente

## Fórmula documentada

Temperatura estandarizada: Q = (Trectal − Tambiente) / (37,2 − Tambiente).

Ambiente hasta 23 °C: Q = 1,25 × eBt − 0,25 × e5Bt. Ambiente por encima de 23 °C: Q = (10/9) × eBt − (1/9) × e10Bt.

B = −1,2815 × (factor × peso)−0,625 + 0,0284. El tiempo t (horas) se obtiene resolviendo numéricamente la ecuación, como en el nomograma.

## Límites y población

La estimación de Henssge depende del modelo de enfriamiento y de una medición rectal, con condiciones ambientales y factores de corrección definidos en la versión. No es una hora exacta de muerte. La solución numérica y la incertidumbre deben corresponder a las condiciones del caso y a la fuente; el resumen original no permite confirmar todos estos criterios. Esta variante declara la ecuación técnica de Otatsume y colaboradores, de 2024, cuyas ecuaciones 1–4 se leyeron en la página 2 del artículo: A = 5/4 para temperaturas ambientales hasta 23 °C y A = 10/9 por encima de 23 °C. El coeficiente 10/9 se utiliza como fracción, sin sustituirlo por 1,11. El término B, el factor aplicado al peso, los límites de entrada y la solución numérica se mantienen como en esta interfaz. La publicación de 2019 imprime 1,11 y 0,11, un límite ambiental diferente y una posición distinta del factor de corrección; esa edición se conserva como comparación, no como prueba de equivalencia íntegra. El original de 1988 no se leyó íntegramente. La comprobación no aprueba la hora de muerte individual, la selección de factores de corrección, la incertidumbre, el intervalo de confianza ni el uso pericial.

## Referencias

- [Henssge C. Death time estimation in case work. I. The rectal temperature time of death nomogram. Forensic Sci Int, 1988.](https://doi.org/10.1016/0379-0738(88)90168-5)

- [Henssge C, Madea B. Estimation of the time since death in the early post-mortem period. Forensic Sci Int, 2004.](https://doi.org/10.1016/j.forsciint.2004.04.051)

- [Schweitzer W, Thali MJ. Computationally approximated solution for the equation for Henssge's time of death estimation. BMC Med Inform Decis Mak, 2019.](https://doi.org/10.1186/s12911-019-0920-y)

- [Otatsume et al.2024, technical equations1–4, printedp2; not full original1988 nomogram review.](https://miyazaki-u.repo.nii.ac.jp/record/2000525/files/1-s2.0-S1752928X2300152X-main.pdf)

## Reproducir las pruebas técnicas

Ejecute node test.cjs en el directorio raíz de este repositorio para repetir los casos sintéticos registrados. Se conservan las entradas, los resultados esperados y las tolerancias originales. Las pruebas técnicas no constituyen validación clínica.

```sh
node test.cjs
```

tool.json contiene las fuentes, la edición y el alcance de la revisión. examples.json conserva las entradas y los resultados esperados de los casos sintéticos; results.json registra los resultados obtenidos.

[Ficha y referencias](../tool.json) · [Código JavaScript](../calculator.js) · [Casos de referencia](../examples.json) · [results.json](../results.json)

## Revisión y condiciones de uso

No se ha realizado una revisión clínica independiente.

Esta interfaz es una traducción de elaboración propia, no una edición oficial o certificada. No se han realizado la revisión clínica independiente, la revisión lingüística profesional ni la autorización de derechos de los instrumentos.

Resultado de la fórmula o clasificación. La interpretación, la conducta y la aplicabilidad dependen de la evaluación profesional y de la fuente seleccionada.

## Licencia y atribución

Apache-2.0 se aplica únicamente al código de ELUCENIA. Los derechos de los instrumentos, publicaciones, traducciones y datos permanecen en manos de sus respectivos titulares. Conserve LICENSE y NOTICE.

ELUCENIA · Felipe Guedes · Copyright © 2026
