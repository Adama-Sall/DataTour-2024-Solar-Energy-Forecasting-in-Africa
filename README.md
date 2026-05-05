# DataTour 2024 — Solar Energy Forecasting in Africa

## Contexte

L’accès à une énergie fiable reste un enjeu majeur dans plusieurs régions d’Afrique subsaharienne. Dans ce projet, l’objectif est de construire un modèle de **régression** capable de prédire la **demande énergétique projetée** à partir de variables géographiques, socio-économiques et environnementales.

Ce travail a été réalisé dans le cadre de **DataTour 2024** et s’inscrit dans une problématique de prévision énergétique appliquée au développement des infrastructures solaires.

## Objectif du projet

L’objectif principal est de :

- prédire la variable cible `demande_energetique_projectee` ;
- comparer plusieurs modèles de régression ;
- améliorer la performance via le feature engineering, la réduction de dimension et l’optimisation d’hyperparamètres ;
- produire des prédictions exploitables dans un fichier de soumission.

## Données utilisées

Le jeu de données est composé de trois fichiers :

- `train.csv` : ensemble d’entraînement contenant la cible ;
- `test.csv` : ensemble de test contenant aussi la cible pour l’évaluation ;
- `submission.csv` : ensemble final à prédire pour la soumission.

### Variables principales

Parmi les variables disponibles :

- `country`
- `lat`, `lon`
- `population`
- `tauxensoleillement`
- `demandeenergetiqueactuelle`
- `capaciteinstalleeactuelle`
- `dureeensoleillementannuel`
- `coutinstallationsolaire`
- `proximiteinfrastructuresenergetiques`
- `tauxadoptionenergiesrenouvelables`
- `stabilitepolitique`
- `tauxaccesenergie`
- `niveauurbanisation`
- `potentielinvestissement`
- `typessols`
- `emissionsco2evitees`
- `idh`
- `habitdemariage`
- `nombreanimauxdomestiques`

## Méthodologie

Le notebook suit les étapes suivantes :

1. **Importation et exploration des données**
   - analyse des dimensions ;
   - vérification des doublons ;
   - étude des valeurs manquantes ;
   - inspection des distributions.

2. **Analyse exploratoire**
   - étude univariée et bivariée ;
   - comparaison train/test ;
   - identification des variables informatives.

3. **Prétraitement**
   - encodage des variables catégorielles ;
   - standardisation des variables numériques ;
   - gestion des valeurs manquantes ;
   - réduction de dimension par **PCA**.

4. **Modélisation**
   - régression linéaire ;
   - Lasso ;
   - LightGBM ;
   - HistGradientBoosting ;
   - XGBoost ;
   - CatBoost ;
   - GradientBoostingRegressor ;
   - modèles d’ensemble et stacking.

5. **Optimisation**
   - recherche d’hyperparamètres avec **Optuna** ;
   - validation croisée en **KFold** ;
   - évaluation avec la métrique **RMSE**.

## Résultats

Les modèles ont été évalués via la **Root Mean Squared Error (RMSE)**.  
L’approche a inclus plusieurs essais de modèles individuels et d’ensembles afin d’identifier la stratégie la plus performante.

Les résultats intermédiaires ont montré l’intérêt :

- de la validation croisée ;
- de la combinaison de modèles ;
- de l’optimisation des paramètres ;
- de la préparation soignée des variables.

## Structure du dépôt

```bash
.
├── datatour_2024_solar_energy_forecasting.ipynb
├── README.md
└── assets/
```

## Technologies utilisées

- Python
- Jupyter Notebook
- NumPy
- pandas
- scikit-learn
- seaborn
- matplotlib
- XGBoost
- LightGBM
- CatBoost
- Optuna

## Installation

Cloner le dépôt :

```bash
git clone https://github.com/ton-compte/nom-du-repo.git
cd nom-du-repo
```

Installer les dépendances principales :

```bash
pip install numpy pandas scikit-learn seaborn matplotlib xgboost lightgbm catboost optuna
```

## Utilisation

1. Ouvrir le notebook `datatour_2024_solar_energy_forecasting.ipynb`.
2. Exécuter les cellules dans l’ordre.
3. Vérifier les étapes de preprocessing, de modélisation et de prédiction.
4. Générer les prédictions finales pour la soumission.

## Compétences mises en œuvre

Ce projet mobilise plusieurs compétences en data science :

- analyse exploratoire de données ;
- préparation et transformation de données ;
- modélisation supervisée ;
- évaluation de modèles ;
- optimisation d’hyperparamètres ;
- assemblage de modèles ;
- interprétation de résultats.

## Pistes d’amélioration

Plusieurs pistes peuvent encore être explorées :

- test de nouvelles méthodes d’encodage ;
- sélection plus fine des variables ;
- utilisation de modèles plus avancés ;
- amélioration du stacking ;
- analyse d’erreurs plus poussée.
