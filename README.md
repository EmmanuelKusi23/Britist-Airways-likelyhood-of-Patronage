
# British Airways Customer Booking Prediction ✈️

![GitHub](https://img.shields.io/github/license/yourusername/british-airways-booking-prediction)
![Python](https://img.shields.io/badge/python-3.8%20%7C%203.9%20%7C%203.10-blue)

Predicting customer booking completion likelihood using historical flight booking data. This project helps optimize marketing strategies by identifying high-intent customers.

## Table of Contents
- [Project Overview](#project-overview)
- [Dataset Description](#dataset-description)
- [Key Insights](#key-insights)
- [Preprocessing Steps](#preprocessing-steps)
- [Modeling](#modeling)
- [Results](#results)
- [How to Run](#how-to-run)
- [Future Work](#future-work)
- [License](#license)

---

## Project Overview
**Objective**: Predict whether a customer will complete a flight booking (`booking_complete`).  
**Business Impact**: Identify conversion patterns to:
- Target high-potential customers with personalized offers.
- Reduce operational costs by focusing resources effectively.
- Improve revenue through data-driven marketing.

---

## Dataset Description
**Source**: Hypothetical British Airways booking data (simulated).  
**Size**: 50,000 records, 14 features.  
**Features**:

| Feature                 | Description                                  | Type       |
|-------------------------|----------------------------------------------|------------|
| `num_passengers`        | Number of passengers                         | Numerical  |
| `sales_channel`         | Booking platform (Internet/Mobile)           | Categorical|
| `purchase_lead`         | Days between booking and flight              | Numerical  |
| `flight_day`            | Departure day (1=Mon to 7=Sun)               | Numerical  |
| `booking_origin`        | Customer's country (104 unique values)       | Categorical|
| `wants_extra_baggage`   | 1 if extra baggage requested                 | Binary     |
| `booking_complete`      | **Target**: 1 if booking succeeded           | Binary     |

---

## Key Insights
### 1. Class Imbalance
- Only **14.96%** of bookings were completed.  
  ![Class Distribution](images/class_distribution.png)

### 2. Geographic Trends
- Top booking countries: Australia (35.7%), Malaysia (14.3%), South Korea (9.1%).

### 3. Flight Behavior
- **Peak Departure Hours**: 9 AM - 3 PM.  
- **Popular Days**: Weekends (Saturday/Sunday).

### 4. Purchase Lead Time
- Average: **85 days** (max = 867 days).  
  ![Lead Time Distribution](images/lead_time_dist.png)

---

## Preprocessing Steps
1. **Categorical Encoding**:
   - One-hot encoded `sales_channel` and `trip_type`.
   - Target-encoded `booking_origin`.

2. **Feature Engineering**:
   - Binned `purchase_lead` into categories (e.g., "<7 days", "7-30 days").
   - Derived `is_weekend` from `flight_day`.

3. **Handling Imbalance**:
   - Applied **SMOTE** to balance classes.


## Project Overview  
This project applies data science techniques to analyze customer behavior and determine the factors influencing the likelihood of patronage for British Airways. By leveraging machine learning and statistical analysis, the study identifies key variables affecting customer retention and provides actionable insights for improving airline services and customer satisfaction.  

The analysis covers data preprocessing, exploratory data analysis (EDA), feature engineering, and predictive modeling using machine learning algorithms. The success of this project lies in uncovering critical trends and making data-driven recommendations that could enhance British Airways' market position.  

---

## Objectives of the Analysis  
✅ **Understand Customer Behavior:** Identify patterns in customer preferences, satisfaction levels, and service factors influencing airline choice.  
✅ **Determine Key Drivers of Patronage:** Use feature importance techniques to pinpoint the most influential factors affecting customer decisions.  
✅ **Build Predictive Models:** Develop machine learning models to forecast the likelihood of customer patronage based on historical data.  
✅ **Provide Actionable Insights:** Offer recommendations to optimize British Airways' customer engagement strategies.  

---

## Methodology and Data Science Workflow  

### **1. Data Preprocessing**  
- **Handling Missing Values:** Missing data was identified and addressed using imputation techniques to ensure analysis accuracy.  
- **Encoding Categorical Variables:** Categorical features such as customer demographics and service ratings were transformed using One-Hot Encoding.  
- **Feature Scaling:** Numerical variables were normalized using StandardScaler to improve model performance and convergence.  

### **2. Exploratory Data Analysis (EDA)**  
EDA was performed to identify patterns, correlations, and key insights:  
- 📊 **Visualization Techniques:** Histograms, box plots, and bar charts were used to analyze distributions and detect outliers.  
- 🔍 **Correlation Analysis:** A heatmap was generated to examine relationships between variables, helping in feature selection.  
- 📌 **Customer Segmentation:** Customers were grouped based on behavior patterns, allowing for targeted business strategies.  

### **3. Machine Learning Modeling**  
Multiple machine learning techniques were implemented to predict customer patronage:  
- **Random Forest Classifier:** Used for feature importance analysis and predictive modeling.  
- **Train-Test Split:** The dataset was split (80% training, 20% testing) to evaluate model performance.  
- **Hyperparameter Tuning:** Grid search and cross-validation techniques were applied to optimize model accuracy.  

### **4. Feature Importance Analysis**  
- 🔹 **Random Forest Feature Importances:** This technique identified the top predictors of customer patronage.  
- 🔹 **Permutation Importance:** A secondary check was performed to validate which variables had the most influence on predictions.  

---

## Key Findings and Success Achieved  

### **1. Identified Critical Factors Affecting Patronage**  
📌 **Customer Service Ratings:** High customer service ratings significantly increased the likelihood of repeat patronage.  
📌 **Flight Punctuality:** Customers preferred airlines with a strong track record of on-time departures and arrivals.  
📌 **Loyalty Programs:** Membership in frequent flyer programs increased customer retention.  
📌 **Price Sensitivity:** Competitive pricing played a role in airline selection but was less significant than service quality.  

### **2. Improved Predictive Accuracy**  
- 🎯 **Model Performance:** The Random Forest Classifier achieved an accuracy of **85%**, effectively predicting customer patronage based on available data.  
- 🛠 **Feature Engineering Success:** Data transformation and feature selection improved model interpretability and performance.  

### **3. Business Insights for British Airways**  
✅ **Service Enhancement:** Improving customer service and flight punctuality can directly increase market share.  
✅ **Targeted Marketing Strategies:** Personalized offers and loyalty programs should be emphasized to attract and retain high-value customers.  
✅ **Competitive Pricing Adjustments:** While pricing is a factor, it should be balanced with service quality to maximize long-term profitability.  

---

## Conclusion  
This project successfully demonstrates how data science can be used to gain meaningful insights into customer behavior in the airline industry. The predictive model not only forecasts patronage likelihood but also provides actionable recommendations for British Airways to enhance customer experience and loyalty.  

With further refinement, the model can be expanded to incorporate real-time customer feedback, economic conditions, and competitor analysis to improve accuracy and adaptability.  

---

## Next Steps & Future Enhancements  
🚀 **Integrate Sentiment Analysis:** Include customer reviews to gain deeper insights into passenger experiences.  
🚀 **Expand Dataset Scope:** Incorporate competitor performance metrics for a more comprehensive analysis.  
🚀 **Develop a Real-Time Dashboard:** Enable live monitoring of key customer satisfaction indicators.  

---

## Repository Structure  
📂 **data/** – Contains the dataset used for analysis.  
📂 **notebooks/** – Jupyter notebooks with full data preprocessing, EDA, and model training steps.  
📂 **models/** – Saved machine learning models for reuse.  
📂 **reports/** – Summary insights and visualizations from the analysis.  

---

## How to Run the Analysis Locally  

1. **Clone the repository:**  
   ```bash
   git clone https://github.com/EmmanuelKusi23/Britist-Airways-likelyhood-of-Patronage.git
   cd Britist-Airways-likelyhood-of-Patronage

## How to Run
1. **Clone Repository**:
   ```bash
   git clone https://github.com/yourusername/british-airways-booking-prediction.git
   cd british-airways-booking-prediction
