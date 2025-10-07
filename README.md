# Analyse du catalogue Hipparcos

Ce projet utilise le fichier de données `hipparcos-voidmain.csv` (catalogue Hipparcos) pour explorer et analyser des propriétés stellaires. Le but est de préparer les données, d'explorer les relations astrophysiques, et d'expérimenter des méthodes de machine learning simples.

Contenu prévu

- Description du jeu de données et des colonnes importantes (RA, Dec, Plx, Vmag, SpType, etc.).
- Nettoyage et prétraitement :
  - Suppression des colonnes non pertinentes.
  - Traitement des valeurs manquantes (imputation par moyenne pour les colonnes numériques, suppression ou stratégies alternatives pour les colonnes catégorielles).
  - Conversion des types (par exemple, typage des identifiants en chaînes, conversion des magnitudes en numériques si nécessaire).
  - Détection et traitement des outliers.

- Exploration descriptive :
  - Statistiques de base (moyenne, médiane, écart-type, quartiles).
  - Histogrammes, boxplots et scatter plots pour visualiser distributions et corrélations.
  - Carte des positions célestes (RA/Dec) pour visualiser la distribution des étoiles.

- Feature engineering :
  - Calcul de la distance à partir de la parallaxe (attention aux unités et aux parallaxes nulles ou négatives).
  - Création d'indices de couleur et de catégories spectrales simplifiées (ex : première lettre de `SpType`).

- Machine Learning (expérimentations) :
  - Clustering (KMeans, DBSCAN) pour regrouper des étoiles selon leurs caractéristiques.
  - Classification simple : prédire le type spectral (ou une version réduite) à partir des caractéristiques photométriques et astrométriques.
  - Détection d'étoiles variables à partir des indicateurs de variabilité.

Dépendances minimales (Python)

- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn
- jupyter

Commandes utiles

- Lancer le notebook :

  jupyter notebook main.ipynb

- Installer les dépendances :

  pip install pandas numpy matplotlib seaborn scikit-learn jupyter

Notes et précautions

- La parallaxe peut contenir des zéros ou des valeurs négatives ; il faut gérer ces cas avant de calculer des distances (par ex. distance=1/(parallaxe/1000) en parsecs si la parallaxe est en millisecondes d'arc).
- Certaines colonnes peuvent avoir un pourcentage élevé de valeurs manquantes ; envisager de supprimer ces colonnes ou d'utiliser des méthodes d'imputation plus robustes.
- Conserver une copie du dataset brut avant toute modification.

Prochaines étapes

1. Valider le chargement du fichier et inspecter les colonnes.
2. Mettre en place le prétraitement de base (nettoyage, imputation, typage).
3. Générer des visualisations exploratoires et la matrice de corrélation.
4. Essayer des modèles de clustering et de classification basiques.

Auteur: (votre nom)
Date: 2025-10-07
