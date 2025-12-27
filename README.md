# Stroke Risk Prediction using Machine Learning

This project investigates the association between demographic, clinical, and lifestyle risk factors and the occurrence of stroke using population-level health survey data. Using exploratory data analysis, statistical testing, and multiple machine learning classification models, the study aims to identify key predictors of stroke and evaluate model performance for accurate risk prediction.

---

## Dataset

- **Source:** Behavioral Risk Factor Surveillance System (BRFSS) dataset (Kaggle)
- **Format:** CSV
- **Size:** 40,910 records × 11 features
- **Target Variable:** Stroke (Yes / No)

### Key Features
- Demographic: Age, Sex, Ever Married, Work Type, Residence Type
- Clinical: Hypertension, Heart Disease, BMI, Average Glucose Level
- Lifestyle: Smoking Status

The dataset includes both categorical and continuous variables collected through self-reported health surveys :contentReference[oaicite:0]{index=0}.

---

## Project Objectives

- Analyze the impact of age, BMI, hypertension, smoking status, heart disease, and glucose levels on stroke occurrence
- Identify statistically significant risk factors associated with stroke
- Build and compare machine learning models for stroke prediction
- Evaluate model performance using classification metrics and ROC curves

---

## Methodology

### 1. Data Cleaning & Preprocessing
- Loaded data using **pandas**
- Identified missing values in the **gender** column and imputed using mode
- Removed invalid negative age values
- Converted numerical variables into categorical formats for visualization
- Detected BMI outliers using box plots and applied **winsorization** (5th–95th percentile) to cap extreme values

These steps ensured data consistency and reduced the influence of outliers on model performance :contentReference[oaicite:1]{index=1}.

---

### 2. Exploratory Data Analysis (EDA)
- Examined distributions of gender, smoking status, BMI, and glucose levels
- Visualized stroke occurrence across:
  - Gender
  - Hypertension status
  - Heart disease
  - BMI
  - Smoking status
  - Average glucose level

EDA revealed higher stroke prevalence among individuals with hypertension, heart disease, smoking habits, and elevated glucose levels :contentReference[oaicite:2]{index=2}.

---

### 3. Correlation Analysis
- Generated a correlation matrix using Pearson correlation
- Identified strong positive correlations between stroke and:
  - Hypertension
  - Heart disease
  - Average glucose level
  - Smoking status
- Observed a weak negative correlation between stroke and gender

---

### 4. Statistical Testing
- Performed **Chi-Square tests** to assess associations between stroke and categorical variables
- Variables such as gender, hypertension, smoking status, heart disease, BMI, and glucose levels showed statistically significant associations with stroke (p < 0.05)
- Null hypothesis was rejected for all tested variables, indicating meaningful relationships with stroke occurrence :contentReference[oaicite:3]{index=3}.

---

## Machine Learning Models

### Data Preparation
- Defined `stroke` as the dependent variable
- Applied **train–test split (80/20)**
- Dataset was naturally balanced; therefore, **SMOTE was not applied** to preserve original distribution :contentReference[oaicite:4]{index=4}.

### Models Implemented
- Logistic Regression
- K-Nearest Neighbors (KNN)
- Random Forest
- CatBoost Classifier

Each model was evaluated using accuracy, precision, recall, F1-score, and ROC-AUC.

---

## Results

### Occurrence of Stroke by Risk Factors
![Risk Factors](images/risk_factors.png)

### Correlation Heatmap
![Correlation Heatmap](images/correlation_heatmap.png)

### ROC Curve
![ROC Curve](images/roc_curve.png)

### Model Performance Comparison
![Model Performance](images/model_performance.png)

---

## Model Performance Summary

| Model               | Accuracy | Precision | Recall | F1-Score | ROC-AUC |
|---------------------|----------|-----------|--------|----------|---------|
| Random Forest       | 99%      | 100%      | 98%    | 99%      | 1.00    |
| CatBoost            | 82%      | 83%       | 80%    | 82%      | 0.91    |
| KNN                 | 84%      | 76%       | 94%    | 82%      | 0.89    |
| Logistic Regression | 67%      | 71%       | 58%    | 64%      | 0.72    |

The Random Forest classifier demonstrated superior predictive performance and generalization capability compared to other models :contentReference[oaicite:5]{index=5}.

---

## Conclusion

- Stroke occurrence is significantly associated with age, hypertension, heart disease, glucose level, BMI, smoking status, and gender
- Machine learning models effectively captured these relationships
- Random Forest emerged as the most reliable model for stroke prediction
- Findings support the use of ML-based risk assessment tools in public health and clinical decision-making

---

## Code

- Full implementation is available in:
  - `IntroProject_26thNov.ipynb`
- The notebook includes:
  - Data preprocessing
  - Visualization
  - Statistical testing
  - Model training and evaluation

---

## Limitations
- Only one dataset was used due to lack of merge-compatible identifiers
- Minor inconsistencies were observed in age values within the dataset

---

## References
- BRFSS Stroke Dataset (Kaggle)
- WHO Stroke Definition
- Volkow et al., 2017
