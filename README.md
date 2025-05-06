Superstore Sales and Profit Prediction
Project Overview
This project develops machine learning models to predict sales revenue and profit for retail transactions using the Superstore dataset. The models leverage time-based features and other characteristics to capture seasonal patterns and relationships between variables, resulting in highly accurate predictions.
Author
Nguyễn Phúc Nguyên (20227138)
Hanoi University of Science and Technology
Dataset
The Superstore dataset contains 9,994 records with 21 columns, including:

Target variables: Sales, Profit
Features: Quantity, Discount, Category, Sub-Category, Region, State
Time data: Order Date, Ship Date
Key Features
The project implements several features to enhance model performance:
Time-based Features

Order_Year, Order_Month, Order_DayOfWeek, Order_Quarter
Season (Winter, Spring, Summer, Fall)
Shipping_Delay (days between order and shipping)

Interaction Features

Sales_per_Quantity = Sales / Quantity
Discounted_Sales = Sales × (1 - Discount)
Estimated_Cost = Sales - Profit
Quantity_Discount = Quantity × Discount

Methodology
Data Preprocessing

Outlier removal (5% of extreme values)
Feature engineering (time-based and interaction features)
Categorical encoding (Label Encoding)
Numerical standardization (StandardScaler)
Missing value handling

Model Building

Algorithm: LightGBM (gradient boosting framework)
Training split: 80% training, 20% testing
Key parameters:

num_leaves=31
learning_rate=0.05
feature_fraction=0.9
bagging_fraction=0.8
objective='regression'
metric='l2'
num_boost_round=1000



Results
Sales Prediction

Train: MAE = 0.600, MSE = 0.790, R² = 0.99996
Test: MAE = 1.439, MSE = 18.744, R² = 0.99913

Profit Prediction

Train: MAE = 2.140, MSE = 13.859, R² = 0.9778
Test: MAE = 3.154, MSE = 49.118, R² = 0.9121

Insights

Sales and profit show strong seasonal patterns, with peaks in November and December
Sales have a positive correlation with Profit (0.48)
Quantity correlates positively with Sales (0.20)
Discount correlates negatively with Profit (-0.22)
Overall sales increase year over year from 2014 to 2017

Applications

Sales and profit forecasting
Discount optimization
Seasonal planning
Inventory management

Future Improvements

Integration with time series models (Prophet)
Automated hyperparameter tuning (Grid Search, Random Search)
Additional cost data collection
Model complexity reduction to decrease overfitting
