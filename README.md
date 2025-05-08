# Oral_Cancer_Analysis_ML_Project
Machine Learning on Oral Cancer Dataset
About the dataset:
The oral cancer prediction dataset is a comprehensive dataset based on real-world oral cancer statistics obtained from Kaggle.com. It includes data on primary oral cancer risk factors such as tobacco use, alcohol intake, HPV infection, and betel quid use.
Objective: 
•	Due to the increased risk of mortality from both primary causes and treatment complications, this machine learning model was built to predict the likely survival outcome of patients with existing risk factors or those already diagnosed with oral cancer. This will enable better prediction of treatment outcomes.
•	The prediction of the 5-year survival rate for patients with oral cancer was performed using either all features or selected features from the database, which includes patients’ medical history, clinical diagnosis, demographic information, and social factors such as the estimated financial burden on the patient.

Step 1. Preprocessing:
•	Handle missing values (mean/median imputation or KNN imputation).
•	Detect and remove outliers.
•	Encode categorical features (One-Hot or Label Encoding).
•	Normalize/standardize numerical features.

ML Process Employed:
There were no missing values in the dataset used for machine learning. The ‘Survival Rate (5-Year, %)’ was selected as the target feature.
This target variable was reclassified into four classes:
 0 (0–25%),
1 (26–50%),
2 (51–75%),
3 (76–100%).
The variable was renamed ‘Survival Rate (5-Year) Class’ for clarity.
Class Meaning:
0: Very low survival rate (0–25%)
1: Low survival rate (26–50%)
2: Medium survival rate (51–75%)
3: High survival rate (76–100%)

A label encoder was applied to the appropriate categorical columns in the original DataFrame (data). The target variable (Y) and features (X) were defined, and training/testing sets were created after encoding.

Step 2: Feature Selection:
•	Use techniques like correlation analysis, Chi_square test, or Recursive Feature Elimination (RFE) etc.

ML Process employed:
Columns that contributed the least valuable information (e.g., ‘ID’ and ‘Country’) were excluded to improve model performance.
Using F-statistics regression, 15 out of 22 features with the highest F-statistic scores were selected.

Selected Features:
['Age', 'Tobacco Use', 'Alcohol Consumption', 'Poor Oral Hygiene', 'Diet (Fruits & Vegetables Intake)', 'Compromised Immune System', 'Oral Lesions', 'White or Red Patches in Mouth', 'Tumor Size (cm)', 'Cancer Stage', 'Treatment Type', 'Cost of Treatment (USD)', 'Economic Burden (Lost Workdays per Year)', 'Early Diagnosis', 'Oral Cancer (Diagnosis)']

Step 3. Modeling:

•	Train classification models (e.g., Logistic Regression, Random Forest, SVM).

Step 4. Evaluation Metrics:
•	  Use Accuracy, Precision, Recall, F1-Score, ROC-AUC.
•	  Display confusion matrix and ROC curve.
ML Process employed:
Classification models including the Random Forest (RF), Logistic Regression (LR), LightGBM (LGBM) and XGBoost(XGB) models were trained to make predictions and evaluated using the default models.
Each model was trained and evaluated on a validation set with all features as well as with selected features.
Example Tuning:
Best parameters for LightGBM:
{'num_leaves': 31, 'n_estimators': 100, 'max_depth': 3, 'learning_rate': 0.1}
Table showing the model accuracy summary:
Classification Model	Accuracy (All Features)	Accuracy (Selected Features)	Accuracy (After Fine-Tuning)
Logistic Regression	0.6925	0.6933	0.6931

LightGBM	0.9800	0.9801	0.9822

XGBoost	0.9796	0.9791	0.9822

Random Forest	0.9804	0.9798	0.9814

To conclude, a visual display of the confusion matrix and multiclass ROC curve was generated for each optimized classification model to illustrate performance.
