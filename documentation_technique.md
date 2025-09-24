# Documentation Technique - Analyse d'Accidentologie à Paris

## 1. Technologies Utilisées

### Framework Principal
- **Streamlit** : Framework Python pour la création d'applications web data-driven
  - Avantages : 
    - Développement rapide d'interfaces
    - Intégration native avec pandas et plotly
    - Rechargement automatique lors des modifications
    - Widgets interactifs prêts à l'emploi

### Manipulation de Données
- **Pandas** :
  - Utilisé pour :
    - Chargement et prétraitement des données
    - Agrégations et groupements
    - Filtrage dynamique
    - Calculs statistiques
  - Points forts :
    - Performance sur grands jeux de données
    - Fonctions d'agrégation puissantes
    - Gestion efficace de la mémoire

### Visualisation
- **Plotly** :
  - Types de graphiques utilisés :
    - Cartes de chaleur (heatmaps)
    - Graphiques linéaires pour l'évolution temporelle
    - Graphiques à barres empilées
  - Avantages :
    - Interactivité native
    - Personnalisation poussée
    - Export possible en HTML

- **Folium** :
  - Utilisé pour :
    - Cartes interactives
    - Clustering de marqueurs
    - Superposition de couches
  - Basé sur Leaflet.js avec tuiles OpenStreetMap

## 2. Architecture du Code

### Structure des Données
```python
# Principales colonnes du DataFrame
- date : Date et heure de l'accident
- latitude/longitude : Coordonnées géographiques
- type_usager : Type d'usager impliqué
- gravite_combinee : Niveau de gravité
- arrondissement : Arrondissement de Paris
- Adresse : Adresse complète
```

### Prétraitement des Données
1. **Nettoyage des adresses** :
   ```python
   def clean_address(address):
       # Supprime tout avant la virgule
       parts = address.split(',', 1)
       return parts[1].strip() if len(parts) > 1 else address.strip()
   ```

2. **Normalisation des voies** :
   - Utilisation de l'algorithme de Levenshtein
   - Seuil de similarité à 20%
   - Regroupement des variations orthographiques

### Fonctionnalités Principales

1. **Analyse par Arrondissement** :
   - Carte interactive avec clustering
   - Heatmap des accidents
   - Statistiques détaillées
   - Points noirs d'accidentologie

2. **Analyse par Voie** :
   - Évolution temporelle
   - Répartition par gravité
   - Statistiques détaillées par voie

## 3. Points Techniques Importants

### Performance
1. **Optimisation des données** :
   - Conversion CSV vers Parquet
   - Types de données optimisés
   - Indexation des colonnes clés

2. **Gestion de la mémoire** :
   - Filtrage précoce des données
   - Utilisation de `.copy()` pour éviter les modifications involontaires
   - Nettoyage des données temporaires

### Algorithmes Clés

1. **Distance de Levenshtein** :
   ```python
   def levenshtein_distance(s1, s2):
       # Calcul de la distance d'édition
       # Utilisé pour la normalisation des noms de voies
   ```

2. **Clustering des accidents** :
   - Utilisation de MarkerCluster de Folium
   - Paramètres optimisés pour la visualisation

### Visualisation des Données

1. **Cartes** :
   - Marqueurs colorés par gravité
   - Clustering dynamique
   - Popups informatifs

2. **Graphiques** :
   - Échelles de couleurs cohérentes
   - Légendes explicites
   - Interactivité (zoom, hover, etc.)

## 4. Points Forts pour l'Entretien

### Aspects Techniques
1. **Traitement des Données** :
   - Nettoyage et normalisation robustes
   - Gestion efficace des données manquantes
   - Optimisation des performances

2. **Visualisation** :
   - Multiple types de représentations
   - Interface intuitive
   - Interactivité poussée

3. **Code** :
   - Structure modulaire
   - Fonctions réutilisables
   - Documentation claire

### Aspects Fonctionnels
1. **Analyse Spatiale** :
   - Identification des zones à risque
   - Cartographie interactive
   - Analyse multi-échelles (arrondissement, voie)

2. **Analyse Temporelle** :
   - Évolution des accidents
   - Tendances par période
   - Comparaisons annuelles

3. **Interface Utilisateur** :
   - Navigation intuitive
   - Filtres dynamiques
   - Affichage adaptatif

## 5. Questions Potentielles et Réponses

1. **"Comment avez-vous géré la performance avec un grand volume de données ?"**
   - Utilisation du format Parquet
   - Optimisation des types de données
   - Filtrage efficace des données

2. **"Pourquoi avoir choisi Streamlit ?"**
   - Développement rapide
   - Intégration native avec les outils data
   - Déploiement simple
   - Interface utilisateur intuitive

3. **"Comment améliorer encore l'application ?"**
   - Ajout de prédictions (machine learning)
   - Optimisation du clustering
   - Ajout de nouvelles visualisations
   - API pour les données en temps réel

4. **"Comment gérez-vous la qualité des données ?"**
   - Nettoyage automatisé des adresses
   - Normalisation des noms de voies
   - Validation des coordonnées géographiques
   - Gestion des valeurs manquantes

## 6. Bonnes Pratiques Implémentées

1. **Code** :
   - Fonctions documentées
   - Noms explicites
   - Structure modulaire
   - Gestion des erreurs

2. **Données** :
   - Validation des entrées
   - Nettoyage systématique
   - Format optimisé
   - Backups et versioning

3. **Interface** :
   - Messages d'aide
   - Feedback utilisateur
   - Navigation intuitive
   - Responsive design

## 7. Évolutions Possibles

1. **Techniques** :
   - Migration vers une base de données
   - API REST pour les données
   - Cache Redis pour les requêtes fréquentes
   - Tests automatisés

2. **Fonctionnelles** :
   - Prédictions de zones à risque
   - Comparaison entre arrondissements
   - Export des données
   - Rapports automatisés

3. **Interface** :
   - Mode sombre
   - Plus de personnalisation
   - Tableaux de bord personnalisables
   - Version mobile optimisée 