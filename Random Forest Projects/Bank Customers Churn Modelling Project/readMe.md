## Bank Customers Churn Modelling:

**Dataset Overview:**
Churn Modelling dataset from Kaggle. The dataset has 10000 rows and 14 columns.

**Objective:**
To create a model that predicts if a customer would close their bank account and stop being a customer of the bank or not based on the given 13 input features.

**Approach:**
1. Handled missing values.
2. Handled outliers.
3. Applied Label Encoding/One-Hot-Encoding to categorical columns.
4. Did Data Visualization.
5. Applied Feature Scaling.
6. Handled imbalanced data using SMOTE.
7. Split the data into train and test.
8. Model Selection and model building: Since the output column is a nominal categorical variable, we are dealing with a classification problem. I have used the **Bagging Classifier** and **Random Forest Classifier**.
9. Evaluated the model performance and did cross-validation.
10. Reported the model performance.