# Student Performance Analysis and Prediction model

**Project**: Student Performance Analysis And Performance Prediction  
**Author / Maintainer**: Odunayomide Yakubu [Data Scientist and Analyst | Data Storyteller] 


## Overview
This repository contains a reproducible analysis and predictive modeling pipeline for a student performance dataset. The project explores student-level features, performs EDA, preprocesses data, trains machine learning models, and serializes the best model for later use. The primary deliverable is the Jupyter notebook `Student Performance1.ipynb` and a set of helper scripts for reproducibility.

> Goal: improve student academic performance and well-being by identifying key drivers of success and building predictive models to flag at-risk students.

## Table of contents
- [Contents](#contents)
- [Dataset](#dataset)
- [Notebook summary](#notebook-summary)
- [Results (summary)](#results-summary)
- [Installation](#installation)
- [Usage](#usage)
- [Project structure](#project-structure)
- [Reproducibility & recommended workflow](#reproducibility--recommended-workflow)
- [Contributing](#contributing)
- [License](#license)
- [Contact & Acknowledgements](#contact--acknowledgements)

## Contents
This repo includes:
- `notebooks/Student Performance1.ipynb` — EDA, preprocessing, modeling, visualizations (primary notebook).
- `data/` — (expected) place for the dataset (not included here due to privacy/size).
- `scripts/` — helper scripts (training, evaluation, preprocessing).
- `models/` — saved trained model(s) (e.g., `.joblib` files).
- `reports/` — exported HTML, images, and short project report.
- `README.md`, `CONTRIBUTING.md`, `LICENSE`, `requirements.txt`, `.gitignore`.

## Dataset
**Expected path in repo:** `data/student_performance_dataset.csv`

> Note: The original notebook referenced a local path on a user machine (e.g. `C:\Users\chris\...student_performance_dataset.csv`). For portability and to keep history clean, move the dataset file to `data/` before running the notebook or scripts. If dataset is large, consider using Git LFS or hosting it externally (Google Drive / Zenodo / institutional storage) and add a small sample CSV to `data/sample_student_performance.csv` for quick testing.

### Data fields (typical)
This dataset usually contains student demographics, academic metrics and contextual features (e.g., age, gender, study time, parental education, past grades, attendance). See the notebook for the exact column names.

## Notebook summary
`notebooks/Student Performance1.ipynb` contains:
- Data loading & initial inspection (`pandas`, `df.info()`, `df.head()`, `df.nunique()`).
- Exploratory Data Analysis using `matplotlib` and `seaborn` (charts and embedded figures).
- Preprocessing and missing-value handling (uses `SimpleImputer`, encoders and `ColumnTransformer`).
- Train/test split and model training with `scikit-learn` (pipelines and model serialization via `joblib`).
- Outputs: plots, summary tables, and saved model artifacts (if run).

## Results (summary)
> Replace this section with the project's quantitative outcomes after running the notebook fully.

- Best model: **`<RandomForestRegressor>`** 
-Tuned Model Test MSE: 0.0579
-Tuned Model Test R-squared: 0.9288
- 
- Performance (example placeholders):
  - Accuracy: `99.61%`
  - Precision / Recall / F1: `X.XX / X.XX / X.XX`
  - ROC-AUC: `0.XX`
- Key drivers identified: e.g., study time, past grade, parental education (update after EDA)

## Installation

### Clone the repo
```bash
git clone https://github.com/<Odunayomide-Yakubu>/student-performance-prediction.git
cd student-performance-prediction

