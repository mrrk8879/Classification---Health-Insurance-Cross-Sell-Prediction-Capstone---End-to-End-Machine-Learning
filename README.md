# Health Insurance Cross-Sell Prediction


## 📋 Table of Contents
- [Project Overview](#project-overview)
- [Business Context](#business-context)
- [Problem Statement](#problem-statement)
- [Dataset](#dataset)
- [Methodology](#methodology)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Key Insights](#key-insights)
- [Hypothesis Testing](#hypothesis-testing)
- [Data Preprocessing](#data-preprocessing)
- [Model Implementation](#model-implementation)
- [Model Evaluation](#model-evaluation)
- [Feature Importance](#feature-importance)
- [Business Impact](#business-impact)
- [Conclusion](#conclusion)

## 🔍 Project Overview
This project aims to predict whether health insurance policyholders will be interested in purchasing vehicle insurance. By developing a robust machine learning model, we help an insurance company target customers more effectively, optimize marketing strategies, and enhance overall business performance.

## 💼 Business Context
The client, a health insurance provider, offers both health and vehicle insurance products. Understanding which health insurance customers are likely to purchase vehicle insurance can significantly enhance the company's cross-selling efforts and improve customer lifetime value.

## 🎯 Problem Statement
In the competitive insurance industry, retaining existing customers and maximizing their lifetime value is crucial for business growth. The challenge is to identify which health insurance customers are most likely to purchase vehicle insurance, allowing for more targeted and efficient marketing campaigns.

Currently, the company lacks a systematic approach to predict customer interest in additional insurance products, resulting in inefficient marketing strategies, increased customer acquisition costs, and missed revenue opportunities.

## 📊 Dataset
The dataset comprises 381,109 records with 12 features:

### Variables Description
- **id**: Unique identifier for each customer
- **Gender**: Gender of the customer
- **Age**: Age of the customer
- **Driving_License**: Whether the customer holds a driving license (0/1)
- **Region_Code**: Region code of the customer
- **Previously_Insured**: Whether the customer previously had insurance (0/1)
- **Vehicle_Age**: Age of the vehicle
- **Vehicle_Damage**: Whether the customer had any previous vehicle damage (Yes/No)
- **Annual_Premium**: Amount paid for insurance annually
- **Policy_Sales_Channel**: Channel through which the policy was sold
- **Vintage**: Number of days the customer has been associated with the company
- **Response**: Target variable indicating interest in vehicle insurance (0/1)

## 🛠️ Methodology
1. Data Cleaning & Exploration
2. Exploratory Data Analysis & Visualization
3. Hypothesis Testing
4. Feature Engineering & Data Preprocessing
5. Model Development and Evaluation
6. Hyperparameter Tuning
7. Final Model Selection and Interpretation

## 📈 Exploratory Data Analysis

Key visualizations included:
- Distribution of response variable
- Gender distribution and response rates
- Impact of driving license on insurance interest
- Previously insured customers vs. response
- Vehicle age vs. response
- Age distribution vs. response
- Annual premium distribution
- Correlation analysis

## 💡 Key Insights

1. **Imbalanced Dataset**: Only about 12-13% of customers showed interest in vehicle insurance, indicating a highly imbalanced dataset.

2. **Gender Impact**: Male customers (17-18%) showed higher interest in vehicle insurance compared to female customers (12-13%).

3. **Driving License**: Customers without driving licenses showed virtually no interest in vehicle insurance.

4. **Previous Insurance**: Customers who were previously insured showed significantly less interest in purchasing new vehicle insurance.

5. **Vehicle Age**: Customers with vehicles older than 2 years showed the highest interest rate (nearly 50%), suggesting higher risk awareness.

6. **Customer Age**: Middle-aged customers (40-50 years) showed the highest interest in vehicle insurance.

7. **Annual Premium**: Premium distribution was heavily right-skewed with some outliers present.

## 🧪 Hypothesis Testing

Three hypotheses were tested:

1. **Gender and Response Rate**:
   - H0: Gender does not affect interest in vehicle insurance
   - H1: Gender affects interest in vehicle insurance
   - Result: Rejected H0 (p-value ≈ 0), confirming gender impacts insurance interest

2. **Age and Annual Premium**:
   - H0: No relationship between age and annual premium
   - H1: Relationship exists between age and annual premium
   - Result: Rejected H0 (p-value = 0), confirming correlation between age and premium

3. **Vehicle Age and Response**:
   - H0: Interest in vehicle insurance is independent of vehicle age
   - H1: Interest depends on vehicle age
   - Result: Rejected H0 (p-value = 0), confirming vehicle age affects insurance interest

## 🧹 Data Preprocessing

1. **Handling Missing Values**: No missing values were found in the dataset.

2. **Handling Outliers**: Outliers were detected in Annual Premium using IQR method but were retained to preserve valuable information.

3. **Categorical Encoding**: Ordinal encoding was applied to Gender, Vehicle Age, and Vehicle Damage.

4. **Feature Selection**: Tree-based feature importance was used to identify and retain the most relevant features.

5. **Data Transformation**: Log transformation was applied to Annual Premium to address right skewness.

6. **Data Scaling**: StandardScaler was used to normalize the numerical features.

7. **Handling Imbalanced Data**: SMOTE was applied to generate synthetic samples for the minority class after undersampling the majority class.

8. **Data Splitting**: 80% training and 20% testing split was used.

## 🔑 Feature Importance

The Random Forest model identified the following feature importances:

1. **Vintage (0.193)**: Length of customer relationship
2. **Annual_Premium (0.174)**: Amount paid for insurance
3. **Age (0.119)**: Customer age
4. **Region_Code (0.086)**: Geographic location
5. **Vehicle_Damage (0.071)**: Previous vehicle damage history
6. **Previously_Insured (0.058)**: Prior insurance status
7. **Policy_Sales_Channel (0.054)**: Sales channel used

## 🤖 Model Implementation

Several machine learning models were implemented:

1. **Logistic Regression**
2. **Random Forest**
3. **XGBoost**

Each model was further optimized using hyperparameter tuning.

## 📏 Model Evaluation

| Model | Accuracy | Precision | Recall | F1 Score | AUC-ROC |
|-------|----------|-----------|--------|----------|---------|
| Logistic Regression | 0.7836 | 0.70 | 0.98 | 0.82 | 0.78 |
| Random Forest (Base) | 0.8583 | 0.83 | 0.90 | 0.86 | 0.9448 |
| Random Forest (Tuned) | 0.8331 | 0.77 | 0.94 | 0.85 | 0.9147 |
| XGBoost (Base) | 0.8239 | 0.78 | 0.91 | 0.84 | 0.9183 |
| XGBoost (Tuned) | 0.8314 | 0.79 | 0.91 | 0.84 | 0.9241 |

The **Base Random Forest** model was selected as the final model due to its superior performance across multiple metrics, particularly its high precision, good recall, and excellent AUC-ROC score.



## 💰 Business Impact

1. **Targeted Marketing**: The model enables precise identification of customers likely to purchase vehicle insurance, reducing marketing costs and improving conversion rates.

2. **Customer Insights**: Feature importance analysis provides valuable insights into customer behavior and preferences, guiding product development and marketing strategies.

3. **Reduced Acquisition Costs**: By focusing on high-probability prospects, the company can reduce customer acquisition costs.

4. **Improved Customer Experience**: Targeted offerings enhance customer experience by avoiding irrelevant marketing communications.

5. **Revenue Growth**: Effective cross-selling increases revenue per customer and overall company growth.

## 🏁 Conclusion

The project successfully developed a predictive model to identify health insurance customers likely to purchase vehicle insurance. The Random Forest model, with its balanced performance in precision, recall, and AUC-ROC, provides a robust solution for the company's cross-selling efforts.

Key factors influencing customer interest include customer vintage, annual premium amount, customer age, and region. These insights can guide targeted marketing strategies and personalized customer interactions.

Future work could focus on advanced feature engineering, continuous model refinement, and integration with the company's CRM systems for real-time predictions and recommendations.

---

*This project demonstrates the value of machine learning in making data-driven decisions and optimizing business outcomes in the insurance industry.*
