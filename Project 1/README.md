# Project 1: Exploratory Data Analysis & Data Cleaning

## 📋 Executive Overview
This project represents the initial milestone of the **Decode Labs Data Science Internship**. The objective of this assignment is to execute a rigorous Data Cleaning and Exploratory Data Analysis (EDA) workflow on an unrefined enterprise dataset (`Dataset for Data Analytics.xlsx`), transform it into a structured format, and uncover actionable insights to support data-driven decision-making.

---

## 📊 Dataset Specifications & Transformation Summary

### 1. Raw Data Inspection
* **Source File**: `Dataset for Data Analytics.xlsx`
* **Initial Issues Identified**:
  * Structural inconsistencies and unformatted column headers.
  * Missing, null, or placeholder values across key variables.
  * Inconsistent data types (e.g., numeric values stored as text strings).
  * Trailing white spaces and duplicate records.

### 2. Data Cleaning & Preprocessing Pipeline
* **Missing Value Handling**: Evaluated missingness patterns; applied conditional imputation for missing quantitative values and dropped non-recoverable records.
* **Data Type Normalization**: Cast text-formatted numeric and date attributes into their respective target data types (`float64`, `int64`, `datetime64`).
* **Deduplication & Standardization**: Identified and removed redundant records; standardized categorical text variables across all rows.
* **Processed Output**: Exported sanitized dataset to `Dataset_for_Data_Analytics_Cleaned.xlsx`.

---

## 🔬 Key Analytical Highlights

* **Distribution & Trends**: Analyzed core metric distributions using summary statistics, histograms, and box plots to detect skewness and extreme values.
* **Categorical Segmentation**: Grouped key performance metrics across dimensions to identify leading drivers and outlier performance.
* **Correlation Analysis**: Computed correlation matrices to evaluate relationships between numerical variables, highlighting key features for future modeling.

---

## 📁 File Manifest

| File Name | Description |
| :--- | :--- |
| `EDA_Project_1.ipynb` | Comprehensive Jupyter Notebook containing raw data loading, cleaning scripts, EDA visualizations, and statistical summaries. |
| `Dataset for Data Analytics.xlsx` | The original, unmodified input dataset provided for analysis. |
| `Dataset_for_Data_Analytics_Cleaned.xlsx` | The transformed, fully sanitized output dataset ready for downstream analytics or modeling. |
| `requirements.txt` | List of explicit Python dependencies required to execute the notebook. |
| `README.md` | Granular technical documentation for Project 1 (this file). |

---

## ⚙️ Environment Setup & Execution Instructions

### Step 1: Clone Repository & Open Folder

```bash
git clone https://github.com/hassaanahmad204/DecodeLabs-Internship.git
cd "DecodeLabs-Internship/Project 1"
```

### Step 2: Create & Activate Virtual Environment

Windows:

```powershell
python -m venv venv
.\venv\Scripts\activate
```

macOS / Linux:

```bash
python3 -m venv venv
source venv/bin/activate
```

### Step 3: Install Project Dependencies

```bash
pip install -r requirements.txt
```

### Step 4: Run the Analysis Notebook

```bash
jupyter notebook EDA_Project_1.ipynb
```

---

## 🛠️ Technology Stack

- Language: Python 3.x
- Data Processing & Manipulation: `pandas`, `numpy`
- Excel File I/O: `openpyxl`
- Data Visualization: `matplotlib`, `seaborn`
- Environment: VS Code / Jupyter
