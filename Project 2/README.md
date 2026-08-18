# Project 2: Supervised Learning — Fraud Detection Pipeline

## 📋 Executive Overview
This project delivers an end-to-end Machine Learning classification pipeline designed to detect fraudulent credit card transactions in a heavily imbalanced financial environment. Using advanced resample engineering, robust feature scaling, and ensemble modeling, this pipeline demonstrates how to prioritize fraud detection recall and precision over raw accuracy metrics.

---

## 📊 Dataset & Imbalance Architecture

* **Dataset Source**: [Kaggle — Credit Card Fraud Detection Dataset](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud)
* **Total Transactions**: 284,807
* **Fraud Ratio**: ~0.172% (492 fraudulent transactions vs. 284,315 legitimate)
* **Feature Set**: 28 PCA-anonymized numerical features (`V1` to `V28`), transaction `Time`, and transaction `Amount`

> **Note on Data Access**: Due to GitHub file size limitations, the raw `creditcard.csv` dataset is excluded via `.gitignore`. You can download the dataset directly from the [Kaggle Dataset Link](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud) and place it inside the `Project 2/` directory.

---

## ⚙️ Data Preprocessing & Pipeline Engineering

1. **Feature Normalization**: Scaled `Time` and `Amount` using `RobustScaler` to minimize the influence of extreme monetary outliers.
2. **Stratified Splitting**: Applied an 80/20 train-test split stratified on the target class (`stratify=y`) to maintain the true underlying class ratio across validation splits.
3. **Synthetic Minority Over-sampling (SMOTE)**:
   * Generated synthetic samples for the minority fraud class strictly within the training set (`X_train`) to eliminate data leakage[cite: 1].
   * Balanced the training distribution to allow downstream estimators to learn distinct fraud boundary representations[cite: 1].

---

## 🤖 Model Implementation & Comparative Evaluation

Models were evaluated without relying on raw accuracy, focusing instead on **Precision**, **Recall**, **F1-Score**, and **ROC-AUC**[cite: 1]:

| Algorithm | Focus & Architecture | Precision (Fraud) | Recall (Fraud) | F1-Score | ROC-AUC |
| :--- | :--- | :---: | :---: | :---: | :---: |
| **Logistic Regression** | Baseline linear classification on resampled feature space | ~0.06 | ~0.91 | ~0.11 | ~0.97 |
| **Random Forest** | Non-linear ensemble of decision trees with depth constraints | ~0.85+ | ~0.82+ | ~0.84+ | ~0.97+ |

### 🔍 Key Metrics Breakdown
* **Recall (Sensitivity)**: Prioritized to minimize False Negatives (fraud slipping through undetected)[cite: 1].
* **Precision**: Optimized in Random Forest to drastically reduce False Positives, ensuring operational efficiency for fraud investigators[cite: 1].
* **ROC-AUC**: Confirms the classifier's discriminatory threshold performance across all decision boundaries[cite: 1].

---

## 📁 File Manifest

```text
Project 2/
├── Fraud_Detection_Project_2.ipynb  # End-to-end data pipeline, training, and evaluation
├── requirements.txt                 # Project-specific Python dependencies
└── README.md                        # Technical documentation (this file)

🚀 How to Run
Step 1: Navigate to Project 2
Bash
cd "Project 2"
Step 2: Download the Dataset
Download creditcard.csv from the Kaggle Dataset Page.

Place the unzipped creditcard.csv file inside this Project 2 folder.

Step 3: Install Dependencies
Bash
pip install -r requirements.txt
Step 4: Execute the Pipeline
Open the notebook in VS Code or Jupyter:

Bash
jupyter notebook Fraud_Detection_Project_2.ipynb
🛠️ Tech Stack & Libraries
Language: Python 3.x

Data Manipulation: pandas, numpy

Machine Learning: scikit-learn

[cite: 1]

Imbalanced Data Handling: imbalanced-learn (SMOTE)[cite: 1]

Visualizations: matplotlib, seaborn