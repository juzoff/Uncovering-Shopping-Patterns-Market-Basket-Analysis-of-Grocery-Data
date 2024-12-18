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
- Top Rules Inspection:
  - Inspected the top 10 filtered rules to identify the most significant associations based on the defined parameters, helping to understand customer purchasing behavior.
- Visualization Preparation:
  - Loaded necessary visualization packages (arules and arulesViz) to aid in the graphical representation of the association rules.
- Graphical Representation:
  - Produced a graph using the 'graph' method, employing HTML widgets for dynamic visualization of the association rules, aiding in the exploration of item relationships in a more interactive format.
