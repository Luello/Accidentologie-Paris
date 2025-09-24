# 🚨 Analyse d'Accidentologie à Paris

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://python.org)
[![Streamlit](https://img.shields.io/badge/Streamlit-1.28+-red.svg)](https://streamlit.io)
[![Data Science](https://img.shields.io/badge/Data%20Science-ML-green.svg)](https://scikit-learn.org)
[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

## 📊 Aperçu du projet

Application d'analyse d'accidentologie à Paris développée avec Streamlit, combinant **machine learning** et **visualisation interactive** pour analyser et prédire les accidents de la route.

### 🎯 Fonctionnalités principales

- **📈 Prédictions ML** : Modèles XGBoost, Prophet et SARIMA
- **🗺️ Cartographie interactive** : Cartes de chaleur et clustering
- **📊 Visualisations avancées** : Graphiques temporels et statistiques
- **🔍 Analyse spatiale** : Points noirs par arrondissement et voie
- **⚡ Performance optimisée** : Traitement de 7 ans de données

## 🚀 Technologies utilisées

### Machine Learning
- **XGBoost** : Modèle de prédiction principal
- **Prophet** : Analyse des séries temporelles
- **SARIMA** : Modélisation statistique avancée

### Visualisation & Interface
- **Streamlit** : Interface utilisateur interactive
- **Plotly** : Graphiques interactifs
- **Folium** : Cartes géographiques
- **Pandas** : Manipulation de données

### Données
- **Accidents** : 7 ans de données (2017-2023)
- **Météo** : Température, précipitations, vent
- **Trafic** : Débit et concentration routière

## 📈 Résultats techniques

- **R² Score** : 0.85+ sur les prédictions
- **MAE** : < 2 accidents/jour
- **Performance** : Traitement de 50k+ accidents
- **Visualisation** : Cartes interactives temps réel

## 🛠️ Installation

### Prérequis
```bash
Python 3.8+
```

### Installation des dépendances
```bash
pip install -r requirements.txt
```

### Lancement de l'application
```bash
streamlit run app.py
```

L'application sera accessible sur `http://localhost:8501`

## 📁 Structure du projet

```
Geo_tree/
├── app.py                          # Application principale Streamlit
├── requirements.txt                # Dépendances Python
├── README.md                       # Documentation
├── documentation_technique.md      # Documentation technique
├── accidentologie.parquet          # Données d'accidents optimisées
├── data_meteo.csv                  # Données météorologiques
├── trafic_routier_paris.csv        # Données de trafic
└── data_accidents/                 # Données brutes par année
    ├── annee=2017/
    ├── annee=2018/
    └── ...
```

## 🎨 Fonctionnalités détaillées

### 1. Cartographie interactive
- **Carte de chaleur** des zones à risque
- **Clustering** des accidents
- **Filtres** par gravité et type d'usager
- **Zoom** et navigation fluide

### 2. Analyse temporelle
- **Évolution animée** par mois/année
- **Tendances** saisonnières
- **Comparaisons** inter-annuelles
- **Prédictions** futures

### 3. Analyse spatiale
- **Points noirs** par arrondissement
- **Analyse par voie** avec normalisation
- **Statistiques** détaillées
- **Évolution** temporelle par zone

### 4. Modèles de prédiction
- **XGBoost** : Prédictions quotidiennes
- **Prophet** : Saisonnalité et tendances
- **SARIMA** : Modélisation statistique
- **Validation** croisée et métriques

## 🔧 Optimisations techniques

### Performance
- **Format Parquet** pour les données
- **Types optimisés** (datetime64, categories)
- **Filtrage précoce** des données
- **Cache Streamlit** pour les calculs lourds

### Qualité des données
- **Nettoyage** automatique des adresses
- **Normalisation** des voies (Levenshtein)
- **Validation** des coordonnées
- **Gestion** des valeurs manquantes

## 📊 Exemples d'utilisation

### Analyse d'un arrondissement
```python
# Sélection d'un arrondissement
arrondissement = "11"
# Filtrage par gravité
gravite = ["Tué", "Blessé hospitalisé"]
# Visualisation des points noirs
```

### Prédiction d'accidents
```python
# Entraînement du modèle XGBoost
model = train_xgboost_model(train_data, test_data)
# Prédictions pour 2023
predictions = model.predict(features_2023)
```

## 🎯 Cas d'usage

- **Sécurité routière** : Identification des zones à risque
- **Urbanisme** : Planification des infrastructures
- **Prévention** : Campagnes ciblées
- **Recherche** : Analyse des facteurs d'accidents

## 📈 Métriques de performance

| Modèle | R² Score | MAE | RMSE |
|--------|----------|-----|------|
| XGBoost | 0.85 | 1.8 | 2.3 |
| Prophet | 0.82 | 2.1 | 2.7 |
| SARIMA | 0.79 | 2.4 | 3.1 |

## 🔮 Évolutions possibles

- **API REST** pour les données
- **Base de données** PostgreSQL
- **Cache Redis** pour les performances
- **Tests automatisés** pytest
- **Déploiement** Docker
- **Monitoring** des performances

## 📝 Documentation technique

Voir [documentation_technique.md](documentation_technique.md) pour :
- Architecture détaillée
- Algorithmes utilisés
- Optimisations
- Bonnes pratiques

## 🤝 Contribution

Les contributions sont les bienvenues ! Pour contribuer :

1. Fork le projet
2. Créez une branche (`git checkout -b feature/AmazingFeature`)
3. Committez vos changements (`git commit -m 'Add AmazingFeature'`)
4. Push vers la branche (`git push origin feature/AmazingFeature`)
5. Ouvrez une Pull Request

## 📄 Licence

Ce projet est sous licence MIT. Voir le fichier [LICENSE](LICENSE) pour plus de détails.

## 👨‍💻 Auteur

**Votre nom** - [@votre-github](https://github.com/votre-github)

## 🙏 Remerciements

- **OpenData Paris** pour les données d'accidents
- **Météo France** pour les données météorologiques
- **Communauté Streamlit** pour l'inspiration

---

⭐ **N'hésitez pas à donner une étoile si ce projet vous a aidé !**