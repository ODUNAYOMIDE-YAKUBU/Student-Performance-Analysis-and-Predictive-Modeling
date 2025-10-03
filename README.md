# Student Performance Analysis and Predictive Modeling

**Project**: Student Performance Analysis And Performance Prediction  
**Author / Maintainer**: Odunayomide Yakubu [Data Scientist and Analyst |Data Storyteller] 


## Overview
This repository contains a reproducible analysis and predictive modeling pipeline for a student performance dataset. The project explores student-level features, performs EDA, preprocesses data, trains machine learning models, and serializes the best model for later use. The primary deliverable is the Jupyter notebook `Student Performance1.ipynb` and a set of helper scripts for reproducibility.

> Goal: improve student academic performance and well-being by identifying key drivers of success and building predictive models to flag at-risk students.

## 📌 Introduction
The **Student Performance Dataset** provides insights into academic achievements and extracurricular activities of students. This dataset is valuable for analyzing factors that impact student success, study habits, and parental influence.

## 📂 Dataset Overview
- **Total Records:** 6,055  
- **Total Columns:** 15

### 🔑 Key Features
- **Demographics:** `StudentID`, `Age`, `Gender`, `Ethnicity`  
- **Academic Performance:** `GPA`, `GradeClass`, `Absences`, `StudyTimeWeekly`  
- **Parental Influence:** `ParentalEducation`, `ParentalSupport`  
- **Extracurricular Activities:** `ClubInvolvement`, `Sports`, `Music`, `Volunteering`  
- **Additional Support:** `Tutoring`  


## 🗂 Data dictionary (column descriptions)
> Short, human-readable descriptions for each column — update as needed to match your dataset precisely.
- `StudentID` - Student unique identifier (integer)
- `Age` — Student age in years (integer).  
- `Gender` — Student gender (e.g., `Male`, `Female`, `Other`).  
- `Ethnicity` — Self-reported ethnicity or category.  
- `GPA` — Grade Point Average (continuous: 0.0 – 4.0 or dataset scale).  
- `GradeClass` — Categorical grade bracket (e.g., `A`, `B`, `C`) or year group.  
- `Absences` — Number of class days missed.  
- `StudyTimeWeekly` — Reported weekly study hours.  
- `ParentalEducation` — Highest education level of parents/guardians.  
- `ParentalSupport` — Indicator of parental support (binary/categorical/scale).  
- `ClubInvolvement` — Participation in clubs (Yes/No or list).  
- `Sports` — Participation in sports (Yes/No or frequency).  
- `Music` — Participation in music programs (Yes/No or frequency).  
- `Volunteering` — Volunteering involvement (Yes/No or hours).  
- `Tutoring` — Whether student receives tutoring (Yes/No / hours).  
- `EnrollmentStatus` — Current enrollment status (e.g., `Active`, `Transferred`, `Dropped`) — **(replace if different)**


## 🎯 Target variable(s)
Choose target depending on your problem formulation:
- **Regression:** `GPA` (predict continuous performance scores).  
- **Classification:** `GradeClass` (predict grade bucket or `AtRisk` label derived from GPA thresholds).  
- You can also define derived targets such as `AtRisk` (GPA < threshold) or `Improved` (GPA increase vs previous term).

## 📊 Potential Use Cases
- Predicting student performance based on study habits.  
- Analyzing the impact of extracurricular activities on GPA.  
- Examining the role of parental support in academic success.  
- Identifying trends in absenteeism and its effects on grades.  
- Building an early-warning system to flag at-risk students for intervention.

## 🧰 Preprocessing Checklist (recommended)
Before training models, perform these reproducible steps:

1. **Data ingestion** — load from `data/student_performance_dataset.csv`.  
2. **Missing values** — impute:  
   - Categorical: most frequent or a dedicated `Missing` category.  
   - Numerical: median (robust) or mean where appropriate.  
3. **Type conversions** — convert categorical columns to `category` dtype.  
4. **Feature engineering** — create derived features (e.g., `StudyTimeCategory`, `AbsenceRate`, `ExtracurricularScore`).  
5. **Encoding** — one-hot / ordinal encoding for categorical variables (choose consistent mapping).  
7. **Train/test split** — use stratified split for classification; keep a holdout test set (e.g., 20%).  
8. **Imbalanced classes** — handle via resampling, class weights, or targeted metrics.  
9. **Versioning** — save processed datasets and preprocessing pipeline (e.g., `joblib`).

## 🧪 Modeling & evaluation
Suggested approaches and metrics:

### Model types
- Logistic Regression (classification) .  
-  Random Forest Regression .  

### Evaluation metrics
- **Regression:** RMSE, MAE, R² for `GPA` prediction.  
- **Classification:** Accuracy, Precision, Recall, F1-score, .  
- **Business-relevant:** Precision@k, Recall@k, confusion matrix for `AtRisk` detection.

### Model validation
- Cross-validation (k-fold) for robust estimates.  
- Use a holdout test set for final evaluation.  
- Report confidence intervals where possible.

## Notebook summary
`notebooks/Student Performance1.ipynb` contains:
- Data loading & initial inspection (`pandas`, `df.info()`, `df.head()`, `df.nunique()`).
- Exploratory Data Analysis using `matplotlib` and `seaborn` (charts and embedded figures).
- Preprocessing and missing-value handling (uses `SimpleImputer`, encoders and `ColumnTransformer`).
- Train/test split and model training with `scikit-learn` (pipelines and model serialization via `joblib`).
- Outputs: plots, summary tables, and saved model artifacts (if run).

## Results (summary)
> Replace this section with the project's quantitative outcomes after running the notebook fully.

- Model Performance: **`<RandomForestRegressor>`** 
  - Tuned Model Test MSE: `0.0579`
  - Tuned Model Test R-squared: `0.9288`
  
- Performance: **`<LogisticRegression>`**
  - Accuracy: `99.61%`
  - Precision / Recall / F1: `1 / 1 / 1`

- Key drivers identified: `[ 'GPA', 'Absences', 'StudyTimeWeekly', 'Tutoring']`

## Installation


## Usage

All analysis and modeling are performed within Jupyter Notebooks. Open the relevant `.ipynb` files to follow the workflow:

- **EDA.ipynb**: Data exploration and visualization
- **Preprocessing.ipynb**: Data cleaning and feature engineering
- **Modeling.ipynb**: Building and evaluating predictive models

## Project Structure

```
.
├── data/
│   └── student_performance.csv        # Raw dataset
├── notebooks/
│   ├── EDA.ipynb                      # Exploratory Data Analysis
│   ├── Preprocessing.ipynb            # Data preprocessing steps
│   └── Modeling.ipynb                 # Predictive modeling
├── requirements.txt
├── README.md
```

## Machine Learning Models

- Logistic Regression
- Decision Trees
- Random Forests
- (Add or modify based on your implementation)

## Results

Summarize your key findings here, e.g.:

-### Major takeaways
- **Top predictors of student performance:** `StudyTimeWeekly`, `Absences`, `PastGrades` (or prior term performance), and `ParentalSupport` are the strongest predictors of final academic outcome based on feature importance analysis.
- **Attendance matters:** Higher `Absences` is consistently associated with lower `GPA` and a higher probability of being flagged `AtRisk`.
- **Study habits drive gains:** Students reporting ≥ **71%** hours/week of focused study show substantially higher average GPA than peers.
- **Extracurricular involvement shows mixed effects:** Participation in clubs, sports, and music correlates with improved engagement and modest positive GPA lift after controlling for study time; the effect varies by activity type.
- **Tutoring helps but is clustered:** Students receiving tutoring often start with lower baseline performance (selection effect) yet demonstrate better relative improvement; targeted tutoring appears more effective than unfocused programs.
- **Model performance:** Best model = **RandomForestRegressor** — *Accuracy:* `92.9%`, *Recall (AtRisk):* `99.6%`.
- **Fairness & bias check:** Performance gaps were observed across demographic groups (e.g., `Ethnicity`, `ParentalEducation`). Without mitigation, models may reproduce existing disparities.


### Practical recommendations
1. **Early-warning dashboard:** Implement a real-time rule to flag students with low recent grades, high absences, or low study hours for counselor outreach and support.  
2. **Targeted tutoring & monitoring:** Prioritize tutoring for flagged students and measure short-term GPA changes to evaluate impact.  
3. **Parental engagement programs:** Run low-cost workshops or weekly progress summaries for students with low `ParentalSupport` scores.  
4. **Promote structured study time:** Offer study-skill sessions and track `StudyTimeWeekly` as a KPI; marginal increases in study time correlate with measurable GPA gains.  
5. **Audit model fairness:** Perform subgroup evaluation and calibration checks before deployment; consider class balancing, reweighting, or fairness-aware algorithms for mitigation.

## Contributing

Contributions are welcome! Please open issues or submit pull requests for enhancements, bug fixes, or new features.

## License

[MIT License](LICENSE)

## Contact

For questions or collaborations, reach out to the repository owner via [GitHub profile](https://github.com/ODUNAYOMIDE-YAKUBU).


### Clone the repo
 **Clone the repository:**
   ```bash
   git clone https://github.com/ODUNAYOMIDE-YAKUBU/Student-Performance-Analysis-and-Predictive-Modeling.git
   cd Student-Performance-Analysis-and-Predictive-Modeling
   ```
