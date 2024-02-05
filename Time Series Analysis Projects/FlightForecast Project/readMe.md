## FlightForecast: Navigating Time Trends in Airline Passengers:

**Dataset Overview:**
Airline Passengers dataset from Kaggle. The dataset has 144 rows and 2 columns. The first column 'Month' contains the month and year information and the second column 'Passengers' contains the number of Passengers who travelled in that Airline for that month. We have 12 Years of data starting from 1 Jan 1949 to 31 Dec 1960.

**Objective:**
To analyze this Time Series data and build a model that could forecast for one year, the number of Passengers who would travel in that Airline every month.

**Approach:**
1. Checked for missing values.
2. Split the data into train(first 11 years data) and test(last 1 year data).
3. Analyzed the trend; seasonality; and stationarity of the time series using the ADF(Augmented-Dickey Fuller) test.
4. The time series is non-stationary and exhibits trend and seasonality so I decided to use the SARIMA(Seasonal Auto-Regressive Integrated Moving Average) model to capture the trend and seasonality.
5. I have used different approaches to evaluate the model parameters(p, d, q, P, D, Q).
    5.1 To use the ACF and PACF of the non-seasonally differenced series.
    5.2 To use the ACF and PACF of the seasonally differenced series.
    5.3 To use the grid-search method.
6. Used the metrics **AIC(Akaike Information Criterion)** to select the best model to forecast for the next year.
7. Used the best model and did the forecast for the next year. 
8. Evaluated the model performance using the metric MAD(mean absolute deviation)
and plotted the predictions against the actual values.
9. Reported the model performance.