# Diabetes-Prediction
Diabetes Prediction - Machine Learning Project
## Objective
To predict whether a patient is diabetic or not based on 
medical diagnostic measurements using Machine Learning models.

## Dataset
- Source: Pima Indians Diabetes Database (Kaggle/UCI)
- 768 records, 9 features
- Target variable: Outcome (0 = No Diabetes, 1 = Diabetes)

## Data Cleaning
- Dataset had no null values but contained hidden missing values
- Medical columns like Glucose, BloodPressure, BMI cannot be zero
- Found zeros in:
  - Glucose: 5 rows
  - BloodPressure: 35 rows
  - SkinThickness: 227 rows
  - Insulin: 374 rows
  - BMI: 11 rows
- Replaced all zeros with median values of respective columns
## Key EDA Findings
- Glucose is the strongest predictor of diabetes (correlation = 0.49)
- BMI shows moderate correlation with diabetes (0.31)
- Age and Pregnancies also positively correlate with diabetes
- Dataset has mild class imbalance:
  - No Diabetes (0): 500 patients (65%)
  - Diabetes (1): 268 patients (35%)
## Feature Importance - Random Forest
Top predictors of diabetes identified by Random Forest:
1. Glucose - 0.26 (most important)
2. BMI - 0.16
3. Age - 0.14
4. DiabetesPedigreeFunction - 0.12
5. BloodPressure - 0.09
6. Insulin - 0.08
7. Pregnancies - 0.07
8. SkinThickness - 0.07 (least important)

Both correlation analysis and feature importance 
consistently ranked Glucose as the strongest predictor.
## Model Comparison
Three machine learning models were trained and evaluated:

| Model | Accuracy |
|-------|----------|
| Logistic Regression | 76.6% |
| Random Forest | 76.6% |
| SVM | 76.6% |

All three models gave consistent accuracy of 76.6%.
This suggests the dataset has a performance ceiling 
around this range, possibly due to:
- Mild class imbalance
- Limited number of features
- Dataset size (768 rows)
## Predictive System
Built an end-to-end prediction system that takes a 
patient's medical data as input and predicts 
whether the person is diabetic or not.

### Sample Input:
- Pregnancies: 4
- Glucose: 110
- BloodPressure: 92
- SkinThickness: 0
- Insulin: 0
- BMI: 37.6
- DiabetesPedigreeFunction: 0.191
- Age: 30

### Output: Person is NOT DIABETIC
## Conclusion

This end-to-end machine learning project predicts diabetes 
risk based on medical diagnostic data.

### Key Findings:
1. GLUCOSE is the strongest predictor of diabetes
2. BMI and Age are second and third most important features
3. All three models achieved consistent accuracy of 76.6%
4. Dataset has mild class imbalance (65% vs 35%)

### Limitations:
- Dataset limited to female patients above 21 years
- Class imbalance affects model performance on diabetic cases
- Recall for diabetic class (0.65) needs improvement

### Future Improvements:
- Apply SMOTE to handle class imbalance
- Try XGBoost and Neural Networks
- Deploy model using Streamlit for real time prediction

### Predictive System:
Built an end-to-end prediction system that takes patient 
medical data as input and predicts diabetes risk in real time.
