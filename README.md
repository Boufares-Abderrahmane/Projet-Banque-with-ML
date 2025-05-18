# Analyse Prédictive des Données Bancaires avec Machine Learning

## Objectif du rapport
Ce projet a pour but de prédire l'obtention d'un prêt personnel à partir de données clients d'une banque fictive, à l'aide de méthodes de Machine Learning.  
Il combine une phase d’exploration de données approfondie et une modélisation prédictive pour identifier les profils les plus susceptibles d’obtenir un prêt.

## Données utilisées
L'échantillon contient 4894 clients avec les variables suivantes :
- Âge
- Années d'expérience
- Revenu mensuel par millier
- Nombre de personnes par famille
- Dépenses mensuelles
- Niveau d'éducation (1 à 3)
- Possession d’un compte d’épargne logement
- Statut de prêt personnel (oui/non)

Seulement 9,78% des clients de l'échantillon ont obtenu un prêt personnel.

## Analyse exploratoire (EDA)
- Étude de la distribution de chaque variable
- Tests statistiques pour identifier les corrélations significatives
- Visualisations : histogrammes, boxplots, diagrammes empilés
- Variables significativement corrélées à l’obtention d’un prêt :
  - Revenu par millier
  - Dépenses mensuelles
  - Niveau d’éducation
  - Taille de la famille
  - Compte épargne logement

## Modélisation
Plusieurs modèles ont été testés et comparés :
| Modèle                | Précision | Rappel    | AUC        |
|-----------------------|-----------|-----------|------------|
| Régression Logistique | 48.5%     | 91.6%     | 0.9657     |
| Probit                | 48.5%     | 91.6%     | 0.9658     |
| Log-Log               | 53.4%     | 87.5%     | 0.9604     |
| **Arbre de Décision** | **63.1%** | **98.6%** | **0.9811** |
| SVM                   | 46.6%     | 90.6%     | 0.9603     |

**Modèle retenu : Arbre de décision**  
 - Meilleur compromis entre rappel, précision et taux de bonne classification.  
 - Interprétable grâce aux conditions de segmentation.

##  Importance des variables (selon l'arbre)
- Revenu mensuel : ~70%
- Taille de la famille : ~15%
- Niveau d’éducation : ~12%
- Dépenses mensuelles : ~10%

##  Validation
- Matrice de confusion : 98,6% de bonne classification sur les clients ayant obtenu un prêt
- Testé sur une base de nouveaux clients : prédictions cohérentes

## Outils & technologies
- Python
- Pandas, NumPy
- Matplotlib, Seaborn
- Scikit-learn
- Modèles : Logistic Regression, Decision Tree, SVM

## Structure du projet
│
├── 1-Bivarié.ipynb # Notebook d’exploration bivariée (analyse des relations entre variables)
├── 2-Modele.ipynb # Notebook de modélisation machine learning
├── 1-banque.csv # Données anonymisées utilisées
├── 2-Banque_Nvlle.csv # Données anonymisées nouvelles pour lesquelles ont souhaite avoir des prédictions
├── Rapport.pdf # Explication des variables, méthodes et résultats
├── README.md # Présentation du projet (ce fichier)
└── requirements.txt