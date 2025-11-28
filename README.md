# Credit Card Approval Prediction (Classification)

##  Project Goal

The objective of this project was to build a robust **binary classification model** (Logistic Regression) to predict the likelihood of credit card approval (class 1) or denial (class 0). The focus was on mastering **data preprocessing techniques** to handle a classic, anonymized, and dirty financial dataset.

##  Key Performance Summary

The **Logistic Regression** model, after meticulous preprocessing, delivered an **excellent** and highly reliable performance, indicating strong separation of the approved and denied classes.

| Metric | Denied (0) | Approved (1) | Overall Score |
| :--- | :--- | :--- | :--- |
| **Accuracy** | - | - | 86.2% |
| **F1-Score (Approved)** | 0.88 | **0.85** | - |
| **ROC AUC Score** | \multicolumn{2}{|c|}{Model's ability to discriminate classes} | **0.9470 (Excellent)** |

---

##  Detailed Methodology and Pipeline

The project involved critical steps to prepare the raw, anonymized data for modeling.

### 1 Data Cleaning and Imputation

* **Non-Standard Missing Values:** The dataset contained missing values marked as **`?`**, which were successfully converted to `NaN` during loading.
* **Imputation Strategy:**
    * **Numerical Features (e.g., A14):** Imputed with the **Mean** value.
    * **Categorical Features (e.g., A1, A4):** Imputed with the **Mode** (most frequent category).
* **Type Conversion:** Successfully converted numerical features that were loaded as `object` (like A2) back to `int32` after imputation.

### 2. Feature Engineering and Encoding

* **Target Encoding:** The target variable (`+` and `-`) was successfully converted to **1 (Approved)** and **0 (Denied)**.
* **Feature Encoding:** All remaining categorical `object` columns were transformed using **One-Hot Encoding** to create numerical dummy variables, which is mandatory for Logistic Regression.
* **Scaling:** All features were scaled using **StandardScaler** to ensure equal influence on the distance-based model calculation.

### 3. Model Training (Logistic Regression)

* **Model Choice:** Logistic Regression was chosen for its **interpretability** and efficiency in solving binary classification problems.
* **Imbalance Handling:** The data exhibited only **minor imbalance (1.25:1)**, therefore, no oversampling techniques (like SMOTE) were needed, preserving the integrity of the original data distribution.

### 4. Evaluation and Optimization

* **Evaluation Focus:** Metrics beyond simple Accuracy were prioritized: **Precision, Recall, and F1-Score**.
* **Key Finding:** The **ROC AUC Score of 0.9470** demonstrated that the Logistic Regression model, with robust preprocessing, achieved near-perfect discriminatory power, confirming its reliability without requiring complex optimization or ensemble methods.

---

##  Repository Contents

| File Name | Description |
| :--- | :--- |
| `Credit_Approval_Classification.ipynb` | The complete, executable Jupyter Notebook detailing all steps from data loading, cleaning, encoding, training, and final evaluation. |
| `README.md` | This project summary and methodology. |
| `requirements.txt` | Lists all necessary Python dependencies. |

##  Dependencies (`requirements.txt`)
