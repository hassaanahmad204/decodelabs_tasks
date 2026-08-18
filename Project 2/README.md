# Project 2: Fraud Detection Pipeline

An end-to-end supervised learning pipeline for detecting fraudulent credit card
transactions in a heavily imbalanced dataset. The project compares a linear
baseline with a tree-based ensemble while prioritizing fraud recall and precision
over raw accuracy.

## Dataset

- **Source:** [Kaggle Credit Card Fraud Detection Dataset](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud)
- **Transactions:** 284,807 total
- **Fraud cases:** 492, or approximately 0.172%
- **Features:** `Time`, `Amount`, and 28 PCA-anonymized features (`V1` to `V28`)

The raw `creditcard.csv` file is excluded from the repository because of GitHub's
file size limits. Download it from Kaggle and place it in the `Project 2/`
directory before running the notebook.

## Preprocessing

1. Scale `Time` and `Amount` with `RobustScaler` to reduce the impact of outliers.
2. Split the data into training and test sets using an 80/20 stratified split.
3. Apply SMOTE only to `X_train` so that synthetic samples do not leak into the
   test set.

## Model Evaluation

The models are compared using fraud-class **precision**, **recall**, **F1-score**,
and **ROC-AUC** rather than accuracy alone.

| Model | Description | Precision | Recall | F1-score | ROC-AUC |
| --- | --- | ---: | ---: | ---: | ---: |
| Logistic Regression | Linear baseline trained on the resampled feature space | ~0.06 | ~0.91 | ~0.11 | ~0.97 |
| Random Forest | Non-linear decision-tree ensemble with depth constraints | ~0.85+ | ~0.82+ | ~0.84+ | ~0.97+ |

### Metric Priorities

- **Recall:** Reduces false negatives, or fraudulent transactions missed by the model.
- **Precision:** Reduces false positives and limits unnecessary investigator workload.
- **ROC-AUC:** Measures discrimination across classification thresholds.

## Project Files

```text
Project 2/
|-- Fraud_Detection_Project_2.ipynb  # Data pipeline, training, and evaluation
|-- requirements.txt                 # Python dependencies
`-- README.md                        # Project documentation
```

## How to Run

### 1. Open the project directory

```bash
cd "Project 2"
```

### 2. Download the dataset

Download `creditcard.csv` from the [Kaggle dataset page](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud), then place the file in this directory.

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Run the notebook

Open `Fraud_Detection_Project_2.ipynb` in VS Code or Jupyter, or launch it from the command line:

```bash
jupyter notebook Fraud_Detection_Project_2.ipynb
```

## Tech Stack

- **Language:** Python 3.x
- **Data manipulation:** pandas, NumPy
- **Machine learning:** scikit-learn
- **Imbalanced learning:** imbalanced-learn (SMOTE)
- **Visualization:** Matplotlib, Seaborn