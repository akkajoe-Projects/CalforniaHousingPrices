# California Housing Prices
Prediction of California Housing Prices using 1990 census data

## Overview
This project aims to predict housing prices in California using various machine learning models. The dataset, originally from R. Kelley Pace and Ronald Barry's “Sparse Spatial Autoregressions,” contains attributes such as location (longitude and latitude), median age of houses, number of rooms, population, median income, and proximity to the ocean. The project involves several steps, including data visualization, data cleaning, feature engineering, and model training.

## Data Exploration and Visualization
The initial phase involves exploring the dataset to understand its structure and key statistics. Various plots, such as scatter plots and correlation matrices, are used to visualize relationships between different attributes. A strong correlation between median income and median house value is observed, which helps in identifying significant features for the model.

## Data Preprocessing
Data preprocessing includes handling missing values, encoding categorical attributes, and scaling numerical features. Missing values are handled using the SimpleImputer with the median strategy. Categorical attributes, such as 'ocean_proximity,' are encoded using OrdinalEncoder and OneHotEncoder. Feature scaling is performed using StandardScaler to ensure all features contribute equally to the model.

## Feature Engineering
New features are created to enhance the model's performance. For example, 'rooms_per_household,' 'bedrooms_per_room,' and 'population_per_household' are derived from existing attributes. These additional features help capture more information about the housing data, leading to potentially better predictions.

## Model Training and Evaluation
Various models, including Linear Regression, Decision Tree Regressor, and Random Forest Regressor, are trained and evaluated. The performance of these models is measured using Root Mean Squared Error (RMSE). Initially, the Linear Regression model underfits the data, while the Decision Tree Regressor overfits it. The Random Forest Regressor provides a better balance with a significantly lower RMSE. Cross-validation is used to ensure the models' robustness and prevent overfitting.

## Hyperparameter Tuning
Hyperparameter tuning is performed using GridSearchCV to find the best combination of parameters for the Random Forest Regressor. This process involves testing different values for hyperparameters like the number of estimators and the maximum number of features. The best model is selected based on its performance on the validation set.

## Final Model Evaluation
The final model, selected through hyperparameter tuning, is evaluated on the test set. The RMSE on the test set is computed to assess the model's performance. Additionally, a 95% confidence interval is calculated to provide an estimate of the prediction precision.

## Results
The dataset contains 20,640 entries with 10 attributes. Below are some key statistics:

- **Mean Longitude:** -119.57
- **Mean Latitude:** 35.63
- **Mean Housing Median Age:** 28.64
- **Mean Total Rooms:** 2635.76
- **Mean Total Bedrooms:** 537.87
- **Mean Population:** 1425.48
- **Mean Households:** 499.54
- **Mean Median Income:** 3.87
- **Mean Median House Value:** 206,855.82

The distribution of the 'ocean_proximity' attribute is as follows:
- **<1H OCEAN:** 9,136
- **INLAND:** 6,551
- **NEAR OCEAN:** 2,658
- **NEAR BAY:** 2,290
- **ISLAND:** 5

The Random Forest Regressor, after hyperparameter tuning, achieved the best performance with the following results:
- **Training RMSE:** 18,500
- **Validation RMSE:** 50,000
- **Test RMSE:** 48,000
- **95% Confidence Interval for Test RMSE:** [46,000, 50,000]
