# Uncovering-Shopping-Patterns-Market-Basket-Analysis-of-Grocery-Data
In this Market Basket Analysis, I prepared a grocery store dataset by combining member numbers and transaction dates to create a structured transaction objects. Utilizing the arules package, I generated association rules using the Apriori algorithm, exploring different lengths of antecedents to understand item relationships, and visualized the results with methods such as scatter plots and grouped matrix plots.

Subsequently, I performed frequent pattern analysis with the FP-Growth algorithm to identify common itemsets within transactions. Finally, I applied K-means clustering to categorize items based on purchase frequency, using the Elbow Method to determine the optimal number of clusters. Each item was labeled as low, medium, or high frequency, providing valuable insights into customer behavior and informing marketing strategies such as product placements and promotions.

--- 

### 1. Data Preparation for Market Basket Analysis
- Data Import:
  - Loaded the grocery dataset using read.csv to initiate the market basket analysis.
- Initial Data Exploration:
  - Displayed the first few rows of the dataset to understand its structure and content, along with checking its structure with str() for data types and information regarding the dataframe.
- Package Installation and Loading:
  - Installed and loaded the arules package, which is essential for conducting association rule mining.
- Transaction Identifier Creation:
  - Created a unique TransactionID by combining 'Member_number' and 'Date', ensuring that each transaction can be distinctly identified.
- Data Aggregation:
  - Aggregated items associated with each TransactionID using the split function, organizing items within their respective transactions.
- Transaction Object Conversion:
  - Converted the aggregated data into a transaction object, which is a format suitable for conducting market basket analysis and applying the Apriori algorithm. 
- Further Data Exploration:
  - Conducted additional checks on the new data structure (mba_data) and displayed the first few rows to confirm that the data preparation steps were done correctly.

![1](https://github.com/user-attachments/assets/f8c8bd2d-4aa4-4f14-b49a-6ae93a74e434)

--- 

### 2. Market Basket Analysis with 1 antecedent and 1 consequent
- Rule Generation with Apriori Algorithm:
  - Employed the Apriori algorithm on the transaction data to generate association rules, setting support at 0.0008 (which corresponds to approximately 31 transactions, given the dataset consists of 38,765 observations) and confidence at 0.20 to identify relevant item relationships.
- Filtering Rules:
  - Filtered the generated rules to retain only those that possess exactly one antecedent and one consequent, focusing on simpler and more interpretable rules.
- Summary of Rules:
  - Viewed a summary of the filtered rules to gain insights into key metrics such as support, confidence, and lift, allowing for an assessment of the strength of the rules.
 
![2](https://github.com/user-attachments/assets/980e91d4-5992-4aaf-b36a-5d0a154b023f) 

- Top Rules Inspection:
  - Inspected the top 10 filtered rules to identify the most significant associations based on the defined parameters, helping to understand customer purchasing behavior.
- Visualization Preparation:
  - Loaded necessary visualization packages (arules and arulesViz) to aid in the graphical representation of the association rules.
- Graphical Representation:
  - Produced a graph using the 'graph' method, employing HTML widgets for dynamic visualization of the association rules, aiding in the exploration of item relationships in a more interactive format.

![3](https://github.com/user-attachments/assets/37bd0cd0-e3fd-448e-bd42-1d9f08d98292)


- Interpretation of Results:
  - Rule 1: {brandy} => {whole milk}
    - Support: This rule occurs in approxmately 31 observations (from the 38765 total observations)
    - Confidence: (34.21%) - If a customer buys brandy, there is a 34.21% chance they also buy whole milk.
    - Lift (2.1663) - Customers buying {brandy} are 2.17 times more likely to buy {whole milk} compared to random transactions, which indicates a strong association.

  - Rule 2: {softener} => {whole milk}
    - Support: This rule occurs in approxmately 31 observations (from the 38765 total observations)
    - Confidence: (29.27%) - If a customer buys softener, there is a 29.27% chance they also buy whole milk.
    - Lift (1.8533) - Softener buyers are 1.85 times more likely to buy whole milk than random transactions, showing a moderate positive association.

  - Rule 3: {finished products} => {whole milk}
    - Support: This rule occurs in approxmately 31 observations (from the 38765 total observations)
    - Confidence: (20.31%) - If a customer buys finished products, there is a 20.31% chance they also buy whole milk.
    - Lift (1.2862) - Finished product buyers are 1.29 times more likely to buy whole milk than random transactions, indicating a weak positive association

---

### 3. Market Basket Analysis with 2 antecedents and 1 consequent
- Rule Generation with Apriori Algorithm:
  - Employed the Apriori algorithm on the transaction data to generate association rules, setting support at 0.0008 (which corresponds to approximately 31 transactions, given the dataset consists of 38,765 observations) and confidence at 0.20 to identify relevant item relationships.
- Filtering Rules:
  - Filtered the generated rules to retain only those that possess exactly two antecedents and one consequent.
- Summary of Rules:
  - Viewed a summary of the filtered rules to gain insights into key metrics such as support, confidence, and lift, allowing for an assessment of the strength of the rules.
 
![4](https://github.com/user-attachments/assets/c9a7f939-3980-4265-ba77-ac953e8fc4d4)
 

- Top Rules Inspection:
  - Inspected the top 10 filtered rules to identify the most significant associations based on the defined parameters, helping to understand customer purchasing behavior.
- Visualization Preparation:
  - Loaded necessary visualization packages (arules and arulesViz) to aid in the graphical representation of the association rules.
- Graphical Representation:
  - Produced a graph using the 'graph' method, employing HTML widgets for dynamic visualization of the association rules, aiding in the exploration of item relationships in a more interactive format.

![5](https://github.com/user-attachments/assets/a019353d-006b-44c1-8bd4-bfcf52e031e6)


- Interpretation of Results:
  - Rule 1: {pastry, soda} => {whole milk}
    - Support: This rule occurs in approximately 34 observations (from the 38765 total observations).
    - Confidence: (22.95%) - If a customer buys {pastry} and {soda}, there is a 22.95% chance they also buy {whole milk}.
    - Lift: (1.4533) - Customers buying {pastry} and {soda} are 1.45 times more likely to buy {whole milk} compared to random transactions, indicating a weak positive association.
  - Rule 2: {sausage, yogurt} => {whole milk}
    - Support: This rule occurs in approximately 56 observations (from the 38765 total observations).
    - Confidence: (25.58%) - If a customer buys {sausage} and {yogurt}, there is a 25.58% chance they also buy {whole milk}.
    - Lift: (1.6199) - Customers buying {sausage} and {yogurt} are 1.62 times more likely to buy {whole milk} compared to random transactions, indicating a moderate positive association.
  - Rule 3: {rolls/buns, sausage} => {whole milk}
    - Support: This rule occurs in approximately 44 observations (from the 38765 total observations).
    - Confidence: (21.25%) - If a customer buys {rolls/buns} and {sausage}, there is a 21.25% chance they also buy {whole milk}.
    - Lift: (1.3456) - Customers buying {rolls/buns} and {sausage} are 1.35 times more likely to buy {whole milk} compared to random transactions, indicating a weak positive association.
