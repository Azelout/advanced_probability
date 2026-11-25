# Fiches de révision : Advanced Probabilities (M1, S1, V. M. Lambert)

Fiches en LaTeX, en français. Le terme anglais du cours est indiqué entre parenthèses quand il diffère.

- `preambule.tex` : préambule commun (environnements `definition`, `theoreme`, `proposition`, `lemme`,
  `remarque`, `horscours`, encadrés `piege`, `liens`, `methode`, `alerte`).
- `cours/` : 9 fiches de cours, une par chapitre des slides (vecteurs gaussiens et espérance conditionnelle à part).
- `td/` : 6 fiches de rappels, une par TD, à lire **avant** de chercher les exercices.

## Compilation

```sh
cd fiches/cours && latexmk -pdf *.tex
cd ../td        && latexmk -pdf *.tex
latexmk -c      # nettoie les fichiers auxiliaires (garde les PDF)
```

## Conventions

- **Numérotation** : un seul compteur par fiche, préfixé par la fiche. « C6.5 » désigne l'énoncé n°5 de la
  fiche C6 (ici, la proposition qui liste les propriétés de l'espérance conditionnelle). Les fiches de TD renvoient
  aux fiches de cours par ces numéros.
- **Hors cours** : tout résultat standard absent des documents du cours est signalé « Hors cours » ou « standard ».
- **% À VÉRIFIER** : commentaire LaTeX laissé dans le source là où le cours ou l'énoncé paraît incohérent
  (détail dans les encadrés « Attention à l'énoncé »).
- **Fiches de TD** : outils du cours, méthode et indication, sans corrigé rédigé. La « Réponse » est donnée seulement
  pour les calculs (valeur numérique ou formule finale), pour vous permettre de vérifier votre résultat.

## Liste des fiches

| Fiche | Fichier | Contenu | Source |
|---|---|---|---|
| C1 | `cours/C1_espaces_probabilises.tex` | Tribus, tribu engendrée, filtration, v.a., probabilité, probabilité conditionnelle, Bayes | slides ch. 1–3 |
| C2 | `cours/C2_mesure_integration.tex` | Lebesgue, comptage, négligeables, densités, transfert, lois usuelles | slides ch. 4 |
| C3 | `cours/C3_independance.tex` | Indépendance (événements, tribus, v.a.), Borel–Cantelli, mesure produit, densités | slides ch. 5 |
| C4 | `cours/C4_convergences.tex` | Fonction caractéristique, convergence en loi, Lévy, LGN, TCL, modes de convergence (hors cours) | slides ch. 6 (début) |
| C5 | `cours/C5_vecteurs_gaussiens.tex` | Gaussienne réelle, vecteurs gaussiens, 𝒩_d(m, K), indépendance ⇔ covariance nulle | slides ch. 6 + poly |
| C6 | `cours/C6_esperance_conditionnelle.tex` | 𝔼[X \| 𝒢] : définition, propriétés, partition, densités, cas gaussien | slides ch. 7 + 2 polys |
| C7 | `cours/C7_changement_de_loi.tex` | Absolue continuité, Radon–Nikodym, formule de Bayes conditionnelle | slides ch. 8 |
| C8 | `cours/C8_martingales_temps_arret.tex` | Processus, martingales, Doob, temps d'arrêt, théorème d'arrêt | slides ch. 9 |
| C9 | `cours/C9_processus_de_poisson.tex` | Processus ponctuel, comptage, Poisson, inter-arrivées exponentielles | slides ch. 10 + poly |
| TD1 | `td/TD1_tribus_probabilites.tex` | Tribus, compatibilité de probabilités, Bayes | C1 |
| TD2 | `td/TD2_mesure_transfert.tex` | Transfert, Poisson → exponentielle, log-normale | C2, C9, C5 |
| TD3 | `td/TD3_independance_convergence_gaussiens.tex` | Borel–Cantelli, convergences, TCL, vecteurs gaussiens, Black–Scholes | C3, C4, C5 |
| TD4 | `td/TD4_esperance_conditionnelle.tex` | Lois conditionnelles, max/min, régression gaussienne | C6, C3, C5 |
| TD5 | `td/TD5_martingales_poisson.tex` | Temps d'arrêt, martingales, Poisson, paradoxe de l'autobus | C8, C6, C9 |
| TD6 | `td/TD6_arret_optionnel.tex` | Martingales exponentielles, théorème d'arrêt, ruine | C8 |

## Corrigés

`corriges/` : corrigé rédigé complet de chaque TD, à lire **après** avoir cherché l'exercice avec la fiche de rappels.
Même numérotation que l'énoncé. Chaque étape renvoie au cours (« C6.5, point 6 »), précise le sens des égalités et
convergences (p.s., L^p, en loi) et vérifie les hypothèses. Les outils absents du cours sont signalés « Hors cours ».
Les énoncés douteux sont signalés par un encadré « Attention à l'énoncé » et un `% À VÉRIFIER` dans le source.
Chaque corrigé a été relu par un relecteur indépendant, qui a refait les calculs.

| Corrigé | Pages | Points d'énoncé signalés |
|---|---|---|
| `corriges/TD1_corrige.tex` | 4 | ex. 1.3 : sens de 𝒯₁ × 𝒯₂ (pavés) ; ex. 4 : « baisse » = complémentaire de « hausse » |
| `corriges/TD2_corrige.tex` | 5 | ex. 2 : processus de Poisson supposé ; application : conditionnement par {τ > 10} |
| `corriges/TD3_corrige.tex` | 10 | ex. 10 : « erf » = f.d.r. de 𝒩(0,1) ; facteur K manquant en IV.2 (et dans les paramètres de V.2) |
| `corriges/TD4_corrige.tex` | 6 | aucun ; ex. 3 : sens donné à « sachant {Y = y} » |
| `corriges/TD5_corrige.tex` | 9 | ex. 3C : « {τ = i} indépendant de 𝓕ᵢ » rend τ déterministe ; preuve donnée pour tout τ borné |
| `corriges/TD6_corrige.tex` | 6 | ex. 1 : indépendance des Zᵢ supposée ; ex. 2 : martingale seulement si p = ½, et P(X_T = 150) = 2/3 ≠ p (cas p ≠ ½ traité) |

```sh
cd fiches/corriges && latexmk -pdf *.tex && latexmk -c
```

## Ordre de révision conseillé

1. **C1 → TD1** : le vocabulaire de base.
2. **C2 → TD2** : intégrer et calculer des lois (le transfert sert partout ensuite).
3. **C3** : indépendance, prérequis de tout le reste.
4. **C4 → C5 → TD3** : convergences puis vecteurs gaussiens (le TD3 mélange les trois fiches C3–C5).
5. **C6 → TD4** : espérance conditionnelle, chapitre central de l'examen.
6. **C7** : court, mais réutilise C6 (formule de Bayes conditionnelle).
7. **C8 → C9 → TD5 → TD6** : martingales et temps d'arrêt, puis Poisson ; TD5 couvre les deux, TD6 approfondit l'arrêt.

Avant l'examen : relire tous les encadrés **« Pièges classiques »** et les tableaux **« type de question → méthode »**
à la fin de chaque fiche de TD.

## Points signalés dans les sources

- C2 : les slides écrivent ln(S_T/s₀) ∼ 𝒩(r, σ²T) dans l'exemple du call. Reproduit tel quel ; en Black–Scholes
  usuel, la moyenne serait (r − σ²/2)T.
- C8 : le théorème du temps d'entrée est énoncé dans les slides sans hypothèse ; en temps continu, il en faut
  (cas « processus continu, fermé » traité au TD5).
- C6 : la propriété « 𝔼(X 𝔼(Y|𝒢)) = 𝔼(XY) » est énoncée dans le cours sous la seule hypothèse 𝔼|X 𝔼(Y|𝒢)| < ∞,
  ce qui ne suffit pas à garantir que 𝔼(XY) existe. La fiche suppose 𝔼|XY| < ∞.
- TD3, ex. 10 : l'énoncé définit « erf » comme la fonction de répartition de 𝒩(0, 1) (notation non standard).
  Le facteur K manque en IV.2 (vérifié sur le PDF), et aussi dans la liste de paramètres de V.2.
- TD5, ex. 3 : « {τ = i} indépendant de 𝓕ᵢ » combiné à « τ temps d'arrêt » force τ déterministe ;
  la fiche propose deux lectures non dégénérées.
- TD6, ex. 1 : l'indépendance des Z_i n'est pas écrite dans l'énoncé.
- TD6, ex. 2 : l'énoncé affirme P(X_T = 150) = p. C'est faux en général : (X_n) n'est une martingale que si p = 1/2,
  et alors P(X_T = 150) = 2/3.
