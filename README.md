# Vital Signs and Patient Clinical Outcomes: A Statistical and Machine Learning Analysis

A Healthcare Data Analytics Project Using Python

## Project Overview

Vital signs are important indicators of a patient's physiological condition. Measurements such as body temperature, pulse rate, respiratory rate, and blood pressure provide information about a patient's clinical status.

This project analysed a synthetic dataset of 1,000 patient records to investigate the relationship between five vital signs and four patient clinical outcomes: Improved, Unchanged, Referred, and Died.

The objective was to examine whether vital signs differed significantly across patient outcomes, evaluate their ability to predict patient outcomes using machine learning, and determine whether vital signs alone were sufficient for reliable outcome classification.

The analysis involved data cleaning, descriptive statistics, hypothesis testing, effect-size analysis, correlation analysis, multicollinearity assessment, and multiclass machine learning classification.

After data cleaning and complete-case selection, 878 patient records remained for the primary statistical and predictive analyses.

**Dataset:** Synthetic patient vital signs and clinical outcomes  
**Records before cleaning:** 1,000  
**Records after duplicate removal:** 988  
**Records used in the primary analysis:** 878  
**Tools:** Python, pandas, NumPy, SciPy, scikit-learn, Matplotlib

## Full Project Report

The detailed project report is available here:

[View Full Vital Signs and Patient Clinical Outcomes Analysis Report (PDF)](Vital_Signs_Patient_Outcomes_Analysis_Report.pdf)

## Project Objectives

1. Investigate whether five vital signs differ significantly across four patient clinical outcomes.
2. Evaluate how accurately vital signs alone can predict patient clinical outcomes using machine learning.
3. Determine whether the five vital signs are sufficient for reliable classification of the four patient outcomes.

## Dataset Overview

The synthetic dataset was designed to represent patient vital-sign measurements and clinical outcomes.

The original dataset contained seven columns:

- Patient_ID
- Temperature_C
- Pulse_Rate_bpm
- Respiratory_Rate_cpm
- Systolic_BP_mmHg
- Diastolic_BP_mmHg
- Patient_Outcome

The five vital signs were:

- Body temperature
- Pulse rate
- Respiratory rate
- Systolic blood pressure
- Diastolic blood pressure

Patient outcomes were grouped into four categories:

- Improved
- Unchanged
- Referred
- Died

Three additional variables were derived from the original blood pressure and pulse measurements:

- Pulse Pressure
- Mean Arterial Pressure (MAP)
- Shock Index

The dataset was synthetically generated using AI and does not represent actual patient records.

## Tools and Technologies

- Python
- pandas
- NumPy
- SciPy
- scikit-learn
- Matplotlib
- Jupyter Notebook

## Data Cleaning

The data preparation process addressed several quality issues:

- Duplicate records
- Missing values
- Invalid physiological measurements
- Inconsistent measurement units and formatting
- Data type standardisation
- Blood pressure consistency checks

After removing duplicate records, 988 records remained.

Following the handling of missing and invalid measurements, complete-case analysis was performed, resulting in 878 records for the primary analysis.

Twenty-three observations identified as IQR outliers across the five vital signs were retained because they were considered plausible within the dataset's documented measurement ranges.

## Statistical Methods

The project used several statistical techniques to investigate differences in vital signs across patient outcomes.

**Descriptive and exploratory analysis**

- Mean, median, standard deviation, and quartiles
- Skewness and kurtosis
- Distribution assessment
- Correlation analysis
- Variance Inflation Factor (VIF)

**Hypothesis testing**

- One-way ANOVA
- Welch's ANOVA
- Kruskal–Wallis test
- Tukey HSD post-hoc test
- Dunn's post-hoc test with Holm adjustment
- Chi-square test
- Levene's test

**Effect-size analysis**

- Eta-squared
- Omega-squared
- Epsilon-squared
- Cramér's V

The analysis also examined clinical flags based on illustrative vital-sign thresholds.

## Machine Learning Methods

Several classification models were developed and compared to evaluate the predictive performance of vital signs.

The models included:

- Majority-class baseline
- Logistic Regression
- Balanced Logistic Regression
- Random Forest
- Gradient Boosting
- Support Vector Machine (RBF)

The dataset was divided into training and testing sets using a stratified 80:20 split.

Model selection was performed using repeated stratified five-fold cross-validation on the training data. Macro-F1 was used as the primary model-selection metric because the four outcome categories were not equally represented.

The selected model was evaluated on the held-out test dataset.

**Evaluation metrics included:**

- Accuracy
- Balanced Accuracy
- Macro-F1 Score
- Precision
- Recall
- ROC-AUC
- Cohen's Kappa
- Matthews Correlation Coefficient
- Confusion Matrix

## Key Findings

### Vital Signs and Patient Outcomes

All five vital signs demonstrated statistically significant differences across the four patient outcome groups.

The strength of association varied across the measurements.

Respiratory rate showed the largest effect size, followed by pulse rate, temperature, diastolic blood pressure, and systolic blood pressure.

| Vital Sign | Eta-squared (η²) |
|---|---:|
| Respiratory Rate | 0.373 |
| Pulse Rate | 0.332 |
| Temperature | 0.288 |
| Diastolic Blood Pressure | 0.211 |
| Systolic Blood Pressure | 0.174 |

These findings indicate that the distributions of the five vital signs differed across patient outcome categories in the synthetic dataset.

### Correlation and Multicollinearity

Correlation analysis identified strong positive relationships among temperature, pulse rate, and respiratory rate.

Blood pressure measurements showed negative relationships with these three vital signs.

Variance Inflation Factor analysis produced values between 1.6 and 3.2, indicating that severe multicollinearity was not detected among the five predictors.

### Predictive Model Performance

Balanced Logistic Regression was selected based on its cross-validation macro-F1 performance.

On the independent test dataset, the model achieved:

| Evaluation Metric | Result |
|---|---:|
| Accuracy | 53.4% |
| Balanced Accuracy | 49.5% |
| Macro-F1 Score | 0.459 |
| Macro ROC-AUC | 0.765 |
| Cohen's Kappa | 0.329 |
| Matthews Correlation Coefficient | 0.333 |

The model achieved an accuracy of 53.4%, compared with 48.3% for the majority-class baseline.

Although the model performed better than the baseline, its overall classification performance remained modest.

### Performance Across Patient Outcomes

The model performed differently across the four outcome categories.

| Patient Outcome | Precision | Recall | F1-Score |
|---|---:|---:|---:|
| Improved | 0.740 | 0.671 | 0.704 |
| Unchanged | 0.385 | 0.455 | 0.417 |
| Referred | 0.250 | 0.147 | 0.185 |
| Died | 0.425 | 0.708 | 0.531 |

The model performed better when identifying patients in the Improved and Died categories.

However, its ability to identify Referred patients was particularly weak, with a recall of approximately 14.7%.

### Are Five Vital Signs Sufficient to Predict Patient Outcomes?

The project established predefined performance criteria to assess whether the five vital signs were sufficient for reliable classification.

The selected model did not meet the predefined requirements for:

- Test macro-F1 score of at least 0.70.
- Recall of at least 60% across all four outcome categories.
- A lower 95% confidence bound for accuracy exceeding the majority-class baseline.

The results therefore indicated that five vital signs alone were insufficient for reliable classification of all four patient outcomes in this synthetic dataset.

## Sensitivity Analysis

Additional analyses were performed to examine the robustness of the findings.

These included:

- Available-case statistical analysis.
- Median-imputation sensitivity analysis.
- Comparison of complete-case and imputed modelling results.
- Comparison of models using five original vital signs against models incorporating derived variables.
- Comparison of conventional ANOVA, Welch's ANOVA, and Kruskal–Wallis results.

The additional analyses generally supported the main findings. Incorporating the three derived variables did not improve the reported predictive performance over the five original vital signs.

## Limitations

- The dataset is synthetic and AI-generated. It does not represent verified real-world patient records.
- The relationships between vital signs and outcomes were introduced during synthetic data generation.
- The findings demonstrate statistical associations within the generated dataset, not real-world clinical relationships.
- The analysis used only five vital signs and did not include other potentially important clinical information such as age, diagnosis, comorbidities, laboratory results, or treatment history.
- The dataset contained measurements from a single time point rather than repeated observations over time.
- The test dataset contained 176 records, limiting the precision of some class-specific performance estimates.
- The model was not externally validated using an independent real-world healthcare dataset.

## Conclusion

This project demonstrated how Python, statistical analysis, and machine learning can be applied to investigate relationships between vital signs and patient clinical outcomes.

All five vital signs showed statistically significant differences across the four outcome categories, with respiratory rate demonstrating the strongest association.

However, statistical differences did not translate into reliable prediction across all outcome categories.

Balanced Logistic Regression achieved 53.4% accuracy and a macro-F1 score of 0.459 on the test dataset. Its performance was particularly limited when identifying patients in the Referred category.

The findings demonstrate an important distinction between statistical association and predictive sufficiency: variables may differ significantly across outcome groups without providing enough information to classify individual outcomes reliably.

Because the dataset is synthetic, these findings should be interpreted as an analytical and methodological demonstration rather than clinical evidence. The model is not intended for diagnosis, triage, treatment decisions, or patient care.

## About

A healthcare data analytics project applying Python, statistical hypothesis testing, effect-size analysis, and machine learning to investigate the relationship between patient vital signs and clinical outcomes using synthetic healthcare data.
