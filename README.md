# Invistico Airline Passenger Satisfaction prediction

## Project Overview

Customer satisfaction is a key driver of customer retention and profitability in the airline industry. This project uses machine learning to predict whether a passenger is satisfied or dissatisfied based on their travel experience, service ratings, and flight-related information.

The objective is to identify the most influential factors affecting customer satisfaction and provide actionable recommendations that can help airlines improve customer experience and operational performance.

---

## Problem Statement

Airlines collect large volumes of customer feedback data, but identifying the factors that most strongly influence satisfaction can be challenging. Understanding these drivers is essential for improving service quality, increasing customer loyalty, and reducing customer churn.

This project develops a classification model to predict passenger satisfaction and uncover the key service and operational factors that contribute to positive or negative customer experiences.

---

## Dataset

The dataset contains passenger demographics, travel information, and service quality ratings across 22 columns and 129880 rows. 

### Key Features

* Age
* Flight Distance
* Customer Type
* Type of Travel
* Class
* Inflight Wi-Fi Service
* Departure/Arrival Time Convenience
* Ease of Online Booking
* Gate Location
* Food and Drink
* Online Boarding
* Seat Comfort
* Inflight Entertainment
* On-board Service
* Leg Room Service
* Baggage Handling
* Check-in Service
* Cleanliness
* Departure Delay in Minutes
* Arrival Delay in Minutes

### Target Variable

| Satisfaction Status | Count | Percentage |
|--------------------|--------:|-----------:|
| Satisfied | 71,087 | 54.73% |
| Dissatisfied | 58,793 | 45.27% |
| **Total** | **129,880** | **100.00%** |
 
### Missing & Duplicated Values


---

## Project Workflow

### 1. Data Cleaning

  * Arrival Delay in Minutes alone have missing values amounting **393** in count accounting **0.03%.**
  * The missing values were filled with median values because the *min* value was **0** and *max* value is **1584**. Given that most values were concentrated below *700* minutes and there are outliers. These outliers will thereby distort the mean.
  * There are no duplicate values.
  * Handled categorical variables using one-hot encoding
  * Prepared data for machine learning

### 2. Exploratory Data Analysis (EDA)

* Examined customer satisfaction distribution
* Analyzed service ratings and travel characteristics
* Identified relationships between features and satisfaction

### 3. Feature Engineering

* Encoded categorical variables
* Scaled numerical variables using StandardScaler

### 4. Model Development

A Logistic Regression classifier was trained to predict customer satisfaction.

Model optimization included:

* Feature scaling


---

## Model Performance

### Confusion Matrix

| Actual / Predicted | Dissatisfied | Satisfied |
| ------------------ | ------------ | --------- |
| Dissatisfied       | 9435         | 2240      |
| Satisfied          | 2246         | 12055     |

### Classification Metrics

| Metric    | Score  |
| --------- | ------ |
| Precision | 0.8433 |
| Recall    | 0.8429 |
| F1 Score  | 0.8431 |

### Interpretation

The model correctly identifies satisfied passengers with strong precision and recall scores of approximately 84%. The balanced performance indicates that the model effectively minimizes both false positives and false negatives.

---

## Key Drivers of Customer Satisfaction

### Strong Positive Drivers

* Inflight Entertainment
* Seat Comfort
* On-board Service
* Check-in Service
* Ease of Online Booking
* Leg Room Service

### Strong Negative Drivers

* Disloyal Customer
* Personal Travel
* Economy Class
* Arrival Delay
* Food and Drink Quality
* Departure/Arrival Time Convenience

---

## Business Impact of Prediction Errors

While overall model accuracy and F1 score provide a measure of predictive performance, understanding the business implications of prediction errors is equally important.

### False Positives (Predicting Satisfaction When the Customer is Actually Dissatisfied)

A False Positive occurs when the model predicts that a passenger is satisfied, but the passenger is actually dissatisfied.

**Business Costs:**
- Dissatisfied customers may not receive timely intervention or service recovery efforts.
- Increased risk of customer churn and loss of future revenue.
- Negative word-of-mouth and unfavorable online reviews can damage brand reputation.
- Management may incorrectly assume service quality is meeting customer expectations.
- Customer complaints and operational issues may go unnoticed.

**Example:**
A passenger experiences poor service and flight delays but is predicted as satisfied. As a result, the airline does not follow up with compensation, support, or retention offers, increasing the likelihood that the customer switches to a competitor.

### False Negatives (Predicting Dissatisfaction When the Customer is Actually Satisfied)

A False Negative occurs when the model predicts that a passenger is dissatisfied, but the passenger is actually satisfied.

**Business Costs:**
- Resources may be wasted on unnecessary customer retention efforts.
- The airline may provide discounts, loyalty rewards, or follow-up communications to customers who do not require intervention.
- Customer service teams may spend time addressing non-existent issues.
- Operational costs may increase due to unnecessary outreach campaigns.

**Example:**
A satisfied passenger is incorrectly flagged as dissatisfied and receives compensation or special offers that were not needed, resulting in additional costs for the airline.

### Which Error is More Costly?

In most airline customer satisfaction use cases, **False Positives are generally more costly than False Negatives**.

The cost of losing an unhappy customer, damaging customer loyalty, and generating negative reviews often exceeds the cost of conducting unnecessary follow-up actions for a satisfied customer. Consequently, airlines may prefer a model that identifies dissatisfied customers more aggressively, even if this slightly increases the number of False Negatives.

### Business Recommendation

If the model is deployed to support customer retention initiatives, management should consider prioritizing the detection of dissatisfied passengers by optimizing the model for higher recall on the dissatisfied class. This approach can help ensure that at-risk customers are identified early and receive appropriate service recovery actions before they choose a competing airline.

---

## Business Recommendations

* Invest in inflight entertainment systems and content quality.
* Improve seat comfort and cabin service standards.
* Enhance digital experiences such as online booking and boarding.
* Reduce operational delays to improve customer satisfaction.
* Strengthen loyalty programs to improve customer retention.
* Focus on improving the experience of economy-class passengers.

---

## Tools and Technologies

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn
* Jupyter Notebook

---

## Future Improvements

* Experiment with ensemble models such as Random Forest, XGBoost, and LightGBM.
* Deploy the model using Streamlit or Flask.
* Implement real-time satisfaction monitoring dashboards.
* Incorporate customer review text using Natural Language Processing (NLP).
* Establish automated retraining and model monitoring pipelines.

---

## Author

Taiwo Olaniyi Toheeb

Data Analyst | Data Scientist | Aspiring Transportation Data Scientist
