## BasketBuddy: Mining Patterns in Mall Shopping

**Dataset Overview:**
Market_Basket_Optimisation dataset from Kaggle. The dataset has 7501 rows and 20 columns. Each row represents a transaction which contains the list of items purchased in that transaction. 

**Objective:**
To systematically find the association rules b/w itemsets **(i.e. X => Y)**. 

**Approach:**
1. Pre-processed the dataset to remove all the NaN values from each row.
2. Identified the unique items from all the transactions along with their incident count.
3. Visualized the Top 36 frequently occurring items using a **TreeMap**.
4. Generated the frequently occurring itemsets using the **Apriori Algorithm**.
5. Identified 95 association rules using the frequent itemsets based on the **Confidence metric**.
6. Did a sanity check of the obtained association rules by using custom functions get_itemset_occurrences() and get_support() to verify the metrics for one of the 95 generated association rules.
7. Summarized the results.