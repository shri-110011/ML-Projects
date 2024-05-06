## Sentiment Analysis on Amazon Product Reviews:

**Dataset Overview:**

Amazon Fine Food Reviews dataset from Kaggle. The dataset consists of reviews of fine foods from Amazon. The data span a period of more than 10 years, including all ~500,000 reviews up to October 2012. Reviews include product and user information, ratings, and a plain text review.

**Objective:**

To create a model that could assign a label to each review based on the sentiment
of the review text.
A label 0 indicates negative sentiment, 1 indicates neutral sentiment and 2 indicates positive sentiment.

**Approach:**
1. Checked for duplicate values in the reviews data frame(No duplicates found).

2. Did EDA on the reviews data frame and came to the following conclusion.

- Same user may have given multiple reviews.

- Same user may have given multiple reviews for same and different products.

- Two different users may have same ProfileName.

3. Dropped inconsistent rows(rows where HelpfulnessNumerator > HelpfulnessDenominator).

4. Removed duplicate rows considering 'UserId', 'ProfileName', 'Time', and 'Text' columns.

5. Selected 50000 reviews from the original 'reviews' data frame and applied text pre-processing to the 'Text' column which contains the review text.

The following text pre-processing operations have been done to get normalized
tokens for the 'Text' column.

- Used BeautifulSoup library to convert the text review which contains broken html into proper markup and then to extract the text from it.

- Used regex to handle review text that contains links not as the value of the href attribute of the anchor tag.

- Used the 'contractions' module to deal with English language contractions in the review text.

- Tokenized the review text. For this we decided to use **word_tokenize()** to tokenize the document because it splits text after each punctuation mark and handles special cases as well like it does not split when (.) appears in between a token like in 'Mr.John' or '12.23'. In the case of **Treebank tokenizer** for (.) split occurs only when periods appear at the end of the line like in the sentence 'The cat sleeps on the mat. The mat is soft and comfortable. ' for the last (.) a split would occur. 

- Removed the punctuation.

- Removed the stopwords.

- Used lemmatization to normalize the tokens.

6. Used **CountVectorizer** to create a matrix of binary occurrence counts using **binary=True** parameter.

7. Used the **Bag of Words** matrix containing binary occurrence counts and **TfidfTransformer** to get the TFIDF matrix.

8. Created the design matrix using the TFIDF matrix and the dependent variable vector using the 'Score' column of the 'reviews' data frame.

Applied thresholding to the 'Score' column i.e. scores of 4 and 5 are mapped to 2, scores of 3 are mapped to 1, and scores of 1 and 2 are mapped to 0.

9. Split the dataset into train and test.

10. Built the multiclass classifier using Random Forest and Gradient Boosting.

11. Evaluated the results and got the following conclusion.

**With Random Forest:**

We have an overfitting problem.
The model does well in classifying the training samples that actually belong to class 2(positive reviews). For class 1(neutral reviews) and class 0(negative reviews), the prediction is not good. This is because we have a highly imbalanced dataset.

**With Gradient Boost:**

We do not have any overfitting problem.
Again the model does well in classifying the training samples that actually belong to class 2(positive reviews). For class 1(neutral reviews) and class 0(negative reviews), the prediction is not good. This is because we have a highly imbalanced dataset.
