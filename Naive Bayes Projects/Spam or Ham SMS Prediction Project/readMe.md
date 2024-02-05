## Spam or Ham SMS Prediction:

**Dataset Overview:**
SMS Spam Collection dataset from Kaggle. The dataset has 5572 rows and 4 columns. Each row corresponds to an SMS message and has a label of 'spam' or 'ham' associated with it.

**Objective:**

To create a text classification model that could predict the label 'spam' or 'ham' for a given SMS message.

**Approach:**

1. Checked for duplicates.
2. Checked missing values.
3. Handled data imbalance through the minority class oversampling method.
4. Did the following text pre-processing for the SMS message: 
    4.1 Removed the punctuations.
    4.2 Coverted the text into lowercase.
    4.3 Did **word tokenization**, **removed stop words**, applied 
    **Stemming technique** using the **nltk library** and got the normalized 
    SMS message.
    4.4 Used **CountVectorizer** to get **Bag of Words** for the corpus containing SMS messages.
5. Split the data into train and test.
6. Model Selection and model building: Since we have a text classification problem. I have used the **Bernoulli Naive Bayes Classifier** and **Multinomial Naive Bayes Classifier**.
7. Evaluated the model performance.
8. Reported the model performance.