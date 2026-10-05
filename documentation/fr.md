<!-- ELUCENIA technical documentation · intervalo-post-mortem-henssge · fr · no clinical/professional/rights approval -->

# Intervalle post-mortem selon la température (Henssge)

[conditions, sources et autorisations](https://elucenia.org/fr/outils/intervalo-post-mortem-henssge)

## Mode d’emploi

Utilisez l’outil sur le portail ou ouvrez index.html via un serveur HTTP local. Sélectionnez la langue, remplissez les champs et lancez le calcul.

## Données d’entrée et unités

### Température rectale profonde

`tr`

°C · intervalle: 5–42

### Température ambiante (moyenne locale)

`ta`

°C · intervalle: -10–35

### Poids corporel

`peso`

kg · intervalle: 1–250

### Facteur de correction du poids (1,0 = corps nu, sec, en air immobile)

`fc`

facultatif · intervalle: 0,3–3

## Édition de la méthode

Henssge : équation technique d’Otatsume et al. 2024 (jusqu’à 23 °C : 5/4 et 1/4 ; au-dessus de 23 °C : 10/9 et 1/9) ; bissection numérique ; l’original de 1988 n’a pas été lu intégralement

## Formule documentée

Température standardisée: Q = (Trectale − Tambiante) / (37,2 − Tambiante).

Ambiance jusqu’à 23 °C: Q = 1,25 × eBt − 0,25 × e5Bt. Ambiance au-dessus de 23 °C: Q = (10/9) × eBt − (1/9) × e10Bt.

B = −1,2815 × (facteur × poids)−0,625 + 0,0284. Le temps t (heures) est obtenu par résolution numérique de l’équation, comme dans le nomogramme.

## Limites et population

L’estimation de Henssge dépend du modèle de refroidissement et d’une mesure rectale, avec les conditions environnementales et facteurs de correction définis par la version. Ce n’est pas une heure de décès exacte. La solution numérique et l’incertitude doivent correspondre aux conditions du cas et à la source ; le résumé original ne permet pas de confirmer tous ces critères. Cette variante indique l’équation technique d’Otatsume et collaborateurs de 2024, dont les équations 1–4 ont été lues à la page 2 de l’article : A = 5/4 pour une température ambiante jusqu’à 23 °C et A = 10/9 au-dessus de 23 °C. Le coefficient 10/9 est utilisé sous forme de fraction, sans le remplacer par 1,11. Le terme B, le facteur appliqué au poids, les limites d’entrée et la résolution numérique restent ceux de cette interface. La publication de 2019 imprime 1,11 et 0,11, une limite de température ambiante différente et une autre position du facteur de correction ; cette édition est conservée comme comparaison, non comme preuve d’équivalence intégrale. L’original de 1988 n’a pas été lu intégralement. Cette vérification n’approuve ni l’heure de décès individuelle, ni le choix des facteurs de correction, ni l’incertitude, ni l’intervalle de confiance, ni l’usage médico-légal.

## Références

- [Henssge C. Death time estimation in case work. I. The rectal temperature time of death nomogram. Forensic Sci Int, 1988.](https://doi.org/10.1016/0379-0738(88)90168-5)

- [Henssge C, Madea B. Estimation of the time since death in the early post-mortem period. Forensic Sci Int, 2004.](https://doi.org/10.1016/j.forsciint.2004.04.051)

- [Schweitzer W, Thali MJ. Computationally approximated solution for the equation for Henssge's time of death estimation. BMC Med Inform Decis Mak, 2019.](https://doi.org/10.1186/s12911-019-0920-y)

- [Otatsume et al.2024, technical equations1–4, printedp2; not full original1988 nomogram review.](https://miyazaki-u.repo.nii.ac.jp/record/2000525/files/1-s2.0-S1752928X2300152X-main.pdf)

## Reproduire les tests techniques

Exécutez node test.cjs dans le répertoire racine de ce dépôt pour reproduire les cas synthétiques enregistrés. Les données d’entrée, les résultats attendus et les tolérances d’origine sont conservés. Les tests techniques ne constituent pas une validation clinique.

```sh
node test.cjs
```

tool.json contient les sources, l’édition et le périmètre de la revue. examples.json conserve les données d’entrée et les résultats attendus des cas synthétiques ; results.json consigne les résultats obtenus.

[Fiche et références](../tool.json) · [Code JavaScript](../calculator.js) · [Cas de référence](../examples.json) · [results.json](../results.json)

## Revue et conditions d’utilisation

Aucune révision clinique indépendante n’a été effectuée.

Cette interface est une traduction réalisée par nos soins, et non une édition officielle ou certifiée. La revue clinique indépendante, la révision linguistique professionnelle et l’autorisation des droits sur les instruments n’ont pas été réalisées.

Résultat de la formule ou de la classification. L’interprétation, la conduite et l’applicabilité dépendent de l’évaluation professionnelle et de la source sélectionnée.

## Licence et attribution

Apache-2.0 s’applique uniquement au code d’ELUCENIA. Les droits sur les instruments, publications, traductions et données restent ceux de leurs titulaires respectifs. Conservez LICENSE et NOTICE.

ELUCENIA · Felipe Guedes · Copyright © 2026
