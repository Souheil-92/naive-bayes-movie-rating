# IMDb Movie Sentiment Classifier 🎬

## Description
Ce projet de Machine Learning a pour but de prédire si un film est considéré comme "Bien" (1) ou "Pas bien" (0) en se basant sur ses statistiques IMDb[cite: 3]. Le modèle utilise l'algorithme **Multinomial Naive Bayes** de `scikit-learn` et inclut un menu interactif en ligne de commande pour tester les prédictions sur des films spécifiques[cite: 3].

## Nettoyage et Ingénierie des Données (Feature Engineering)
Le dataset original (`IMDB-Movie-Data.csv`) a été retravaillé pour optimiser les performances du modèle :
* **Gestion des valeurs manquantes** : Les valeurs absentes de la colonne `Metascore` ont été remplacées par la moyenne[cite: 3].
* **Normalisation (Min-Max)** : Les colonnes `Votes` et `Metascore` ont été mises à l'échelle pour être comparables[cite: 3].
* **Création de variables (Features)** : 
  * Un ratio `adjusted_rating` a été calculé en divisant le `Rating` par les `Votes`[cite: 3].
  * Un `score` final a été créé en pondérant équitablement l'évaluation ajustée (50%) et le Metascore (50%)[cite: 3].
* **Variable cible** : La classe `sentiment` a été définie dynamiquement : 1 si le score est supérieur à la médiane du dataset, 0 sinon[cite: 3].

## Modélisation et Évaluation
* **Modèle** : `MultinomialNB` (Naïve Bayes Multinomial)[cite: 3].
* **Séparation des données** : 80% pour l'entraînement, 20% pour le test[cite: 3].
* **Métriques de performance évaluées** :
  * Matrice de confusion affichée visuellement avec `seaborn`[cite: 3].
  * Rapport de classification incluant le F1-Score, la Précision et le Rappel[cite: 3].

## Fonctionnalité Interactive
Le script inclut une boucle interactive (Menu) permettant à l'utilisateur de :
1. Entrer le titre d'un film présent dans la base de données[cite: 3].
2. Obtenir une prédiction instantanée du modèle ("BIEN" ou "PAS BIEN")[cite: 3].

## Installation et Utilisation
1. Clonez ce dépôt :
   `git clone https://github.com/votre-nom-utilisateur/imdb-movie-sentiment-classifier.git`
2. Installez les bibliothèques requises (Pandas, NumPy, Matplotlib, Seaborn, Scikit-Learn)[cite: 3].
3. Exécutez le script ou le notebook en vous assurant que le fichier `IMDB-Movie-Data.csv` se trouve dans le même répertoire[cite: 3].

## Auteur
[Ton Prénom / Ton Nom]
