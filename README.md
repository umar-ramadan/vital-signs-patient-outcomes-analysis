# Vital Signs and Patient Clinical Outcomes: A Statistical and Machine Learning Analysis

### Healthcare Data Analytics Project Using Python

## Project Overview

This project analysed a synthetic dataset of 1,000 patient records to examine the relationship between five vital signs and four clinical outcomes: Improved, Unchanged, Referred and Died.

After data cleaning, 878 records were used for statistical analysis and machine learning.

**Tools:** Python, pandas, NumPy, SciPy, Pingouin and scikit-learn.

## Project Report

[**View Full Project Report (PDF)**](https://github.com/umar-ramadan/vital-signs-patient-outcomes-analysis/blob/main/Vital_Signs_Patient_Outcomes_Analysis_Report.pdf)

## Datasets

- [**Raw (Dirty) Dataset**](https://github.com/umar-ramadan/vital-signs-patient-outcomes-analysis/blob/main/Dirty_Vital_Signs_Analysis_Dataset.xlsx)
- [**Cleaned Dataset**](https://github.com/umar-ramadan/vital-signs-patient-outcomes-analysis/blob/main/Cleaned_Vital_Signs_Analysis_Dataset.xlsx)

**Note: This project uses AI-generated synthetic data and does not contain real patient records. Its primary purpose is to demonstrate my skills in healthcare data analytics, statistical analysis and machine learning.**

## Methods

- Data cleaning and exploratory data analysis.
- Statistical hypothesis testing and effect-size analysis.
- Correlation and multicollinearity analysis.
- Multinomial Logistic Regression.
- Model evaluation using accuracy, precision, recall, F1-score and ROC-AUC.

## Key Findings

- All five vital signs differed significantly across the four outcome groups.
- Respiratory rate showed the strongest association with patient outcomes (η² = 0.373).
- The best-performing model achieved 53.4% accuracy and a macro-F1 score of 0.459.
- The model identified Improved and Died outcomes more effectively but struggled to identify Referred cases (14.7% recall).
- Overall, five vital signs alone were insufficient for reliable classification of all four outcomes.

## Conclusion

Statistical differences between patient outcome groups did not translate into strong predictive performance. The findings highlight the limitations of using only five vital signs to predict clinical outcomes.

## Analysis Code

[**View Project Jupyter Notebook**]()

## Disclaimer

This is an educational project using synthetic data. It does not constitute clinical evidence or a validated tool for patient-care decisions.

**AUTHOR: Nrs Umar Ramadan**
