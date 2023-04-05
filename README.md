# EngageML - Enhancing Customer Engagement through Machine Learning

This project aims to analyze a company's ideal customers by performing customer personality analysis. It helps businesses better understand their customers, making it easier to modify products according to the specific needs, behaviors, and concerns of different customer types.

## Dataset

The dataset used in this project is obtained from Kaggle [Customer Personality Analysis dataset](https://www.kaggle.com/datasets/imakash3011/customer-personality-analysis). It contains information about customers, their purchases, and interactions with the company. The dataset includes the following attributes:

### People

- ID: Customer's unique identifier
- Year_Birth: Customer's birth year
- Education: Customer's education level
- Marital_Status: Customer's marital status
- Income: Customer's yearly household income
- Kidhome: Number of children in customer's household
- Teenhome: Number of teenagers in customer's household
- Dt_Customer: Date of customer's enrollment with the company
- Recency: Number of days since customer's last purchase
- Complain: 1 if the customer complained in the last 2 years, 0 otherwise

### Products

- MntWines: Amount spent on wine in the last 2 years
- MntFruits: Amount spent on fruits in the last 2 years
- MntMeatProducts: Amount spent on meat in the last 2 years
- MntFishProducts: Amount spent on fish in the last 2 years
- MntSweetProducts: Amount spent on sweets in the last 2 years
- MntGoldProds: Amount spent on gold in the last 2 years

### Promotion

- NumDealsPurchases: Number of purchases made with a discount
- AcceptedCmp1: 1 if the customer accepted the offer in the 1st campaign, 0 otherwise
- AcceptedCmp2: 1 if the customer accepted the offer in the 2nd campaign, 0 otherwise
- AcceptedCmp3: 1 if the customer accepted the offer in the 3rd campaign, 0 otherwise
- AcceptedCmp4: 1 if the customer accepted the offer in the 4th campaign, 0 otherwise
- AcceptedCmp5: 1 if the customer accepted the offer in the 5th campaign, 0 otherwise
- Response: 1 if the customer accepted the offer in the last campaign, 0 otherwise

### Place

- NumWebPurchases: Number of purchases made through the company’s website
- NumCatalogPurchases: Number of purchases made using a catalogue
- NumStorePurchases: Number of purchases made directly in stores
- NumWebVisitsMonth: Number of visits to the company’s website in the last month

## Data Preparation

### Feature Engineering

Feature engineering involves creating new features from existing ones to improve the model's performance. In this project, we created new features by combining existing ones or by transforming them to better represent the underlying patterns in the data.

Before building the models, some feature engineering was performed on the dataset to create more meaningful features that can better explain the customer behavior. The following features were added:

- Age: The customer's age was derived from their birth year. Age can be a significant factor in customer behavior, as it may affect their spending habits, interests, and priorities.
- Total Children: A new feature was created by summing up the number of children and teenagers in the customer's household (Kidhome + Teenhome). This feature is relevant because customers with children may have different buying habits than those without children.
- Total Spent: A new feature was created by summing up the amount spent on all products (MntWines, MntFruits, MntMeatProducts, MntFishProducts, MntSweetProducts, MntGoldProds). This feature gives an overall view of the customer's spending behavior, which can be useful in identifying high-value customers.
- Response Rate: A new feature was created by summing up the customer's responses to all campaigns (AcceptedCmp1-5, Response). This feature indicates the customer's engagement level with the company's promotions and can be used to identify highly responsive customers.

The above features were chosen because they provide a more comprehensive view of the customer's behavior and preferences, which can help in segmenting the customers based on their value to the company.

For example, by including the age feature, we can analyze the behavior of customers of different age groups. Similarly, by including the total children feature, we can analyze the behavior of customers with different family sizes. The total spent feature gives an idea of the overall value of a customer to the company, and the response rate feature helps in identifying highly responsive customers who may be more likely to purchase again.

Overall, these features were selected to provide a more in-depth analysis of the customer behavior, which can help the company develop targeted marketing strategies for each customer segment and improve customer retention.

### Data Splitting

The dataset was split into training (75%), validation (25%), and test (70% of the validation set) sets. This ensures a fair evaluation of the models' performance on unseen data.

## Model Training

We trained and evaluated multiple machine learning models:

1. Logistic Regression
2. Support Vector Machine
3. K-Nearest Neighbors
4. Naive Bayes
5. Gradient Boosting Tree
6. Ensemble Model

## Ensemble Model

The Ensemble model was chosen because it provided a good balance between precision and recall. A balance between precision and recall is essential in real-world applications to minimize false positives and false negatives, ensuring that the model can make accurate predictions and minimize potential harm.

## Future Work

### Streamlit App

In the next phase of this project, we plan to develop a Streamlit app to create an interactive web application that allows users to explore the data, visualize different variables, and make predictions using the trained Ensemble model. This app will make it easier for stakeholders to understand the customer segmentation and help make informed decisions about marketing strategies and resource allocation.

### CRM-RFM Analysis

We also plan to perform CRM-RFM (Customer Relationship Management - Recency, Frequency, Monetary) analysis to further segment customers based on their purchasing behavior. RFM analysis assigns each customer a score for the following metrics:

- Recency: How recently a customer has made a purchase
- Frequency: How frequently a customer makes purchases
- Monetary Value: How much a customer spends on purchases

These scores will then be used to segment customers into groups based on their overall RFM score. This segmentation helps businesses identify which customers are most valuable and should receive priority attention, and which customers are less valuable and may require less attention or targeted marketing efforts.

By using RFM analysis, businesses can:

- Develop targeted marketing strategies for each customer segment
- Improve customer retention
- Increase overall revenue by focusing on their most valuable customers

The combination of customer personality analysis and CRM-RFM analysis will provide a comprehensive understanding of the company's customer base, allowing for more effective and efficient marketing and customer relationship management strategies.
