# Ad Click Prediction — Logistic Regression
### Classification · Python · Scikit-learn

![Python](https://img.shields.io/badge/Python-3.11-blue?style=flat&logo=python)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-ML-orange?style=flat&logo=scikit-learn)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?style=flat&logo=pandas)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?style=flat&logo=jupyter)
![Accuracy](https://img.shields.io/badge/Accuracy-98%25-brightgreen?style=flat)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=flat)

---

## Overview

This project applies **Logistic Regression** to predict whether a user will click on an online advertisement based on their browsing behaviour and demographic data.

The goal is to build a binary classification model that can help digital marketing teams identify which users are most likely to engage with ads — enabling smarter targeting and reduced ad spend waste.

---

## Business Problem

An advertising company wants to predict whether a user will click on a displayed ad. By understanding which user behaviours and demographics correlate with ad clicks, the company can:

- Target the right users with the right ads
- Reduce wasted impressions on users unlikely to click
- Improve overall campaign ROI

---

## Dataset

**File:** `advertising.csv` — 1000 records, no missing values

| Feature | Type | Description |
|---|---|---|
| `Daily Time Spent on Site` | float | Minutes spent on the site per day |
| `Age` | int | User age |
| `Area Income` | float | Average income of user's geographic area ($) |
| `Daily Internet Usage` | float | Minutes of internet usage per day |
| `Male` | int | Gender flag (1 = Male, 0 = Female) |
| `Clicked on Ad` | int | **Target** — 1 = Clicked, 0 = Did not click |

> Note: `Ad Topic Line`, `City`, `Country`, and `Timestamp` columns are present in the raw data but dropped during feature selection.

---

## Project Workflow

```
Data Loading → EDA → Feature Selection → Train/Test Split → Model Training → Evaluation
```

**1. Exploratory Data Analysis (EDA)**
- Distribution plots for numerical features
- Pairplot to visualise class separation
- Correlation heatmap to identify predictive features

**2. Feature Selection**
- Selected: `Daily Time Spent on Site`, `Age`, `Area Income`, `Daily Internet Usage`, `Male`
- Dropped: text and categorical columns (`Ad Topic Line`, `City`, `Country`, `Timestamp`)

**3. Model Training**
- Algorithm: `LogisticRegression` from Scikit-learn
- Split: 70% train / 30% test (700 train, 300 test records)
- No feature scaling applied (logistic regression with lbfgs solver)

**4. Evaluation**
- Classification report: precision, recall, F1-score per class
- Confusion matrix analysis

---

## Results

### Classification Report

| Class | Precision | Recall | F1-Score | Support |
|---|---|---|---|---|
| 0 (Did not click) | 0.97 | 0.99 | 0.98 | 171 |
| 1 (Clicked) | 0.99 | 0.97 | 0.98 | 159 |
| **Overall Accuracy** | | | **0.98** | **330** |

### Key Takeaway

> The model achieves **98% accuracy** on unseen test data — correctly classifying 323 out of 330 users.
> Both precision and recall are near-perfect for both classes, indicating the model is well-balanced with no significant bias toward either class.

---

## Tech Stack

| Tool | Purpose |
|---|---|
| Python 3.11 | Core language |
| Pandas | Data loading & manipulation |
| NumPy | Numerical operations |
| Scikit-learn | Model training & evaluation |
| Seaborn | Statistical visualisations |
| Matplotlib | Plotting |
| Jupyter Notebook | Development environment |

---

## How to Run

**1. Clone the repository**
```bash
git clone https://github.com/SouravDey1/ad-click-logistic-regression.git
cd ad-click-logistic-regression
```

**2. Install dependencies**
```bash
pip install pandas numpy scikit-learn seaborn matplotlib jupyter
```

**3. Add the dataset**

Place `advertising.csv` in the project root folder.

**4. Open the notebook**
```bash
jupyter notebook logistic_regression_project.ipynb
```

---

## Repository Structure

```
ad-click-logistic-regression/
│
├── logistic_regression_project.ipynb   # Main notebook — EDA, training, evaluation
├── advertising.csv                     # Dataset (add manually)
└── README.md                           # This file
```

---

## What I Learned

- How to frame a **binary classification** problem from a real marketing use case
- Feature selection — which columns add predictive value and which to drop
- Interpreting a **classification report** — precision vs recall trade-off
- Why 98% accuracy here is meaningful: the dataset is balanced (50/50 click ratio), so high accuracy genuinely reflects model quality, not class imbalance
- Difference between regression (predicting a number) and classification (predicting a category)

---

## Author

**Sourav Dey**
Final-Year EEE Student · Ahsanullah University of Science and Technology (AUST)
📧 sourav41dey@gmail.com
🔗 [LinkedIn](https://www.linkedin.com/in/sourav-dey-754298251/)
🐙 [GitHub](https://github.com/SouravDey1)

---

*Part of my Data Science & Machine Learning portfolio.*
*Previous project → [E-Commerce Spending Prediction (Linear Regression)](https://github.com/SouravDey1/ecommerce-linear-regression)*
