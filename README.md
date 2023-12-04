# MSBA-Product-Forecasting

## Business Problem
Maverik, one of the leading fuel and convenience stores in the intermountain west, opens approximately 30 new stores per year. This rapid business expansion makes operational planning for new stores a significant undertaking. Maverik needs to accurately forecast annual sales for four key categories: gasoline, diesel, food service, and merchandise. Improved forecasts are critical to effectively plan initial return on investment documents.

## Group 4 Solution
After comprehensive exploratory data analysis, my team, “Group 4” developed three different modeling approaches to forecast sales, including a penalized regression (LASSO) model, an autoregression in moving averages (ARIMA) model, and a vector autoregression (VAR) model. All groups were favorable in their own respects, but we ultimately recommend using the VAR model for its general applicability, versatility, and accuracy. 

## Contribution
My contributions to the group project include the longitudinal components of the exploratory data analysis. I also wrote the code for the penalized regression model and the VAR model and the shiny app demonstration. 

## usiness Value
The VAR model provides a very versatile tool for forecasting revenue. The model is very computationally efficient, meaning it can be quickly deployed into any R workflow with minimal impact on resources. The model only uses the four key sales indicators, which makes it applicable to any new store that sells these product categories, regardless of the stores’ regions or store features. The model was only trained on one year of sales from each of the given stores, so it can readily predict cumulative sales for any chosen timespan within a year. 

The model could be easily tweaked to forecast longer time horizons if appropriate data is supplied. Individual day forecasts are less accurate because of the model variability; however, the model performs well when forecasting for longer time horizons. Using RMSE as the key performance metric, the VAR model outperforms the baseline on gasoline sales and performs comparably with the other three categories on eight randomly selected holdout sites. We expect the model would improve with more training sites. One of the testing sites held anomalous values for diesel sales which worsened the diesel metrics. More data that contained unique sales would help the model better predict these occurrences.

## Challenges
Traditional time series datasets often forecast longer time horizons on one specific site or location. We were tasked with forecasting a shorter (one-year) time horizon across 38 locations. This provided a logistical challenge as we either needed to forego traditional time series forecasting models or figure out how to compile the predictions of individual models. The penalized regression model, for example, incorporated a pre-engineered 1-day lag for all observations after the opening day. The VAR model forecasts along a pre-engineered variable (“days_since_opening”).

## Key Takeaways
I had some prior experience with time series analysis in my undergraduate studies, but the complexity of this process required me to learn several new methods in a much greater depth. To adapt the models to the specific business problem, I had to write several new functions in R code. This was a new experience for me as most of my prior experience writing functional programming is in Python and Java. This was also a good learning experience for group management. This project was a significant undertaking and breaking up the different components so we could work simultaneously was critical. Our group had to specifically plan out tasks and focus on hitting deadlines so other group members’ steps were not held up. 
