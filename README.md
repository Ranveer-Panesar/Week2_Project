# Heart Disease Prediction Project: Workflow & Analysis

## Project Overview
This project provides a comprehensive machine learning analysis of the **Heart Disease UCI** dataset, covering the full pipeline from raw data acquisition to model interpretation.

## 🛠 Project Highlights & Workflow

### 1. Data Acquisition & Cleaning
- **Source:** Kaggle (`heart-disease-data`).
- **Feature Selection:** The column `ca` was dropped due to high sparsity (~65% missing values).
- **Imputation Strategy:** 
    - **Categorical:** Mode imputation for `slope`, `thal`, `fbs`, `restecg`, and `exang`.
    - **Numerical:** Median imputation for `oldpeak`, `chol`, `trestbps`, and `thalch`.
- **Encoding:** Applied **Label Encoding** for binary features and **One-Hot Encoding** for multi-categorical features to prepare data for tree-based models.

### 2. Modeling Strategy: Tree vs. Forest
We compared a single **Decision Tree** against a **Random Forest (100 estimators)** to evaluate the benefits of ensemble learning.
- **Performance Comparison:**
    - **Random Forest:** ~60% Accuracy. More robust and better at generalizing across classes.
    - **Decision Tree:** ~51% Accuracy. Useful for interpretability but prone to lower accuracy in this multiclass setting.
- **Observation:** Both models excel at identifying healthy patients (Class 0) but show difficulty with disease severity (1-4) due to significant class imbalance.

### 3. Feature Importance & Interpretation
Using the Random Forest's `feature_importances_`, we identified the primary predictors of heart disease:
1. **thalch** (Maximum Heart Rate)
2. **age**
3. **chol** (Cholesterol)

### 4. Visualizing Decisions
We generated a high-level visualization of an individual decision tree (depth 3) to map out how clinical attributes like `thalch` and `oldpeak` lead to specific diagnosis paths.

---
