<!-- ELUCENIA technical documentation · intervalo-post-mortem-henssge · pt-BR · no clinical/professional/rights approval -->

# Intervalo post-mortem pela temperatura (Henssge)

[condições, fontes e permissões](https://elucenia.org/pt-br/ferramentas/intervalo-post-mortem-henssge)

## Como usar

Use a ferramenta no portal ou abra index.html em um servidor HTTP local. Selecione o idioma, preencha os campos e calcule.

## Entradas e unidades

### Temperatura retal profunda

`tr`

°C · intervalo: 5–42

### Temperatura ambiente (média no local)

`ta`

°C · intervalo: -10–35

### Peso corporal

`peso`

kg · intervalo: 1–250

### Fator de correção do peso (1,0 = corpo nu, seco, em ar parado)

`fc`

opcional · intervalo: 0,3–3

## Edição do método

Henssge: equação técnica de Otatsume et al. 2024 (até 23 °C: 5/4 e 1/4; acima de 23 °C: 10/9 e 1/9); bisseção numérica; original de 1988 não lido integralmente

## Fórmula documentada

Temperatura padronizada: Q = (Tretal − Tambiente) / (37,2 − Tambiente).

Ambiente até 23 °C: Q = 1,25 × eBt − 0,25 × e5Bt. Ambiente acima de 23 °C: Q = (10/9) × eBt − (1/9) × e10Bt.

B = −1,2815 × (fator × peso)−0,625 + 0,0284. O tempo t (horas) é obtido por solução numérica da equação, como no nomograma.

## Limites e população

A estimativa de Henssge depende do modelo de resfriamento e de uma medida retal, com condições ambientais e fatores de correção definidos na versão. Não é hora de morte exata. A solução numérica e a incerteza precisam corresponder às condições do caso e à fonte; o resumo original não permite confirmar todos esses critérios. Esta variante declara a equação técnica de Otatsume e colaboradores, de 2024, cujas equações 1–4 foram lidas na página 2 do artigo: A = 5/4 para ambiente até 23 °C e A = 10/9 acima de 23 °C. O coeficiente 10/9 é usado como fração, sem substituí-lo por 1,11. O termo B, o fator aplicado ao peso, os limites de entrada e a solução numérica permanecem os mesmos desta interface. A publicação de 2019 imprime 1,11 e 0,11, uma fronteira ambiental diferente e uma colocação diferente do fator de correção; essa edição fica registrada como comparação, não como prova de equivalência integral. O original de 1988 não foi lido integralmente. A conferência não aprova a hora de morte individual, a escolha dos fatores de correção, a incerteza, o intervalo de confiança nem o uso pericial.

## Referências

- [Henssge C. Death time estimation in case work. I. The rectal temperature time of death nomogram. Forensic Sci Int, 1988.](https://doi.org/10.1016/0379-0738(88)90168-5)

- [Henssge C, Madea B. Estimation of the time since death in the early post-mortem period. Forensic Sci Int, 2004.](https://doi.org/10.1016/j.forsciint.2004.04.051)

- [Schweitzer W, Thali MJ. Computationally approximated solution for the equation for Henssge's time of death estimation. BMC Med Inform Decis Mak, 2019.](https://doi.org/10.1186/s12911-019-0920-y)

- [Otatsume et al.2024, technical equations1–4, printedp2; not full original1988 nomogram review.](https://miyazaki-u.repo.nii.ac.jp/record/2000525/files/1-s2.0-S1752928X2300152X-main.pdf)

## Reproduzir os testes técnicos

Execute node test.cjs na pasta raiz deste repositório para repetir os casos sintéticos registrados. As entradas, expectativas e tolerâncias originais são preservadas. Testes técnicos não constituem validação clínica.

```sh
node test.cjs
```

tool.json contém fontes, edição e escopo de revisão. examples.json conserva as entradas e expectativas sintéticas; results.json registra os resultados obtidos.

[Ficha e referências](../tool.json) · [Código JavaScript](../calculator.js) · [Casos de referência](../examples.json) · [results.json](../results.json)

## Revisão e condições de uso

Revisão clínica independente não realizada.

Esta interface é uma tradução autoral, não uma edição oficial ou certificada. Revisão clínica independente, revisão linguística profissional e autorização de direitos de instrumentos não foram realizadas.

Resultado da fórmula ou classificação. Interpretação, conduta e aplicabilidade dependem da avaliação profissional e da fonte selecionada.

## Licença e atribuição

Apache-2.0 aplica-se somente ao código da ELUCENIA. Os instrumentos, publicações, traduções e dados mantêm os direitos dos respectivos titulares. Preserve LICENSE e NOTICE.

ELUCENIA · Felipe Guedes · Copyright © 2026
