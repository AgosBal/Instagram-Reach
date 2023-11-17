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
<img src="https://github.com/AgosBal/Instagram-Reach/blob/51c616296eef7bcf787eeb9a20f08f9ca4cd5263/img/Instagram%20Reach%20by%20day%20of%20week.png" width='1500' height='500' alt="Instagram reach by day of the week">

The day with the highest average reach is Tuesday, (54,000 accounts reached), followed in decreasing order by Sunday, Monday, Wednesday, Thursday, Saturday and Friday. 
For all days 50% of the reach is below 48,000 - 35,000 accounts reached and the remaining above those values.
The day with the highest concentration of values around the average is Saturday. The day with the highest dispersion of values around the average is Tuesday.
Considering only these values: 
* If looking to maximise the reach of Instagram posts, it is recommended to post on Tuesdays.
* If looking for a more stable and predictable reach, it is recommended to post on Saturdays.

5. 




<img src="https://github.com/AgosBal/Instagram-Reach/blob/f6f05e95f905273ece8dd5b084917b661345f57b/img/agostina-balverde-high-resolution-logo-transparent.png" width="350" height="110" alt="Agostina Balverde logo">
