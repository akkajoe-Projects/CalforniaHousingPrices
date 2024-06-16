# CalforniaHousingPrices
Prediction of California Housing Prices from 1990 census data

The original dataset appeared in R. Kelley Pace and Ronald Barry, “Sparse Spatial Autoregressions,” Statistics
& Probability Letters

This project aims to predict housing prices in California using various machine learning models. The dataset contains attributes such as the location (longitude and latitude), median age of the houses, number of rooms, population, median income, and proximity to the ocean. The project involves multiple steps, including data visualization, data cleaning, feature engineering, and model training. 

# Data Exploration and Visualization
Initially, we explore the dataset to understand its structure and key statistics. Various plots, such as scatter plots and correlation matrices, are used to visualize relationships between different attributes. For instance, we observe a strong correlation between median income and median house value, which helps in identifying significant features for the model.

# Data Preprocessing
The data preprocessing phase involves handling missing values, encoding categorical attributes, and scaling numerical features. Missing values in the dataset are handled using the SimpleImputer with the median strategy. Categorical attributes, such as 'ocean_proximity,' are encoded using OrdinalEncoder and OneHotEncoder. Feature scaling is performed using StandardScaler to ensure that all features contribute equally to the model.

# Feature Engineering
New features are created to enhance the model's performance. For example, we derive 'rooms_per_household,' 'bedrooms_per_room,' and 'population_per_household' from the existing attributes. These additional features help capture more information about the housing data, leading to potentially better predictions.

# Model Training and Evaluation
Various models are trained and evaluated, including Linear Regression, Decision Tree Regressor, and Random Forest Regressor. The performance of these models is measured using Root Mean Squared Error (RMSE). Initially, the Linear Regression model underfits the data, while the Decision Tree Regressor overfits it. The Random Forest Regressor provides a better balance with a significantly lower RMSE. Cross-validation is used to ensure the models' robustness and prevent overfitting.

# Hyperparameter Tuning
Hyperparameter tuning is performed using GridSearchCV to find the best combination of parameters for the Random Forest Regressor. This process involves testing different values for hyperparameters like the number of estimators and the maximum number of features. The best model is selected based on its performance on the validation set.

# Final Model Evaluation
The final model, selected through hyperparameter tuning, is evaluated on the test set. The RMSE on the test set is computed to assess the model's performance. Additionally, a 95% confidence interval is calculated to provide an estimate of the prediction precision.
