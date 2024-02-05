## Iris Flower Species Classification:
  
**Dataset Overview:**
The Iris Flower dataset contains 150 rows and 5 columns. The observations have information about three species of Iris (Iris setosa, Iris versicolor, and Iris virginica).

**Objective:**
To create a model that predicts the species of an Iris flower using the features of that Iris flower and also to find out the important features that help us in this classification.

**Approach:**
1. Handled missing values.
2. Handled outliers.
3. Checked if Feature Scaling is required.
4. Split the data into train and test.
5. Model Selection and model building: Since the output column is a nominal categorical variable we are dealing with a classification problem. The number of
classes are more than 2 therefore I used **Decision Tree algorithm**.
6. Evaluated the model performance.
7. Plotted the decision tree to analyze it and to decide the hyperparameters for post-pruning.
8. Reported the model performance and important feature variables.