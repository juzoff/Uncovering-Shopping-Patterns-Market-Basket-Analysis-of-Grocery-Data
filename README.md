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

---

### 4. Market Basket Analysis with 3 antecedents and 1 consequent
- Rule Generation with Apriori Algorithm:
  - Employed the Apriori algorithm on the transaction data to generate association rules, setting support at 0.0003 (which corresponds to approximately 11 transactions, given the dataset consists of 38,765 observations) and confidence at 0.20 to identify relevant item relationships.
- Filtering Rules:
  - Filtered the generated rules to retain only those that possess exactly three antecedents and one consequent.
- Summary of Rules:
  - Viewed a summary of the filtered rules to gain insights into key metrics such as support, confidence, and lift, allowing for an assessment of the strength of the rules.
 
![6](https://github.com/user-attachments/assets/0ea90e6c-4466-4bb2-8622-19dc09b91b40)


- Top Rules Inspection:
  - Inspected the top 10 filtered rules to identify the most significant associations based on the defined parameters, helping to understand customer purchasing behavior.
- Visualization Preparation:
  - Loaded necessary visualization packages (arules and arulesViz) to aid in the graphical representation of the association rules.
- Graphical Representation:
  - Produced a graph using the 'graph' method, employing HTML widgets for dynamic visualization of the association rules, aiding in the exploration of item relationships in a more interactive format.

![7](https://github.com/user-attachments/assets/88e9db2f-16c2-43da-925e-0fb972ede538)



- Interpretation of Results:
  - Rule 1: {other vegetables, pastry, soda} => {whole milk}
    - Support: This rule occurs in approximately 13 observations (from the 38765 total observations).
    - Confidence: (83.33%) - If a customer buys {other vegetables}, {pastry}, and {soda}, there is an 83.33% chance they also buy {whole milk}.
    - Lift: (5.2768) - Customers buying {other vegetables}, {pastry}, and {soda} are 5.28 times more likely to buy {whole milk} compared to random transactions, indicating a very strong association.
  - Rule 2: {pastry, soda, whole milk} => {other vegetables}
    - Support: This rule occurs in approximately 13 observations (from the 38765 total observations).
    - Confidence: (35.71%) - If a customer buys {pastry}, {soda}, and {whole milk}, there is a 35.71% chance they also buy {other vegetables}.
    - Lift: (2.9250) - Customers buying {pastry}, {soda}, and {whole milk} are 2.93 times more likely to buy {other vegetables} compared to random transactions, indicating a moderate to strong association.
  - Rule 3: {other vegetables, pastry, whole milk} => {soda}
    - Support: This rule occurs in approximately 13 observations (from the 38765 total observations).
    - Confidence: (50.00%) - If a customer buys {other vegetables}, {pastry}, and {whole milk}, there is a 50.00% chance they also buy {soda}.
    - Lift: (5.1490) - Customers buying {other vegetables}, {pastry}, and {whole milk} are 5.15 times more likely to buy {soda} compared to random transactions, indicating a very strong association.
  - Rule 4: {other vegetables, soda, whole milk} => {pastry}
    - Support: This rule occurs in approximately 13 observations (from the 38765 total observations).
    - Confidence: (29.41%) - If a customer buys {other vegetables}, {soda}, and {whole milk}, there is a 29.41% chance they also buy {pastry}.
    - Lift: (5.6859) - Customers buying {other vegetables}, {soda}, and {whole milk} are 5.69 times more likely to buy {pastry} compared to random transactions, indicating a very strong association.
  - Rule 5: {rolls/buns, sausage, yogurt} => {whole milk}
    - Support: This rule occurs in approximately 13 observations (from the 38765 total observations).
    - Confidence: (55.56%) - If a customer buys {rolls/buns}, {sausage}, and {yogurt}, there is a 55.56% chance they also buy {whole milk}.
    - Lift: (3.5179) - Customers buying {rolls/buns}, {sausage}, and {yogurt} are 3.52 times more likely to buy {whole milk} compared to random transactions, indicating a strong association.
  - Rule 6: {sausage, whole milk, yogurt} => {rolls/buns}
    - Support: This rule occurs in approximately 13 observations (from the 38765 total observations).
    - Confidence: (22.73%) - If a customer buys {sausage}, {whole milk}, and {yogurt}, there is a 22.73% chance they also buy {rolls/buns}.
    - Lift: (2.0660) - Customers buying {sausage}, {whole milk}, and {yogurt} are 2.07 times more likely to buy {rolls/buns} compared to random transactions, indicating a weak to moderate association.
  - Rule 7: {rolls/buns, sausage, whole milk} => {yogurt}
    - Support: This rule occurs in approximately 13 observations (from the 38765 total observations).
    - Confidence: (29.41%) - If a customer buys {rolls/buns}, {sausage}, and {whole milk}, there is a 29.41% chance they also buy {yogurt}.
    - Lift: (3.4248) - Customers buying {rolls/buns}, {sausage}, and {whole milk} are 3.42 times more likely to buy {yogurt} compared to random transactions, indicating a strong association.
  - Rule 8: {rolls/buns, whole milk, yogurt} => {sausage}
    - Support: This rule occurs in approximately 13 observations (from the 38765 total observations).
    - Confidence: (25.00%) - If a customer buys {rolls/buns}, {whole milk}, and {yogurt}, there is a 25.00% chance they also buy {sausage}.
    - Lift: (4.1426) - Customers buying {rolls/buns}, {whole milk}, and {yogurt} are 4.14 times more likely to buy {sausage} compared to random transactions, indicating a very strong association.

---

### 5. Market Basket Analysis with 4 antecedents and 1 consequent
- Rule Generation with Apriori Algorithm:
  - Employed the Apriori algorithm on the transaction data to generate association rules, setting support at 0.0002 (which corresponds to approximately 7 transactions, given the dataset consists of 38,765 observations) and confidence at 0.20 to identify relevant item relationships.
- Filtering Rules:
  - Filtered the generated rules to retain only those that possess exactly four antecedents and one consequent.
- Summary of Rules:
  - Viewed a summary of the filtered rules to gain insights into key metrics such as support, confidence, and lift, allowing for an assessment of the strength of the rules.
 
![8](https://github.com/user-attachments/assets/6ebf0f92-22f7-4bac-854b-fe5d0f3e2844)

- Top Rules Inspection:
  - Inspected the top 10 filtered rules to identify the most significant associations based on the defined parameters, helping to understand customer purchasing behavior.
- Visualization Preparation:
  - Loaded necessary visualization packages (arules and arulesViz) to aid in the graphical representation of the association rules.
- Graphical Representation:
  - Produced a graph using the 'graph' method, employing HTML widgets for dynamic visualization of the association rules, aiding in the exploration of item relationships in a more interactive format.

![9](https://github.com/user-attachments/assets/3e379251-3aea-4723-9282-a66f61bde9da)

- Interpretation of Results:
  - Rule 1: {pork, sausage, soda, yogurt} => {whole milk}
    - Support: This rule occurs in approximately 8 observations (from the 38765 total observations).
    - Confidence: (100%) - If a customer buys {pork}, {sausage}, {soda}, and {yogurt}, there is a 100% chance they also buy {whole milk}.
    - Lift: (6.3322) - Customers buying {pork}, {sausage}, {soda}, and {yogurt} are 6.33 times more likely to buy {whole milk} compared to random transactions, indicating a very strong association.
  - Rule 2: {pork, sausage, whole milk, yogurt} => {soda}
    - Support: This rule occurs in approximately 8 observations (from the 38765 total observations).
    - Confidence: (75%) - If a customer buys {pork}, {sausage}, {whole milk}, and {yogurt}, there is a 75% chance they also buy {soda}.
    - Lift: (7.7235) - Customers buying {pork}, {sausage}, {whole milk}, and {yogurt} are 7.72 times more likely to buy {soda} compared to random transactions, indicating a very strong association.
  - Rule 3: {pork, sausage, soda, whole milk} => {yogurt}
    - Support: This rule occurs in approximately 8 observations (from the 38765 total observations).
    - Confidence: (75%) - If a customer buys {pork}, {sausage}, {soda}, and {whole milk}, there is a 75% chance they also buy {yogurt}.
    - Lift: (8.7333) - Customers buying {pork}, {sausage}, {soda}, and {whole milk} are 8.73 times more likely to buy {yogurt} compared to random transactions, indicating a very strong association.
  - Rule 4: {pork, soda, whole milk, yogurt} => {sausage}
    - Support: This rule occurs in approximately 8 observations (from the 38765 total observations).
    - Confidence: (100%) - If a customer buys {pork}, {soda}, {whole milk}, and {yogurt}, there is a 100% chance they also buy {sausage}.
    - Lift: (16.5703) - Customers buying {pork}, {soda}, {whole milk}, and {yogurt} are 16.57 times more likely to buy {sausage} compared to random transactions, indicating an extremely strong association.
  - Rule 5: {sausage, soda, whole milk, yogurt} => {pork}
    - Support: This rule occurs in approximately 8 observations (from the 38765 total observations).
    - Confidence: (75%) - If a customer buys {sausage}, {soda}, {whole milk}, and {yogurt}, there is a 75% chance they also buy {pork}.
    - Lift: (20.2203) - Customers buying {sausage}, {soda}, {whole milk}, and {yogurt} are 20.22 times more likely to buy {pork} compared to random transactions, indicating an exceptionally strong association.

---

### 6. Frequent Pattern Analysis
- Utilized the arules package in R to conduct a thorough examination of item frequencies within the transaction dataset, which consists of 38,765 observations.
- Employed the itemFrequency function to count the absolute frequency of each item across all transactions, facilitating a clear understanding of item popularity.
- Sorted the computed item frequencies in descending order to easily identify the most frequently purchased items.
- Displayed the top five items by frequency, providing valuable insights into consumer preferences that can be leveraged for inventory management and targeted marketing initiatives.

![10](https://github.com/user-attachments/assets/1e3ce382-4edf-467b-8e6f-cffb0621cf3e)

- Interpretation:
  - Whole Milk (2363): This item is the most frequently purchased, with 2,363 transactions involving whole milk. Its high frequency indicates that it is a staple product for consumers and suggests strong household demand. Retailers might consider ensuring an ample supply of whole milk to meet customer needs.
  - Other Vegetables (1827): With 1,827 transactions, other vegetables rank second. This suggests that consumers are likely incorporating a variety of vegetables into their diets, opening opportunities for promotions or bundle deals involving fresh produce to encourage healthy eating.
  - Rolls/Buns (1646): This item appears in 1,646 transactions, indicating significant consumption, likely associated with meal preparation, such as sandwiches or burgers. Retailers could use this insight to promote related items, like spreads or meats, to boost sales.
  - Soda (1453): The frequency of 1,453 transactions for soda suggests its popularity as a beverage choice. Given health trends toward reducing sugary drink consumption, retailers might consider diversifying their beverage offerings or incorporating healthier alternatives alongside soda promotions.
  - Yogurt (1285): With 1,285 transactions, yogurt is a popular item, aligning with trends towards healthy snacking and breakfast options. This could be an opportunity for retailers to explore new yogurt flavors or packaging, as well as to promote yogurt alongside fresh fruits or cereals.

--- 

### 7. K-Means Clustering of Market Basket Data: Identifying Item Frequency Groups

- Data Aggregation and Scaling:
  - Aggregated market basket data to calculate the frequency of each item, then scaled the frequency values to standardize the dataset. Scaling is a crucial step for distance-based methods like k-means clustering to ensure that all features contribute equally to the distance calculations.

- Elbow Method for Optimal Clustering:
  - Conducted an analysis to determine the optimal number of clusters (k) by using the Elbow Method. This involved calculating the total within-cluster sum of squares (WSS) for k values ranging from 1 to 10 and plotting the results. The "elbow" point in the plot helps identify the point where adding more clusters yields diminishing returns in variance reduction.

![11](https://github.com/user-attachments/assets/fa333d3d-daf7-429b-a0cc-3de10201e899)

- K-Means Clustering Application:
  - Applied the k-means clustering algorithm with the identified optimal number of clusters (k=3) to group the items based on their purchase frequency. This process included initializing the algorithm with multiple random starts to enhance the chances of finding a global optimum.

- Cluster Assignment and Visualization:
  - Assigned items to their respective clusters and created a scatterplot to visualize the frequency of items against their cluster assignments. This visualization employs distinct colors for each cluster, making it easier to interpret cluster distribution related to purchase frequency.

![12](https://github.com/user-attachments/assets/338eae57-6b40-40f2-8e1d-fb5a3a8927b3)

- Descriptive Cluster Labeling:
  - Enhanced the cluster analysis by adding descriptive labels ("Low Frequency Items," "Medium Frequency Items," and "High Frequency Items") to the clustering results, which contextualizes the clusters and facilitates better understanding of item behavior in the market basket data.

 ![13](https://github.com/user-attachments/assets/71140ecd-f8ed-46a0-8e7c-0cb3b8dcb205)
