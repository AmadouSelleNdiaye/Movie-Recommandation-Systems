# Movie-Recommandation-Systems
Ce projet vise à explorer et comparer deux approches classiques de recommandation :   - Filtrage collaboratif (basé sur les similarités entre utilisateurs).   - Filtrage basé sur le contenu (utilisant les genres des films et le clustering).

---

## 📌 Objectif  
Ce travail pratique vise à concevoir et comparer deux systèmes de recommandation :  
1. **Filtrage collaboratif** basé sur les utilisateurs.  
2. **Filtrage basé sur le contenu** utilisant le clustering.  

Les données proviennent de [MovieLens](http://movielens.org) et incluent des évaluations de films (`ratings.csv`) et leurs métadonnées (`movies.csv`).  

---

## 📂 Structure des fichiers  
- **Données originales** :  
  - `movies.csv` : Liste des films avec leurs genres.  
  - `ratings.csv` : Évaluations des films par les utilisateurs (notes sur 5 étoiles).  
- **Données nettoyées** :  
  - `movies1.csv`, `ratings1.csv` : Fichiers filtrés (sans films sans genre et notes arrondies).  
- **Sous-ensembles pour évaluation** :  
  - Option 1 : `ratings_apprentissage.csv` (80%) et `ratings_evaluation.csv` (20%).  
  - Option 2 : 5 fichiers de 20% chacun (`ratings_partie1.csv`, etc.) pour une validation croisée.  

---

## 🔧 Travail à réaliser  

### 1. Statistiques descriptives  
- **Diagramme en bâton** : Visualiser la distribution des films par genre (en excluant `(no genres listed)`).  

### 2. Nettoyage des données  
- Supprimer les films sans genre et ajuster les notes (ex: `5.5` → `5`).  
- Générer `movies1.csv` et `ratings1.csv`.  

### 3. Matrice de contenu  
- Construire une **matrice binaire `C`** où chaque ligne représente un film et chaque colonne un genre (ex: `1` si le film appartient au genre, `0` sinon).  

### 4. Profils des utilisateurs  
- Calculer la matrice de profil `P` comme une combinaison linéaire des évaluations et de la matrice `C`.  
- **Normalisation** : Les profils doivent être normalisés pour les étapes suivantes.  

### 5. Préparation des données d'évaluation  
- Diviser `ratings1.csv` en données d'apprentissage (80%) et d'évaluation (20%).  

### 6. Filtrage collaboratif  
- **Similarité** : Utiliser la corrélation de Pearson pour trouver des utilisateurs similaires.  
- **Prédiction** : Estimer les notes via le moyennage des notes des voisins.  
- **Évaluation** : Comparer les notes prédites avec les notes réelles (erreur moyenne).  

### 7. Filtrage basé sur le contenu (clustering)  
- Appliquer un algorithme de clustering (ex: K-moyennes + silhouette) sur les profils `P`.  
- **Recommandation** : Proposer une méthode pour recommander des films basée sur les clusters.  
- **Évaluation** : Similaire au point 6.  

### 8. Approche alternative (Bonus)  
- Proposer un algorithme simple de filtrage basé sur le contenu (ex: Bayesien ou k-NN).  