# Association and Predictive Performance of Vital Signs Alone in Patient Clinical Outcomes

**Healthcare Data Analytics Project | Python, Data Cleaning, Statistical Analysis & Machine Learning**

## 1. Project Overview

This project investigates whether five routine vital signs (temperature, pulse rate, respiratory rate, systolic blood pressure and diastolic blood pressure) can help explain and predict four patient outcomes: Improved, Unchanged, Referred and Died.

Using a dataset of 1,000 patient records, I examined three questions:

1. Do vital signs differ across patient outcome groups?
2. How accurately can vital signs predict patient outcomes?
3. Are five vital signs sufficient to classify the four outcomes reliably?

After data cleaning, 878 records were included in the analysis.

**Tools:** Python, pandas, NumPy, SciPy, Pingouin, scikit-learn, Matplotlib and Jupyter Notebook.

**Important:** This project uses AI-generated synthetic data. It demonstrates my skills in healthcare data cleaning, statistical analysis and machine learning. It does not contain real patient records or provide clinical evidence.

## 2. Project Files

- [**View Full Project Report (PDF)**](Vital_Signs_Patient_Outcomes_Analysis_Report.pdf)
- [**View Raw Dataset (Excel)**](Dirty_Vital_Signs_Analysis_Dataset.xlsx)
- [**View Cleaned Dataset (Excel)**](Cleaned_Vital_Signs_Analysis_Dataset.xlsx)
- **Analysis Notebook:** Jupyter Notebook (uploading soon).

## 3. Data Cleaning

The original dataset contained 1,000 records.

The cleaning process involved:

- Removing 12 duplicate records.
- Converting vital-sign measurements stored as text into numeric values.
- Standardising inconsistent outcome labels.
- Identifying impossible and inconsistent measurements.
- Handling missing values without guessing or imputing patient outcomes.
- Identifying and retaining unusual but physiologically plausible values.

A total of 110 records with at least one missing or invalid vital sign were excluded using complete-case analysis.

**Final dataset: 878 records.**

A chi-square test found no evidence that record removal differed significantly across the four outcome groups (p = 0.518).

## 4. Statistical Analysis

I used:

- Descriptive statistics to summarise the data.
- Distribution checks and Levene's test to assess statistical assumptions.
- One-way ANOVA to compare the five vital signs across outcome groups.
- Welch ANOVA and Kruskal–Wallis tests to check the consistency of the results.
- Post-hoc tests to identify which outcome groups differed.
- Effect sizes to measure the magnitude of differences.
- Chi-square tests to examine associations between clinical vital-sign flags and outcomes.
- Pearson and Spearman correlation and VIF to examine relationships between vital signs.

## 5. Machine Learning

I used Multinomial Logistic Regression to predict the four patient outcomes using only the five vital signs.

Two models were compared:

- Standard Logistic Regression.
- Class-balanced Logistic Regression.

A majority-class baseline, which always predicts Improved, was used for comparison.

The data was divided into training (702 records) and test (176 records) sets using a stratified 80:20 split. Standardisation was fitted using training data only.

**Evaluation metrics:** Accuracy, precision, recall, specificity, F1-score and ROC-AUC.

## 6. Key Findings

### Statistical Associations

All five vital signs differed significantly across the four outcome groups (Holm-adjusted p < 0.001).

Respiratory rate showed the strongest association (η² = 0.373), followed by pulse rate (0.332) and temperature (0.288).

### Predictive Performance

The class-balanced Logistic Regression model achieved:

| Metric | Result |
|---|---:|
| Accuracy | 53.4% |
| Macro-F1 | 0.459 |
| Macro Recall | 49.5% |
| Macro ROC-AUC | 0.765 |

The majority-class baseline achieved 48.3% accuracy.

**Recall by patient outcome:**

| Outcome | Recall |
|---|---:|
| Improved | 67.1% |
| Unchanged | 45.5% |
| Referred | 14.7% |
| Died | 70.8% |

The model struggled particularly to identify Referred patients (14.7% recall). This may partly reflect the overlap between Referred and Died patients in several vital signs: their systolic and diastolic blood pressure differences were not statistically significant in post-hoc comparisons. Although respiratory rate differed significantly between the two groups, the difference was relatively small (1.65 breaths/min).

### Predictive Sufficiency

The model failed all three predefined performance requirements:

- Macro-F1 of at least 0.70.
- Recall of at least 60% for every outcome.
- Lower 95% confidence limit for accuracy above the 48.3% baseline.

**Conclusion:** Five vital signs alone were not sufficient for reliable classification of all four outcomes.

## 7. Limitations

- The dataset is synthetic.
- Only five vital signs were used as predictors.
- Each patient had one set of measurements rather than repeated observations.
- The test dataset contained only 176 records.
- Only Logistic Regression models were evaluated.
- The balanced model was selected after comparing performance on the same test set used for final evaluation, which may favour the selected model.
- No external validation using real-world healthcare data was performed.

## 8. Conclusion

All five vital signs showed significant differences across patient outcome groups, but their ability to predict individual outcomes was limited.

The project demonstrates an important distinction: **statistical association does not necessarily mean reliable prediction.**

The findings also highlight the importance of combining vital signs with other patient information when developing more comprehensive predictive models.

## Disclaimer

This project uses AI-generated synthetic data for educational and analytical demonstration. It does not represent real patients, establish clinical relationships or provide medical advice. It must not be used to make patient-care decisions.
