# Parameter-Optimization-of-SVM
# 🍷 SVM Optimization on UCI Wine Dataset

This project demonstrates the **optimization of Support Vector Machine (SVM)** classifiers on the UCI Wine dataset using limited training data. The goal is to determine the best hyperparameters (`kernel`, `C`, and `gamma`) through random search to maximize classification accuracy.

---

## 📁 Dataset Information

- **Name**: Wine Recognition Dataset  
- **Source**: [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/wine)
- **Number of Features**: 13  
- **Number of Rows**: 178  
- **Target Variable**: Wine class (1, 2, 3)

---

## 🧪 Methodology

1. **Data Loading**:  
   The dataset is loaded using `ucimlrepo` and split into features `X` and target `y`.

2. **Train-Test Split**:  
   For each of **10 random seeds**, the data is split into 70% test and 30% train sets.

3. **Limited Training Size**:  
   From each training split, only **50 samples** are selected to simulate low-resource training.

4. **Random Search Optimization**:  
   For each sample:
   - 100 random combinations of:
     - `kernel`: `'linear'`, `'poly'`, `'rbf'`, `'sigmoid'`
     - `C ∈ [0.1, 10.0]`
     - `gamma ∈ [0.001, 1.0]`
   - Accuracy is calculated on the test set for each combination.
   - The best combination is logged.

5. **Visualization**:  
   The best sample across all runs is visualized using a **convergence plot** that shows how the best accuracy improves over iterations.

---


## 📈 Convergence Plot

This plot represents the improvement in best accuracy over 100 iterations for the best-performing sample (among the 10 tested):

![Convergence Plot](output.png)

**Interpretation**:
- X-axis: Iteration number (logged every 10 iterations)
- Y-axis: Best accuracy found up to that iteration
- The plot reflects how progressively better hyperparameters are found

---

## 📌 Conclusion

- Even with just 50 training samples, careful hyperparameter tuning can yield high accuracies (above 95%).
- The `rbf` and `poly` kernels often outperform others on this dataset.
- Random search, although simple, is effective for finding optimal SVM parameters.

---


---
