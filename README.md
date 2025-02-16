# United-India-Health-Insurance-Cross-Sell-Prediction
End-to-End Machine Learning Classification Project



## Overview

This repository contains a predictive model developed to forecast whether customers with existing health insurance will be interested in purchasing vehicle insurance from the same provider, United India. The model leverages various customer attributes and historical insurance data to generate predictions that can help optimize the company's communication strategy, enhance business revenue, and improve customer acquisition.


**Business Context**

Our client United India, an insurance company, currently offers health insurance to its customers. They now seek assistance in developing a model to predict whether these policyholders from the past year might also be interested in purchasing vehicle insurance from the company.

Developing a model to predict which customers might be interested in vehicle insurance is crucial for our client. It will enable them to tailor their communication strategy effectively, optimize their business model, and enhance revenue.

To build this predictive model, we used information about customer demographics (e.g., gender, age, region), vehicle details (e.g., vehicle age, damage status), and policy information (e.g., premium amount, sales channel).

**Objective:**

The objective of this project is to develop a predictive model that identifies which existing health insurance policyholders are likely to be interested in purchasing vehicle insurance from the same provider. By leveraging customer demographics, vehicle details, and policy information, the model aims to enhance targeted marketing efforts, optimize communication strategies, and increase revenue for the company. This approach will enable the company to prioritize high-potential leads, improve customer engagement, and ultimately refine their business model to achieve greater efficiency and profitability.


## Dataset Description

The dataset used for this project includes the following features:

- **id**: Unique ID for the customer
- **Gender**: Gender of the customer (Male/Female)
- **Age**: Age of the customer
- **Driving License**: Whether the customer has a driving license (Yes/No)
- **Region_Code**: Unique code representing the region of the customer
- **Previously_insured**: Whether the customer already has vehicle insurance (Yes/No)
- **Vehicle_age**: Age of the vehicle
- **Vehicle_damage**: Whether there are past damages present on the vehicle (Yes/No)
- **Annual_premium**: Amount the customer needs to pay as a premium
- **Policy SalesChannel**: Anonymized code for the channel used to outreach to the customer
- **Vintage**: Number of days the customer has been associated with the company
- **Response**: Whether the customer is interested in vehicle insurance (Yes/No)

  


## Objectives

1. Develop a predictive model to identify customers likely to purchase vehicle insurance.
2. Optimize the company’s marketing strategy based on predictive insights.
3. Enhance business revenue through targeted communication and personalized offerings.



## Methodologies

### Data Manipulation and Preparation

1. Created a shallow copy of the original DataFrame for backup purposes.
2. Dropped the unique identifier (`id`) as it does not contribute to our analysis.
3. Converted binary columns (`Driving License`, `Previously_insured`, and `Response`) to categorical values ("Yes" and "No") to simplify visualizations.
4. Converted float data types to integers to reduce memory usage.
5. Created an additional column to categorize customers based on their association duration (`vintage`) into long-term, intermediate, and short-term customers.

### Exploratory Data Analysis (EDA)

- Utilized various visualization techniques like bar charts, pie charts, scatter plots, histograms, and heat maps to understand relationships between variables.
- Performed feature engineering and data pre-processing, including:
  - Identifying and handling outliers using box plots.
  - Scaling data using Min-Max Scaler.
  - Encoding categorical variables using ordinal and label encoding.
  - Addressing class imbalance using SMOTE (Synthetic Minority Over-sampling Technique).

### Model Development

- Implemented three machine learning models:
  - Logistic Regression
  - Decision Tree
  - XGBoost
- Performed hyperparameter tuning using Grid Search and applied stratified k-fold cross-validation to ensure model robustness.

## Insights and Recommendations

### Key Insights

1. **Customer Segmentation**: 
   - Long-term customers show a higher likelihood of purchasing vehicle insurance, indicating a strong potential for cross-selling.
   - Customers with past vehicle damage history are more inclined to seek vehicle insurance.

2. **Marketing Strategy**:
   - Focus marketing efforts on customers with driving licenses, as they are more likely to own vehicles.
   - Prioritize recent vehicle buyers (vehicle age between 1-2 years) for cross-selling efforts.
   - Tailor marketing messages based on gender, considering the differing levels of interest in vehicle insurance.

3. **Feature Importance**:
   - The `Vehicle_damage`, `Previously_insured`, and `Vehicle_age` columns were among the most significant predictors in the model.

### Recommendations

- **Customer Segmentation**: 
  - Implement targeted marketing campaigns for long-term customers with personalized rewards.
  - Streamline claim processes for intermediate customers to encourage loyalty.
  - Offer discounts and promotions to attract short-term customers.

- **Targeted Marketing**:
  - Focus on customers with past vehicle damage history, as they are more likely to purchase insurance.
  - Prioritize customers with driving licenses and recent vehicle purchases.

- **Gender-Based Customization**:
  - Tailor product offerings based on gender insights, particularly to engage male customers who showed higher disinterest.

## Model Selection

After comparing the three models, we selected the **Decision Tree** as the final prediction model due to its superior performance across various evaluation metrics, including accuracy, precision, recall, F1-score, and AUC ROC score. 

- **Logistic Regression**: Underperformed with unsatisfactory metric scores.
- **XGBoost**: Performed moderately well but did not surpass the Decision Tree.
- **Decision Tree**: Achieved the highest scores and demonstrated the best overall performance.

## Conclusion

Deploying the Decision Tree model is the optimal choice for the insurance company's cross-selling efforts. Leveraging the insights gained from our analysis, the company can enhance its vehicle insurance cross-selling strategies by offering discounts, tailoring products based on demographics, and improving the claim settlement process. This targeted approach will allow the company to focus its marketing efforts effectively, ultimately driving revenue growth.



