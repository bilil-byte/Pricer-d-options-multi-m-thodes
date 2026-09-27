# Pricer d'options multi-méthodes : Arbre binomial, Black-Scholes, Monte Carlo

Projet Python de pricing d'options par trois méthodes indépendantes : arbre binomial CRR, formule analytique de Black-Scholes, et simulation Monte Carlo avec démonstration numérique de leur convergence et de leur cohérence croisée.

## Contexte

Ce projet fait suite à l'étude des chapitres 12, 13 et 14 de *Options, Futures and Other Derivatives* (J. Hull) : arbres binomiaux, processus de Wiener et lemme d'Itô, modèle de Black-Scholes-Merton.

## Objectif

Construire un pricer d'options via trois méthodes indépendantes, puis quantifier numériquement leur convergence et leur cohérence. Au-delà du pricing, l'accent est mis sur une démarche de **validation de modèle** : chaque résultat obtenu par une méthode est, autant que possible, vérifié par une autre (cohérence croisée, parité call-put, ordre de convergence théorique, Greeks analytiques vs. différences finies).

## Contenu du notebook

| Module | Contenu 
|---|---|
| 1. Arbre binomial CRR | Options européennes et américaines, exercice anticipé
| 2. Black-Scholes analytique | Prix + Greeks (Delta, Gamma, Vega, Theta, Rho) 
| 3. Convergence arbre - Black-Scholes | Étude log-log de l'erreur de discrétisation 
| 4. Monte Carlo | Simulation de trajectoires (mouvement brownien géométrique), intervalle de confiance, réduction de variance
| 5. Lemme d'Itô | Vérification numérique du drift et de la diffusion de ln(Sₜ)
| 6. Convergence Monte Carlo et Greeks | Vitesse de convergence de MC, comparaison Greeks analytiques vs. différences finies 

## Paramètres de référence

Sauf mention contraire, tous les modules utilisent le même jeu de paramètres, afin de pouvoir comparer directement les résultats d'une méthode à l'autre :

```
S0 = 100    # prix spot du sous-jacent
K  = 100    # strike
T  = 1      # maturité
r  = 0.05   # taux sans risque
σ  = 0.20   # volatilité annualisée
q  = 0      # taux de dividende
```

## Technologies

```
numpy
scipy
matplotlib
```



## Limites et perspectives

Ce travail valide la **cohérence interne** du modèle Black-Scholes et de son infrastructure numérique — il ne constitue pas une validation du modèle au sens propre, c'est-à-dire une confrontation à des données de marché réelles. Une suite naturelle serait d'étudier la volatilité implicite et le smile de volatilité observés sur le marché, afin de tester empiriquement les hypothèses de Black-Scholes (volatilité constante notamment), ou d'étudier la performance réelle d'une couverture delta-neutre construite à partir de ce modèle.

## Auteur

Lilian Nkwemfo
