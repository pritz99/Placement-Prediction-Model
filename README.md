# Placement Prediction Model

This project aims to predict student placement outcomes using machine learning. Several classification models, including **Logistic Regression, Random Forest, and XGBoost**, were tested with **hyperparameter tuning**. However, the results remained around **80% accuracy**, with no significant improvement from tuning.

---

## 1. Dataset Overview

The dataset contains student attributes such as **CGPA, internships, projects, workshops, aptitude test scores, and placement training participation**, among others. The target variable is **PlacementStatus**, which indicates whether a student was placed (`1`) or not (`0`).

### Columns Used
- **Numerical Features:** `CGPA`, `AptitudeTestScore`, `SSC_Marks`, `HSC_Marks`, etc.
- **Categorical Features (Converted to Dummies):**  
  - `Internships`, `Projects`, `Workshops/Certifications` → One-hot encoded because they contain only **2 to 3 unique values**.  
  - `PlacementTraining` as well as `Placement Status` (converted to `1` for "Yes" and `0` for "No").  

---

## 2. Data Preprocessing

✅ **Feature Engineering**:  
- Converted categorical variables into **dummy variables** using `pd.get_dummies()`.  
- Standardized numerical features using **StandardScaler** to ensure proper model convergence.  
- Checked for **multicollinearity** using **Variance Inflation Factor (VIF)** to confirm no strong correlations among independent variables.  

✅ **Train-Test Split**:  
- **80% training data**, **20% test data**.  
- **Data is balanced**, so no resampling techniques like SMOTE were required.  

---

## 3. Models & Results

| Model | Hyperparameter Tuning | Accuracy |
|--------|----------------------|------------|
| Logistic Regression | No | **80.35%** |
| Logistic Regression | Yes (GridSearchCV) | **79.89%** |
| Random Forest | No | **78.9%** |
| Random Forest | Yes (RandomizedSearchCV) | **79.76%** |
| XGBoost | Yes (RandomizedSearchCV) | **79.85%** |

### Observations:
- **Hyperparameter tuning did not significantly improve accuracy**.
- **Logistic Regression performed best** even without tuning.
- **Random Forest and XGBoost performed slightly worse than Logistic Regression** despite their ability to handle complex patterns.

---

## 4. Next Steps

Since accuracy is stuck at ~80%, potential improvements include:  
🔹 **Feature Selection**: Removing redundant features.  
🔹 **Trying Polynomial Features**: Adding non-linear terms for better learning.  
🔹 **Trying Other Models**: Experimenting with **Neural Networks** or **SVMs**.  

---

## 5. How to Run the Model

1️⃣ Clone the repository:
   ```bash
   git clone https://github.com/yourusername/placement-prediction.git
   cd placement-prediction

This is **ready to copy and paste** into your **README.md** file for GitHub. Let me know if you need any changes! 🚀
