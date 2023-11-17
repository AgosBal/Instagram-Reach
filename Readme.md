# Google Trends Analysis <img src="https://github.com/AgosBal/Instagram-Reach/blob/40768e90852e0ed2c44aeb399a07167fcfb74aa5/img/Google%20Trends.png" width="30" height="20" alt="Google Trends">

Using the Google Trends API with Python, I intend to analyse and list the Google Search results on queries related to "when is it ideal to post on social networks".

The code is [here](Google.Search.Analysis.ipynb)


# Instagram Forecast <img src="https://github.com/AgosBal/Instagram-Reach/blob/4abb54adfbc157be97f828eeca8b7f0fb6075498/img/Instagram.png" width="20" height="20" alt="Instagram">
While social media is part of our daily lives, we have a life outside of it and are not always connected.

I did a little analysis on the search for "when is the ideal time to post": [here](Google.Search.Analysis.ipynb). Were I discovered that people are still looking for information related to this topic.

So, knowing the ideal time to post on Instagram can be useful for those who use Instagram as a means of contacting their customers and prospects, if they know their content is going to be of interest.

This project aims to help these people by showing them how many visitors will see their post, story, reel, etc, so that they can plan their strategies in the best way, hopefully resulting in metrics showing improved performance and therefore greater success. Instagram reach prediction helps to know how many users will be reached by content posted on Instagram, based on historical data, among other factors.

For this case I will use this [dataset](Instagram-Reach.csv) and the process will be done in [Python](Instagram.Forecast.ipynb).

# Conclusions
1. During the trends analysis of Instagram reach I got to this plot
<img src="https://github.com/AgosBal/Instagram-Reach/blob/51c616296eef7bcf787eeb9a20f08f9ca4cd5263/img/Trend%20of%20Instagram%20reach.png" width='1500' height='500' alt="Instagram Reach Trend">
A general trend of growth in reach on Instagram can be observed.

Considering that in the months of July to October the reach is higher, a hypothesis to verify would be that in the year 2023 a growth trend is expected in those months.

2. For its part, the company should review the peaks of reach to replicate what was done on those days. To do so, I obtained the following bar chart showing the behaviour of the outreach day by day.
<img src="https://github.com/AgosBal/Instagram-Reach/blob/51c616296eef7bcf787eeb9a20f08f9ca4cd5263/img/Instagram%20reach%2C%20day%20by%20day.png" width='1500' height='500' alt="Instagram Reach day by day">

3. The next step was to create a box plot to visualize the distribution of Instagram reach, showing quartiles, median and outliers.
<img src="https://github.com/AgosBal/Instagram-Reach/blob/51c616296eef7bcf787eeb9a20f08f9ca4cd5263/img/Instagram%20reach%20box%20plot.png" width='1500' height='500' alt="Instagram Reach box plot">
The box plot shows that Instagram's reach is approximately normally distributed, with a median of 50.000 accounts aproximately. This means that half posts got at least 50.000 accounts reach, and half posts had less than 50.000 accounts reach.

According to the quartiles, 75% of the publications had a reach of 75,000 accounts or less, while the remaining 25% had a reach of more than 75,000 accounts.

The interquartile range (IQR) indicates that 50% of the publications had a reach between 25,000 and 75,000 accounts.

There are some outliers. These are the points that lie outside the interquartile ranges. In this case, there are two outliers, one above the third quartile and one below the first quartile.

Overall, the box plot shows that Instagram reach is a positive measure of the performance of a post or story.

4. The next step was to add a column named 'Day Name' to figure out the behaviour of Instagram's reach depending on the day of the week. 
<img src="https://github.com/AgosBal/Instagram-Reach/blob/17a7cf04cb7afa8917f874aa332a1dab142edee8/img/Instagram%20Reach%20by%20day%20of%20week..png" width='1500' height='500' alt="Instagram reach by day of the week">

The day with the highest average reach is Tuesday, (54,000 accounts reached), followed in decreasing order by Sunday, Monday, Wednesday, Thursday, Saturday and Friday. 
For all days 50% of the reach is below 48,000 - 35,000 accounts reached and the remaining above those values.
The day with the highest concentration of values around the average is Saturday. The day with the highest dispersion of values around the average is Tuesday.
Considering only these values: 
* If looking to maximise the reach of Instagram posts, it is recommended to post on Tuesdays.
* If looking for a more stable and predictable reach, it is recommended to post on Saturdays.

5. The function "seasonal_decompose" from the Statsmodels library was used to perform a seasonal decomposition of the time series. The seasonal decomposition consists of dividing the time series into three components:

* Trend: The long-term trend of the time series.
* Seasonal: The periodic patterns that repeat over time.
* Resid: The variability in the time series that cannot be explained by trend or seasonality.

A "multiplicative" model is used since the apparent trend over time is decreasing and not linear or stable (which would suggest using an "additive" model). It can be seen that the trend is decreasing, therefore the multiplicative model was correctly chosen.

<img src="https://github.com/AgosBal/Instagram-Reach/blob/17a7cf04cb7afa8917f874aa332a1dab142edee8/img/Instagram%20reach%20Time%20Series%20Forecasting.png" width="1500" height="500" alt="Seasonal decompose">

Based on the graph, it can be inferred that the Instagram reach of the account has a clear seasonality. Reach decreases in the months of May, August, November and March. These months should be taken into account to analyse the possible external causes of the declines in the trend.

The residual appears to be relatively small, indicating that the seasonal decomposition has been effective. The behaviour of the residual in the central months of the period analysed (April 2022 - April 2023) is striking. This may be due to the fact that the seasonality of the scope of the account is stronger during these months. In addition, the residual seems to have a negative peak in August 2022, which may be due to a specific event that occurred in that month. To identify the causes of the patterns observed in the residual, a correlation analysis between the residual of a seasonal decomposition and the variable Date was used, and it was found that there is no relationship between them, so the patterns may be due to other variables such as marketing strategy, Instagram popularity or external events.

6. To understand a little more about seasonal behaviour and predict how the reach will behave, the SARIMA (Seasonal Autoregressive Integrated Moving Average) model was used, to predict stationary time series with seasonality.
It works by splitting the time series into two components:
* Non-seasonal component: represents the long-term trend of the time series.
* Seasonal component: represents seasonal patterns of the time series. 
It has 5 parameters, of which it uses p, d and q to model the first one and the parameters P, D and Q for the second one. 

An automatic fitting of the model was performed to find the best fit to the data and to avoid over-fitting. The selection of the model parameters was done as follows: the first using the autocorrelation plot, the second with a partial autocorrelation plot, while the third is = 1. 

This was the result for p:
<img src="https://github.com/AgosBal/Instagram-Reach/blob/17a7cf04cb7afa8917f874aa332a1dab142edee8/img/Autocorrelation%20plot%20for%20q.png" width="1000" height="500" alt="Autocorrelation for p">

This for q:
<img src="https://github.com/AgosBal/Instagram-Reach/blob/17a7cf04cb7afa8917f874aa332a1dab142edee8/img/Partial%20Autocorrelation.png" width="1000" height="500" alt="Partial autocorrelation for q">

<img src="https://github.com/AgosBal/Instagram-Reach/blob/f6f05e95f905273ece8dd5b084917b661345f57b/img/agostina-balverde-high-resolution-logo-transparent.png" width="350" height="110" alt="Agostina Balverde logo">
