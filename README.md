# Financial_Time_Series
The objective of the project is to create an auto-regression model in order to predict the price of BTC in USDT from 2017-2022


**Dataset**: a time-series dataset, sourced from Kaggle, displaying the price of BTC in USDT from 2017 to 2022.

Questions to answer: 
1. Does the size of the train dataset affect the mean absolute error (MAE)?
2. Will the average price of BTC decrease or increase in the next 3 months?
3. What do the seasonal trend in the price fluctuation look like?


**Summary** of Data Engineering training project:

In the market of cryptocurrency the Bitcoins are the first currency which has gained significant important.
To predict the market price and stability of Bitcoin in the crypto-market, a machine learning based time series analysis has been applies.
Time-series analysis can predict the rise and falls in the price of Bitcoin. For this purpose, we have used ARIMA for time series analysis as a machine learning technique. The parameters on the basis of which we have evaluated these models are Root Mean Squared Error (RMSE), Mean Aboslute Error (MAE), and R2. 

We conduct experiments on these three techniques but after conducting time series analysis, ARIMA was considered as the best model for forcasting Bitcoin price in the crypto market with RMSE score of 322.4 and MAE score of 227.3.
Additionally, this research can be helpful for investors of crypto-market.

**Methodology**:

_Understanding the data_:
- The data was extracted from Kaggle.
- The data spans over the period 2017 - 2022.
- There are 2 kinds of data: Prices (btc_crop) and a Complete Dataset (bitcoin)

_Features _(full dataset):
- Open Time/Close Time: the time when the market opens and closes.
- Open/close: opening and closing price on the given day (USD).
- High/Low: highest and lowest price on the given day (USD).
- Day of week: 0 (Sunday), 1(Monday), 2(Tuesday), 3(Wednesday), 4(Thursday), 5(Friday), 6(Saturday)
- Volume: the sum total of actual trades taking place (quantity of asset bought or sold) displayed in USD.
- Quote Asset Volume: the volume in the second part of a pair (i.e. BTC/USDT - the quote would be volume in USDT)
- Taker Buy (TB) base volume: when buyers (takers) buy at the bid price set by sellers (makers), the amount of assets traded between the two contributes to the TB base volume.
- Take Buy (TB) quote volume: is expressed as the amount of coins that were paid by the buyer in BTC.

_Cleaning and pre-processing_:
1. Cleaned the data - converted the date to the datetime format, converted the rest of the columns into its correct data type, and checked for null values.
We didn't find any null values or any errors in the data type. The whole dataset has 162583 entries and 23 columns
2. Feature engineering:
2.1. Labeled the 'Open Time' according to the US holiday calendar ('Weekend', 'Workday', 'Holiday').
2.2. Created a function to label time intervals in 'Open Time' to assign the description of the day time ('Morning', 'Afternoon', 'Evening', 'Late Night').

_Exploratory Data Analysis (EDA)_:
- Filtered the data to only show the columns related to time and price (bc_crop)
- Calculated the average price per 15 min interval using the 'high' and 'low' columns
- Grouped the filtered data by date and calculated the mean of the average price per 15 min interval per day
- Created a boxplot with the training data, which has a size of a month, and the full dataset, size of 5 years, to discover seasonality

**Findings**:
- There was no seasonality or trends in both the training data and the full dataset.
