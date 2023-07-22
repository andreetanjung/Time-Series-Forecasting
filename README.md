# Time-Series-Forecasting
### Project Overview
In this notebook, we will attempt to predict the quantity of products sold by a company from January 2022 to March 2023. We will compare several models, including basic time series models like ARIMA, SARIMA, and Exponential Smoothing, as well as an ANN model and the Prophet algorithm. The objective of this notebook is to determine the most accurate model and use it to predict the quantity of items sold for several weeks in advance
### Data
The data was obtained through the academic competition which has been uploaded as `sample_dataset_timeseries_noarea.csv`

Data field description:
| Column | Description |
| --- | --- |
|week_number | contained information about week of specific product sold, (2021-52 to 2023-14).|
|week_start_date | contained information about week start date of specific product sold. |
|week_end_date | contained information about week end date of specific product sold. |
|product_item | contained information about product item/product code. |
|quantity | contained information about quantity of product in respective week. |
### Methodology
- Data preprocessing: make sure the data has no duplicate and missing value
- Exploratory data: understand more about the data
- Decomposition, stationary and autocorrelation analysis: to find out about the trend, seasonality, and find the right ACF and PACF for the model tuning
- Modeling: comparing ARIMA, SARIMA, Holts-Winter, LSTM, and Prophet model to find the best model
### Result and Evaluation
From 5 models that we have tried so far:
1. ARIMA MAPE       : 2.07%

2. SARIMA MAPE      : 2.76%

3. Holts-Winter MAPE: 2.77%

4. LSTM MAPE        : 5.98%

5. Prophet          : 32.8%

ARIMA model shows the best minimum error in forecast, for that reason we will use ARIMA model to predict the quantity sold for several weeks ahead from this dataset. With the low MAPE score, ARIMA model has proven that this model can be used on non-linear trend and without seasonal pattern but need to be remember that this model may not suitable for highly volatile or unpredictable time series data like what happened on the month of May.
- The dataset contains information on the number of items sold by a company from the beginning of 2022 until April 2023, spanning 67 weeks.
- The dataset contains a total of 2037 unique items, with the most sold item being identified by the product ID '2949ca4cfbf13969bccfbb9817f2526a'. The number of items sold of this product is so high that the second most item sold is only half of it.
- Interestingly, the highest and lowest points of items sold occurred during the same month, which is in May 2022, and it is assumed to be due to a long holiday that occurred during that time.
- From the beginning of 2022 until August, there was an upward trend in items sold followed by a downward trend thereafter.
- A recurring pattern observed in the data is the consistent increase in items sold followed by a decrease, which happens every month.
- Out of the several models tested on the dataset, the best performing model is ARIMA, with an average error of 2% in the forecast. Therefore, the model is deemed suitable for deployment as long as the data is assumed stationary.
### Future References
Possible improvements to the model include:
    - Utilizing the BIC (Bayesian information criterion) technique to determine the parameters that could potentially lead to a better model.
    - Trying ensemble learning techniques to combine different models and potentially achieve better accuracy.
    -   that include more than one parameter to get stronger exogenous variables.
### Project Insight on Real Life Business
From the visualization indicates that there will be an increase in item sales over the next two weeks and in the month of July. As a data scientist, we can recommend the following actions based on this insight:
- For the warehouse, they can prepare their inventory items and manage them accordingly to ensure that there are enough stocks available to meet the expected demand.
- For the company, we can suggest implementing a promotional strategy such as offering bundle discounts during the anticipated high sales month. This would help to clear out old inventory while keeping the number of items sold high and maintaining the same profit margin.
- For the seller partners, we can advise them to focus their marketing efforts on specific items or categories during the predicted high sales month
### Directory Structure and Brief Description of Files
`talent_fair_Andrian_Tanjung.ipynb` is a Jupyter notebook that contains the complete project code, including data pre-processing, feature engineering with model, and evaluation.

