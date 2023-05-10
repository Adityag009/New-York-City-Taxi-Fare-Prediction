# New-York-City-Taxi-Fare-Prediction

My project was to predict New York City taxi fares, which was a regression problem. The dataset was very large, with a size of 5.3 GB, which made it difficult to import into Python. I attempted to use Spark to import the dataset, but was unsuccessful. Then, I used the nrows feature of pandas and imported 2,000,000 records for the training dataset.

The first step of data cleaning involved dealing with the outliers in each feature of the dataset. To remove outliers, I defined the acceptable range of values as three standard deviations away from the median, and stored the lower and upper bounds in the variables low and high. I then filtered out any values in the DataFrame that fell outside the acceptable range by using the >= and <= operators to create a boolean mask that selected only the rows with x values between low and high. After that, I used the pickup and dropoff coordinates to calculate the distance traveled by the taxi in kilometers.

Next, I performed exploratory data analysis (EDA) on the dataset, which involved plotting different plots to gain various insights and information.

To train the model, I used a pipeline that trained five models, namely LinearRegression, DecisionTreeRegressor, RandomForestRegressor, AdaBoostRegressor, and GradientBoostingRegressor. I got the best score with the GradientBoostingRegressor, with a training score of 81.02 and a testing score of 80.78. I then used grid search CV for hyperparameter tuning for Ridge and Lasso, but the scores were similar to LinearRegression. Next, I tried hyperparameter tuning for the decision tree, which was a time-consuming task, taking 8 to 9 hours. After several attempts, I reduced the number of parameters and did hyperparameter tuning, but the scores were not good. Finally, I tried the XGBoost algorithm, which gave me the best scores, with a training score of 81.85 and a testing score of 81.20.

I used this model to predict the fare prices for the test dataset. Overall, I learned a lot from this project, and it helped me improve my skills in data cleaning, EDA, and model training.
