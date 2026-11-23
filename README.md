# Telecom Customer Churn Prediction & Business Proposal

## 📌 Project Overview
This repository contains an end-to-end Data Science project completed as part of the **GCI World 2026 Final Assignment** (Matsuo-Iwasawa Lab, The University of Tokyo). 

The project focuses on predicting customer churn in the telecom industry using Machine Learning and translating those predictions into a highly actionable, AI-driven business proposal to reduce revenue loss.

## 🎯 Business Problem
In the telecom industry, every customer who leaves is lost revenue. Providers often react only *after* a customer has left, and retention offers are frequently untargeted. 

**The Goal:** To build a Machine Learning model that can identify which customers are at high risk of churning *before* they leave, allowing the retention team to take proactive, targeted action.

## 📊 Dataset
The model was trained on a merged dataset containing **100,000 customers** and **100 features**.
*   **Client Data:** Demographics, income, marital status, handset price, equipment age.
*   **Record Data:** Usage, billing, revenue, minutes of use, dropped calls.
*   **Target Variable:** `churn` (1 = customer left, 0 = customer stayed). The dataset was perfectly balanced (approx. 50% churn rate).

*(Note: The original `Client.csv` and `Record.csv` files are NOT included in this repository due to data privacy and course policies.)*

## 🛠️ Methodology & Tools
1.  **Exploratory Data Analysis (EDA):** Identified distributions and correlations in usage and revenue data.
2.  **Data Preparation:** 
    *   Dropped identifiers (`Customer_ID`).
    *   Removed sparse columns (>40% missing values).
    *   Imputed remaining missing values (Median for numeric, 'Unknown' for categorical).
    *   Label Encoded categorical variables.
3.  **Machine Learning Model:** 
    *   **Algorithm:** Random Forest Classifier (100 trees, max depth 15).
    *   **Train/Test Split:** 80% Training / 20% Testing (Stratified).
4.  **Libraries Used:** Python, Pandas, NumPy, Scikit-learn, Matplotlib, Seaborn.

## 📈 Model Performance
*   **Accuracy:** 62.1%
*   **ROC-AUC Score:** 0.674 (Better than random guessing)
*   **Precision (Churn):** 0.61
*   **Recall (Churn):** 0.64 (Successfully identified 64% of actual churners).

**Top 5 Churn Indicators (Feature Importance):**
1.  `eqpdays` (Equipment Age) - Older handsets signal higher churn risk.
2.  `months` (Customer Tenure).
3.  `change_mou` (Change in Minutes of Use).
4.  `mou_Mean` (Average Minutes of Use).
5.  `adjrev` (Adjusted Revenue).

## 💡 Business Proposal: AI-Powered Proactive Retention
Based on the model's insights, I proposed an **AI-Powered Proactive Retention System**:
*   **How it works:** The model runs weekly to score every customer from 0 to 1 based on churn probability.
*   **Action:** Customers with a score > 0.6 are flagged as "High Risk". The retention team then targets them with personalized offers.
*   **Expected Impact:** If deployed effectively, a **15% reduction in churn** is estimated, saving approximately **7,434 customers annually** and significantly increasing Customer Lifetime Value (CLV).

## 📂 Repository Structure
```text
├── README.md                  # Project overview and documentation
├── requirements.txt           # Python dependencies
├── notebooks/
│   └── churn_prediction.ipynb # Complete Jupyter Notebook (EDA, Prep, Model)
├── presentations/
│   └── Final_Assignment.pdf   # 15-slide Business Proposal PDF
└── images/
    ├── roc_curve.png          # Model evaluation charts
    ├── feature_importance.png
    └── confusion_matrix.png
