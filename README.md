# Vital Signs and Patient Clinical Outcomes: A Statistical and Machine Learning Analysis

**Healthcare Data Analytics Project | Python, Statistical Inference & Predictive Modeling**

## Project Overview
This project analyzed a synthetic dataset of **1,000 patient records** to evaluate how five core vital signs—heart rate, systolic/diastolic blood pressure, respiratory rate, body temperature, and oxygen saturation ($\text{SpO}_2$)—relate to four clinical outcomes: **Improved**, **Unchanged**, **Referred**, and **Died**.

After data cleaning and validation, **878 patient records** were retained for statistical hypothesis testing and multinomial classification modeling.

**Tech Stack:** Python (`pandas`, `NumPy`, `SciPy`, `Pingouin`, `scikit-learn`, `Matplotlib`, `Seaborn`)

---

## Project Artifacts & Resources
* **Full Analysis Report:** [View Full Project Report (PDF)](Vital_Signs_Patient_Outcomes_Analysis_Report.pdf)
* **Analysis Code:** [View Project Jupyter Notebook](YOUR_NOTEBOOK_LINK_HERE) *(Note: Replace with your current link)*
* **Datasets:**
  * [Raw (Dirty) Dataset (.xlsx)](Dirty_Vital_Signs_Analysis_Dataset.xlsx)
  * [Cleaned Dataset (.xlsx)](Cleaned_Vital_Signs_Analysis_Dataset.xlsx)

> **Data Note:** This project uses AI-generated synthetic data and contains no real patient records. It was built to demonstrate end-to-end clinical data cleaning, statistical testing, and machine learning evaluation.

---

## Methodology
1. **Data Cleaning & Clinical Validation (1,000 → 878 records):**
   Removed **122 records (12.2%)** due to [insert exact reasons from your report, e.g., missing values, duplicate entries, and physiologically implausible vital sign readings].
2. **Exploratory Data Analysis (EDA):**
   Examined vital sign distributions, skewness, and outliers across the four clinical outcome groups.
3. **Statistical Hypothesis Testing & Effect Size:**
   Tested group differences across outcomes and quantified practical significance using eta-squared ($\eta^2$).
4. **Correlation & Multicollinearity Checks:**
   Evaluated inter-variable relationships among vital signs prior to modeling.
5. **Predictive Modeling & Evaluation:**
   Trained a **Multinomial Logistic Regression** classifier and evaluated performance using **Accuracy, Precision, Recall, Macro-F1, and ROC-AUC**.

---

## Key Findings
* **Statistically Significant Differences:** All five vital signs showed statistically significant variation across the four clinical outcome groups.
* **Primary Clinical Driver:** **Respiratory rate** demonstrated the strongest association with patient outcomes ($\eta^2 = 0.373$), consistent with bedside clinical observations where tachypnea is an early indicator of physiological deterioration.
* **Model Performance:** Multinomial Logistic Regression achieved **53.4% overall accuracy** and a **macro-F1 score of 0.459**.
* **Class-Level Recall Gap:** While the model separated *Improved* and *Died* outcomes reasonably well, it struggled to detect *Referred* cases (**14.7% recall**), highlighting overlap in baseline vital signs between intermediate clinical states.

---

## Clinical & Analytical Conclusion
**Statistical significance did not translate into strong standalone predictive accuracy.** While vital signs—particularly respiratory rate—clearly differentiate extreme clinical outcomes at the group level, five static vital signs alone are insufficient to reliably classify all four patient trajectories.

### Future Improvements (Clinical Perspective)
* **Richer Clinical Features:** Incorporating laboratory markers (e.g., lactate, WBC, creatinine), patient age, comorbidities, and neurological status (AVPU/GCS) would provide essential context for intermediate outcomes like *Referred*.
* **Temporal Trends:** Capturing serial vital sign changes (deltas over time) rather than single-point measurements would better reflect patient deterioration or recovery.
* **Handling Class Imbalance:** Applying class weighting or resampling techniques (e.g., SMOTE) alongside tree-based models (Random Forest, XGBoost) to improve minority-class recall.

---

## Disclaimer
This is an educational portfolio project using synthetic healthcare data. It does not constitute clinical evidence or a validated clinical decision-support tool.

**Author:** Umar Ramadan, RN | [umarramadan206@gmail.com](mailto:umarramadan206@gmail.com)
