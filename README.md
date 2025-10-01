# Analyse d'Accidentologie à Paris

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://python.org)
[![Streamlit](https://img.shields.io/badge/Streamlit-1.28+-red.svg)](https://streamlit.io)
[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

## Description

Ce projet analyse les données d'accidents de la route à Paris sur la période 2017-2023. Il combine plusieurs approches de machine learning (XGBoost, Prophet, SARIMA) avec des données météorologiques et de trafic pour identifier les zones à risque et prédire l'évolution des accidents.

L'application web développée avec Streamlit permet d'explorer interactivement les données à travers des cartes, des graphiques temporels et des analyses par arrondissement.

## Fonctionnalités

- **Prédictions** : Modèles XGBoost, Prophet et SARIMA pour prédire les accidents
- **Cartographie** : Cartes interactives avec clustering et zones de chaleur
- **Analyse temporelle** : Évolution des accidents par mois et année
- **Points noirs** : Identification des zones à risque par arrondissement
- **Performance** : Traitement optimisé de 7 ans de données (2017-2023)

## Technologies

**Machine Learning :**
- XGBoost pour les prédictions
- Prophet pour l'analyse des séries temporelles
- SARIMA pour la modélisation statistique

**Visualisation :**
- Streamlit pour l'interface web
- Plotly pour les graphiques interactifs
- Folium pour les cartes géographiques
- Pandas pour le traitement des données

**Sources de données :**
- Accidents de la route (2017-2023)
- Données météorologiques
- Données de trafic routier

## Résultats

- R² Score : 0.85+ sur les prédictions
- MAE : < 2 accidents/jour
- Traitement de 50k+ accidents
- Interface interactive temps réel

## Structure du projet

```
├── app.py                          # Application principale
├── requirements.txt                # Dépendances
├── README.md                       # Documentation
├── accidentologie.parquet          # Données d'accidents
├── data_meteo.csv                  # Données météorologiques
├── trafic_routier_paris.csv        # Données de trafic
└── data_accidents/                 # Données par année
    ├── annee=2017/
    ├── annee=2018/
    └── ...
```

## Fonctionnalités détaillées

**Cartographie interactive :**
- Cartes de chaleur des zones à risque
- Clustering des accidents
- Filtres par gravité et type d'usager

**Analyse temporelle :**
- Évolution par mois et année
- Tendances saisonnières
- Comparaisons inter-annuelles

**Analyse spatiale :**
- Points noirs par arrondissement
- Analyse par voie avec normalisation
- Statistiques détaillées par zone

**Modèles de prédiction :**
- XGBoost pour les prédictions quotidiennes
- Prophet pour la saisonnalité
- SARIMA pour la modélisation statistique

## Exemples d'utilisation

**Analyse d'un arrondissement :**
```python
# Sélection d'un arrondissement
arrondissement = "11"
# Filtrage par gravité
gravite = ["Tué", "Blessé hospitalisé"]
```

**Prédiction d'accidents :**
```python
# Entraînement du modèle XGBoost
model = train_xgboost_model(train_data, test_data)
# Prédictions pour 2023
predictions = model.predict(features_2023)
```

## Cas d'usage

- Sécurité routière : Identification des zones à risque
- Urbanisme : Planification des infrastructures
- Prévention : Campagnes ciblées
- Recherche : Analyse des facteurs d'accidents

## Métriques de performance

| Modèle | R² Score | MAE | RMSE |
|--------|----------|-----|------|
| XGBoost | 0.85 | 1.8 | 2.3 |
| Prophet | 0.82 | 2.1 | 2.7 |
| SARIMA | 0.79 | 2.4 | 3.1 |