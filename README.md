🚗 In-Vehicle Coupon Recommendation Prediction
This repository contains the code and analysis for predicting coupon acceptance in an in-vehicle context. The goal is to build a model that can accurately recommend coupons to drivers based on various factors, thereby improving the effectiveness of coupon campaigns.

Project Overview
In today's competitive market, businesses are constantly looking for innovative ways to attract and retain customers. In-vehicle coupon recommendations offer a unique opportunity to engage drivers with relevant offers based on their current context, such as destination, weather, time of day, and personal preferences.

This project aims to develop a predictive model that determines whether a driver will accept a given coupon. By leveraging machine learning techniques, we analyze a comprehensive dataset containing driver demographics, driving habits, coupon types, and environmental factors to predict coupon acceptance. The insights gained from this project can help businesses optimize their coupon distribution strategies and enhance customer satisfaction.

Dataset
The dataset used in this project is in-vehicle-coupon-recommendation.csv. It contains 12,684 entries and 26 columns, encompassing various features related to the driver, the coupon, and the driving context.

Key Features:

destination: Where the driver is heading (e.g., No Urgent Place, Home, Work).

passanger: Who is in the car with the driver (e.g., Alone, Friend(s), Kid(s), Partner).

weather: Current weather conditions (e.g., Sunny, Rainy, Snowy).

temperature: Temperature in Fahrenheit.

time: Time of day (e.g., 10AM, 2PM, 6PM, 10PM, 7AM).

coupon: Type of coupon offered (e.g., Restaurant(<20), Coffee House, Carry out & Take away, Bar, Restaurant(20-50)).

expiration: Coupon expiration time (e.g., 1d, 2h).

gender: Driver's gender.

age: Driver's age group.

maritalStatus: Driver's marital status.

has_children: Whether the driver has children (0 = No, 1 = Yes).

education: Driver's education level.

occupation: Driver's occupation.

income: Driver's income range.

car: Car type (mostly missing values, dropped during cleaning).

Bar, CoffeeHouse, CarryAway, RestaurantLessThan20, Restaurant20To50: Frequency of visiting these establishments.

toCoupon_GEQ5min, toCoupon_GEQ15min, toCoupon_GEQ25min: Time to reach the coupon's location (binary: 1 if greater than or equal to, 0 otherwise).

direction_same, direction_opp: Direction relative to the coupon.

Y: Target variable; coupon acceptance (1 = Accepted, 0 = Rejected).

Methodology
The project follows a standard machine learning pipeline:

Data Loading and Overview: The dataset is loaded using pandas, and initial checks are performed to understand its shape, data types, and basic statistics.

Data Cleaning:

Duplicate rows are removed to ensure data integrity.

The 'car' column, which has a high percentage of missing values, is dropped.

Missing values in frequency-of-visit columns (Bar, CoffeeHouse, CarryAway, RestaurantLessThan20, Restaurant20To50) are imputed with 'never'.

Exploratory Data Analysis (EDA):

The distribution of the target variable (Y - coupon acceptance) is visualized to understand the class balance.

Key features such as age and gender are analyzed in relation to coupon acceptance using count plots to identify potential trends and insights.

Model Training and Evaluation:

The dataset is prepared for modeling, which typically involves encoding categorical variables and splitting the data into training and testing sets.

Several machine learning models are trained, including Logistic Regression, Decision Tree, and Random Forest.

Models are evaluated based on Accuracy, F1 Score, and ROC AUC to determine their predictive performance.

Model Evaluation Results
After testing different models, the Random Forest model demonstrated the most accurate results for predicting coupon acceptance.

Model

Accuracy

F1 Score

ROC AUC

Logistic Regression

66.43%

74.25%

62.81%

Decision Tree

69.57%

74.64%

68.42%

Random Forest (Tuned)

75.98%

80.72%

74.10%

Random Forest (Base)

76.04%

80.61%

74.39%

The base Random Forest model achieved an accuracy of 76.04%, an F1 score of 80.61%, and an ROC AUC score of 74.39%. Even after hyperparameter tuning, the basic version of Random Forest performed slightly better, indicating its robustness and suitability for this prediction task.
