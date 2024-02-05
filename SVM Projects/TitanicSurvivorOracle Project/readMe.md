## TitanicSurvivorOracle: Unveiling the Fate of Passengers through ML

**Dataset Overview:**
Churn Modelling dataset from Kaggle. The dataset has 891 rows and 12 columns.

**Objective:**
To create a model to predict the people who survived the shipwreck based on the given 11 input features.

**Approach:**
1. Did feature selection by dropping the irrelevant columns/variables.
2. Handled missing values.
3. Checked for outliers.
4. Applied Label Encoding/One-Hot-Encoding to categorical columns.
5. Did Exploratory Data Analysis(EDA).
6. Checked for imbalanced data.
7. Split the data into train and test.
8. Model Selection and model building: Since the output column is a nominal categorical variable with only 2 classes, we are dealing with a binary classification problem. I have used the **Support Vector Machine Classifier** using different kernels like **Linear**,
**Polynomial**, **RBF**, **Sigmoid**.
9. Evaluated the SVM model performance.
10. Used **GridSearchCV** to get the best hyperparameters for SVM.
11. Compared the SVM model with **Logistic Regression** and **Decision Tree classifier**.
12. Used the **Hard and Soft VotingClassifier** to combine multiple models.
13. Reported the performance of the different feasible models built for this
problem.