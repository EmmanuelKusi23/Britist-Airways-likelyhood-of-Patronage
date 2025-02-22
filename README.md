# Britist-Airways-likelyhood-of-Patronage
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

---

## Modeling
### Algorithms
| Model                  | AUC-ROC  | Precision | Recall |
|------------------------|----------|-----------|--------|
| Logistic Regression    | 0.72     | 0.31      | 0.65   |
| XGBoost                | 0.81     | 0.45      | 0.68   |

### Feature Importance (XGBoost)
![Feature Importance](images/feature_importance.png)

---

## How to Run
1. **Clone Repository**:
   ```bash
   git clone https://github.com/yourusername/british-airways-booking-prediction.git
   cd british-airways-booking-prediction
