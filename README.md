# Decode Labs — Data Science Internship Repository

Welcome to my central repository for the **Data Science Internship at Decode Labs**. This repository serves as a structured portfolio documenting end-to-end data science assignments, exploratory data analyses, statistical modeling, machine learning workflows, and data engineering projects completed throughout the internship program.

---

## 📌 Repository Overview

This repository is organized modularly, with each project contained in its dedicated directory. Every project folder includes its respective source code, datasets (or references), requirements, and granular documentation.

| Project Folder | Description | Tech Stack & Focus Areas | Status |
| :--- | :--- | :--- | :---: |
| **[`Project 1/`](./Project%201/)** | **Exploratory Data Analysis & Data Cleaning** | Python, Pandas, OpenPyXL, Matplotlib, Seaborn | ✅ Completed |
| **[`Project 2/`](./Project%202/)** | **Supervised Learning & Fraud Detection** | Python, Pandas, NumPy, Scikit-learn, SMOTE, Matplotlib, Seaborn | ✅ Completed |
| `Project 3/` | *Upcoming Internship Module* | TBD | ⏳ Pending |

---

## 🛠️ Global Setup & Environment Guidelines

### Prerequisites
* **Python**: Version 3.10 or higher recommended.
* **Git**: Installed for version control management.

### Environment Activation
To maintain consistent dependencies across projects without version conflicts, a virtual environment is recommended at the repository root.

```bash
# 1. Clone the repository
git clone https://github.com/hassaanahmad204/DecodeLabs-Internship.git

# 2. Navigate into the main repository directory
cd DecodeLabs-Internship

# 3. Create a virtual environment
python -m venv venv

# 4. Activate the virtual environment
# Windows (PowerShell / Command Prompt):
.\venv\Scripts\activate

# macOS / Linux:
source venv/bin/activate
```

## 📂 Project Directory Structure

```text
DecodeLabs-Internship/
├── .gitignore                      # Git exclusion rules (venv, checkpoints, raw PDFs)
├── README.md                       # Master repository documentation (this file)
├── Project 1/                      # Project 1: EDA & Data Cleaning
    ├── Dataset for Data Analytics.xlsx         # Original raw dataset
    ├── Dataset_for_Data_Analytics_Cleaned.xlsx # Sanitized output dataset
    ├── EDA_Project_1.ipynb                     # Jupyter notebook containing analysis & code
    ├── README.md                               # Project-specific technical documentation
    └── requirements.txt                        # Python library dependencies for Project 1
└── Project 2/                      # Project 2: Fraud Detection Pipeline
    ├── Fraud_Detection_Project_2.ipynb          # Model training and evaluation notebook
    ├── README.md                               # Project-specific technical documentation
    └── requirements.txt                        # Python library dependencies for Project 2
```

## 📊 Project 2: Fraud Detection

Project 2 develops a supervised machine learning pipeline for identifying
fraudulent credit card transactions in a highly imbalanced dataset. The workflow
includes:

- Robust scaling for the `Time` and `Amount` features.
- Stratified 80/20 train-test splitting.
- SMOTE applied only to the training data to prevent data leakage.
- Comparison of Logistic Regression and Random Forest models.
- Evaluation with fraud-class precision, recall, F1-score, and ROC-AUC.

The dataset contains 284,807 transactions, including 492 fraud cases. Because the
dataset is too large for GitHub, download `creditcard.csv` from the [Kaggle Credit
Card Fraud Detection Dataset](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud)
and place it inside the `Project 2/` directory before running the notebook.

## 👤 Author & Acknowledgments

- Intern / Author: Hassaan Ahmad
- Degree: BS Computer Science, COMSATS University Islamabad, Lahore Campus
- Organization: Decode Labs
- Role: Data Science Intern

For specific technical implementation, data preprocessing methodologies, and
analytical findings, refer to the project documentation:

- [Project 1 README](./Project%201/README.md)
- [Project 2 README](./Project%202/README.md)
