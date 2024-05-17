# BIG-DATA-PROJECT

CIS 4130 PROJECT

Gelbert Ramos

Spring 2024

Milestone 1 -Proposal 
(a description of the data source and project)

I propose a predictive modeling project aimed at forecasting the closing prices of various stocks using historical financial data. The dataset will encompass essential attributes such as open price, high price, low price, closing price, volume, and an array of technical indicators like Bollinger Bands, Exponential Moving Averages (EMA), Moving Averages (MA), among others.
My objective is to harness the power of machine learning to predict future closing prices, thereby assisting traders and investors in making well-informed decisions. I will evaluate the performance of our predictive models using key metrics such as Root Mean Squared Error (RMSE) and R-Squared. RMSE will provide insights into the accuracy of our predictions by quantifying the difference between predicted and actual values. Meanwhile, R-Squared will gauge the model's ability to explain the variance in the target variable (next_day_close) using the independent variables.
By employing advanced statistical techniques and leveraging comprehensive financial data, this project aims to enhance decision-making processes in the dynamic world of stock trading and investment.

Huge US 514 Stocks + 1298 columns Market Data 25Gb (kaggle.com)

Milestone 2 - Data Acquisition 
(a description of the steps taken to acquire the data)

In the initial stages of the project, I navigated through the process of acquiring a dataset from Kaggle, ensuring that my system memory could accommodate the size of the intended data file. Following this, I initiated the download process through the console, taking necessary precautions to ensure a smooth retrieval.
Setting up the environment, I created an instance and uploaded the API token file required for authentication. With a Python environment configured, I proceeded to download the designated Kaggle dataset, which comprised a substantial 30 GB of open data. This dataset encapsulated a comprehensive collection of columns sourced from the US Stock Exchange Market Data, representing a diverse array of 514 US stocks.
Understanding the magnitude of data acquisition involved, I opted to execute the code in a unified manner, generating a singular output for streamlined management. Utilizing Python 3 within a virtual Jupyter notebook environment, I initiated the execution of these codes, marking a significant milestone in the project's progression

Milestone 3 - Exploratory Data Analysis and Data Cleaning
(A description of the findings from EDA and an outline of the steps taken to clean the data)

I conducted an  analysis of the dataset, spanning from November 18, 1999, to December 28, 2023. Calculating key statistical measures, I found the mean opening price to be approximately 55.44, with a standard deviation of around 36.76. Interestingly, the mean closing price mirrored the opening price, indicating a consistent and stable pricing behavior over the dataset's timeframe.
Examining the extremes, the highest recorded opening and closing prices peaked at around 179 and 180, respectively, while the lowest recorded values stood at 11, potentially indicating initial values.
Delving into inter-variable relationships, all correlation coefficients surpassed 0.7, signifying a strong linear association among the dataset's variables. This observation suggests a tendency for prices to move in tandem; when one price increases, others also tend to rise, and vice versa.
To ensure data integrity, I employed the .isnull() function to identify any missing entries within the dataset. Fortunately, no anomalies or missing values were detected, affirming the dataset's completeness.
Additionally, I utilized data type analysis and filter functions to identify and remove any irregular entries, ensuring the dataset's consistency and reliability for subsequent analyses.


Milestone 4 - Feature Engineering and Modeling
( Description of the feature pipeline and its model)

I employed feature engineering and modeling techniques to forecast the next day closing prices for stocks starting with letter A. In this case I utilized Linear Regression with Ridge Regularization to build the predictive model, incorporating regularization to prevent overfitting.

Also, I transformed raw data into a format suitable for training machine learning models. In this project, both numeric and categorical features are handled. Numeric features such as open, high, low, close prices, and various technical indicators are assembled into a single feature vector. Categorical features, like stock symbols, are indexed and then one-hot encoded to be included in the feature vector

R-squared value is approximately 0.9994. This indicates that approximately 99.94% of the variance in the target variable is explained by the independent variables in the model. A high R-squared value close to 1 suggests that the model fits the data very well, indicating a strong relationship between the independent and dependent variables


Milestone 5 - Visualization

Linear Regression

This scatter plot with a linear regression line shows the relationship between the actual and predicted stock closing values for the next day. The X-axis represents the actual closing values (next_day_close), and the Y-axis represents the predicted values (prediction). Each point on the plot is a pair of actual and predicted values.
The points are tightly clustered around the diagonal line, indicating that the predictions are very close to the actual values. The regression line closely follows this diagonal, suggesting a strong correlation and high accuracy in the model's predictions. If the model were perfect, all points would lie exactly on the 45-degree diagonal line.






Residuals Results 

This code creates a residual plot, which helps evaluate a regression model's performance by looking at the residuals (the differences between actual and predicted values).
First, it converts the Spark DataFrame test_results into a Pandas DataFrame. Then, it calculates the residuals by subtracting the predicted values (prediction) from the actual values (next_day_close), adding a new column called residuals to the DataFrame.
This plot shows some patterns and increased dispersion in residuals as predicted values rise. This suggests the model's performance varies for different ranges of predicted values, and the spread of residuals increases with prediction value, indicating possible heteroscedasticity (where residual variance isn't constant).
Also, after analyzing the image I found out there is an outlier off from the residuals right in the beginning and I found there are empty values in the data frame in X axis value.






SQL Query Filter

In this table showing the closing prices of Adobe's stock (ADBE) and the closing prices for the next day for a range of dates in January 2023. The table includes the stock symbol, the date, the closing price for that date, and the closing price for the next day




Distribution of Residuals 

I used Seaborn's histplot function to create a histogram of the residuals (differences between actual and predicted values) from the DataFrame
The tall spike at zero visually indicates that most predictions are very close to the actual values. The spread of residuals shows how often large errors occur, which can highlight potential issues in the model.
Overall the indication of large residuals suggests that there is a significant is very rare to find errors, indicating is a good model


Feature Importances ( Indicators)  from the Model

In this bar chart showing the importance of different indicators used in this model shows how each feature of the columns contributes to the model predictions.

In this following visualization I found out that the close price and the macd_20_40_10_macd were by far the most relevant to the model.

MACD ( Moving Average Convergence Divergence)  indicator determines the momentum and strength helping to make to make decisions on when to enter or exit trades.

20: The period of the short-term Exponential Moving Average (EMA)
40: The period of the long-term Exponential Moving Average (EMA)
10: The period of the signal line, which is an EMA of the MACD line














