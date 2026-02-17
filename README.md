# Numerical-solution-of-ordinary-differential-equations

## Description
Ce projet implémente une résolution numérique de l'équation de la chaleur instationnaire en dimension 1. Il a été réalisé dans le cadre du module "Analyse Matricielle Appliquée" (L3 Ingénierie Mathématique).

L'objectif principal est de comparer la performance de différents algorithmes itératifs pour la résolution de systèmes linéaires, tout en optimisant la gestion de la mémoire via des structures de matrices creuses.

## Contenu Mathématique 
* **Modèle physique :** Équation aux dérivées partielles parabolique :
  $$\frac{\partial u}{\partial t} - \mu \frac{\partial^2 u}{\partial x^2} = 0$$
  avec conditions aux limites de Dirichlet homogènes.
* **Discrétisation :**
  * **Espace :** Différences finies sur un maillage régulier ($N$ points).
  * **Temps :** Schéma implicite (Euler rétrograde) garantissant la stabilité inconditionnelle.
* **Algèbre Linéaire :** Le problème se ramène à résoudre à chaque pas de temps un système linéaire $Ax = b$ où la matrice $A$ est symétrique définie positive.

## Implémentation Technique (C++) 
### Algorithmes de Résolution
Implémentation "from scratch" de trois méthodes itératives :
1.  **Gradient à Pas Simple** (Fixed Step Gradient).
2.  **Gradient à Pas Optimal** (Steepest Descent).
3.  **Gradient Conjugué** (Conjugate Gradient) - *Méthode la plus efficace implémentée.*

### Optimisation & Structures de Données
Comparaison de deux approches de stockage pour la matrice du système :
* **Stockage Dense :** Matrice complète (coûteux en mémoire).
* **Stockage Creux (Sparse) :** Structure optimisée ne stockant que les diagonales non nulles (seulement 7 valeurs nécessaires pour reconstruire la matrice), permettant de traiter des maillages très fins ($N >> 1000$).

## Analyse de Performance 
Une étude a été menée sur :
* **La précision :** Calcul de l'erreur en norme $L^\infty$ par rapport à la solution exacte analytique.
* **La complexité :** Comparaison des temps de calcul et de l'occupation mémoire pour des maillages de taille croissante ($N=32 \times 2^i$).

## Visualisation 
Les résultats numériques sont exportés et visualisés à l'aide de **Gnuplot** pour observer l'évolution du profil de température et la convergence vers la solution stationnaire.

## Auteur
**Paul LABORDE** - Étudiant en L3 Ingénierie Mathématique - Université de Bordeaux.
