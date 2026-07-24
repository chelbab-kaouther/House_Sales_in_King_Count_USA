# Final Project: House Sales in King County, USA

Projet final réalisé dans le cadre d'un cours de Data Analysis (IBM Skills Network) portant sur l'analyse et la prédiction des
prix de vente de maisons dans le comté de King County (Seattle, USA), en tant qu'analyste de données pour un fonds d'investissement immobilier.

## 📋 Description

Ce projet a pour objectif de déterminer le prix de marché d'une maison à partir d'un ensemble de caractéristiques 
(surface, nombre de chambres, étages, etc.). Le notebook couvre l'ensemble du pipeline d'un projet de data science : import des données, nettoyage, analyse exploratoire, modélisation et évaluation/amélioration de modèles de régression.

## 🎯 Objectifs pédagogiques

- Importer et explorer un jeu de données réel
- Nettoyer les données (gestion des valeurs manquantes, suppression de colonnes inutiles)
- Réaliser une analyse exploratoire de données (EDA) avec des visualisations statistiques
- Construire des modèles de régression linéaire et Ridge
- Évaluer et améliorer la performance des modèles (transformation polynomiale, pipelines, split train/test)

## 🗂️ Jeu de données

Le dataset contient les prix de vente de maisons dans le comté de King County (incluant Seattle), pour des ventes réalisées entre mai 2014 et mai 2015. Il est basé sur le dataset [House Sales in King County](https://www.kaggle.com/harlfoxem/housesalesprediction) de Kaggle, légèrement modifié pour les besoins du cours.

Principales colonnes du dataset :

| Variable | Description |
|---|---|
| id | Identifiant de la maison |
| date | Date de vente |
| price | Prix (variable cible) |
| bedrooms | Nombre de chambres |
| bathrooms | Nombre de salles de bain |
| sqft_living | Surface habitable (pieds carrés) |
| sqft_lot | Surface du terrain |
| floors | Nombre d'étages |
| waterfront | Vue sur un point d'eau |
| view | Qualité de la vue |
| condition | État général du bien |
| grade | Note globale attribuée selon le système de notation du comté |
| sqft_above | Surface hors sous-sol |
| sqft_basement | Surface du sous-sol |
| yr_built | Année de construction |
| yr_renovated | Année de rénovation |
| zipcode | Code postal |
| lat / long | Coordonnées géographiques |
| sqft_living15 / sqft_lot15 | Surfaces habitable/terrain en 2015 (après rénovations éventuelles) |

## 🛠️ Technologies utilisées

- Python 3
- [pandas](https://pandas.pydata.org/) — manipulation des données
- [numpy](https://numpy.org/) — calculs numériques
- [matplotlib](https://matplotlib.org/) & [seaborn](https://seaborn.pydata.org/) — visualisation de données
- [scikit-learn](https://scikit-learn.org/) — régression linéaire, régression Ridge, pipelines, transformation polynomiale, split train/test

## 📦 Installation

```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```

## 🚀 Utilisation

1. Cloner ce dépôt
2. Ouvrir le notebook `House_Sales_in_King_Count_USA_20231003_1696291200_jupyterlite.ipynb` avec Jupyter Notebook, JupyterLab, ou VS Code
3. Exécuter les cellules dans l'ordre

## 📊 Contenu du notebook

Le notebook est organisé en 5 modules :

### Module 1 — Import des données
Chargement du dataset depuis une URL et exploration initiale (`head()`, `dtypes`, `describe()`).

### Module 2 — Data Wrangling
Suppression des colonnes `id` et `Unnamed: 0`, identification et remplacement des valeurs manquantes des colonnes `bedrooms` et `bathrooms` par leur moyenne.

### Module 3 — Exploratory Data Analysis (EDA)
- Comptage du nombre de maisons par nombre d'étages (`value_counts()`)
- Boxplot comparant les prix selon la présence d'une vue sur l'eau (`waterfront`)
- Regplot pour étudier la corrélation entre `sqft_above` et le prix
- Calcul de la corrélation entre toutes les variables numériques et le prix

### Module 4 — Model Development
- Régression linéaire simple sur `long`, puis sur `sqft_living`
- Régression linéaire multiple sur une liste de features (floors, waterfront, lat, bedrooms, etc.)
- Construction d'un pipeline (`StandardScaler` + `PolynomialFeatures` + `LinearRegression`)

### Module 5 — Model Evaluation and Refinement
- Séparation des données en jeu d'entraînement et de test (85%/15%)
- Régression Ridge (alpha = 0.1) évaluée sur le jeu de test
- Transformation polynomiale de degré 2 combinée à une régression Ridge


## 📄 Licence

Ce notebook est basé sur un projet éducatif © IBM Corporation 2020, utilisé ici à des fins d'apprentissage personnel.
