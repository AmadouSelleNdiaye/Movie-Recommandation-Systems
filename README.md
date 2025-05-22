# Movie Recommendation Systems

This project explores and compares two classic recommendation approaches:  
- **Collaborative filtering** (based on user similarities).  
- **Content-based filtering** (using movie genres and clustering).  

---

## 📌 Objective  
This practical work aims to design and compare two recommendation systems:  
1. **User-based collaborative filtering**.  
2. **Content-based filtering** using clustering.  

The data comes from [MovieLens](http://movielens.org) and includes movie ratings (`ratings.csv`) and metadata (`movies.csv`).  

---

## 📂 File Structure  
- **Original Data**:  
  - `movies.csv`: List of movies with their genres.  
  - `ratings.csv`: User ratings (1-5 stars).  
- **Cleaned Data**:  
  - `movies1.csv`, `ratings1.csv`: Filtered files (removing movies without genres and rounding ratings).  
- **Evaluation Subsets**:  
  - Option 1: `ratings_training.csv` (80%) and `ratings_test.csv` (20%).  
  - Option 2: 5 files of 20% each (`ratings_part1.csv`, etc.) for cross-validation.  

---

## 🔧 Tasks  

### 1. Descriptive Statistics  
- **Bar chart**: Visualize genre distribution (excluding `(no genres listed)`).  

### 2. Data Cleaning  
- Remove movies without genres and adjust ratings (e.g., `5.5` → `5`).  
- Generate `movies1.csv` and `ratings1.csv`.  

### 3. Content Matrix  
- Build a **binary matrix `C`** where each row represents a movie and each column a genre (`1` if the movie belongs to the genre, `0` otherwise).  

### 4. User Profiles  
- Compute the profile matrix `P` as a linear combination of ratings and matrix `C`.  
- **Normalization**: Profiles must be normalized for subsequent steps.  

### 5. Evaluation Data Preparation  
- Split `ratings1.csv` into training (80%) and test (20%) sets.  

### 6. Collaborative Filtering  
- **Similarity**: Use Pearson correlation to find similar users.  
- **Prediction**: Estimate ratings by averaging neighbors' ratings.  
- **Evaluation**: Compare predicted vs. actual ratings (mean error).  

### 7. Content-Based Filtering (Clustering)  
- Apply clustering (e.g., K-means + silhouette) to profiles `P`.  
- **Recommendation**: Propose a cluster-based movie recommendation method.  
- **Evaluation**: Similar to Task 6.  

### 8. Alternative Approach (Bonus)  
- Propose a simple content-based algorithm (e.g., Bayesian or k-NN).  
