# Bike Rent Prediction
> This project aims to develop a predictive model to forecast the demand for shared bikes in the American market, focusing on key factors that influence bike usage. BoomBikes, a leading bike-sharing provider, has faced challenges due to the ongoing pandemic and seeks to leverage data to understand shifting customer needs. By analyzing historical usage data, this project will identify important variables such as weather, temperature, day of the week, and season that impact bike demand.

Using different approaches of regression, the project will explore how these factors affect demand fluctuations and help predict future trends. The insights gained will enable BoomBikes to optimize operations, adjust fleet distribution, refine pricing strategies, and tailor marketing efforts to align with expected demand.

Ultimately, the goal is to provide BoomBikes with a data-driven approach to better anticipate demand, enhance customer satisfaction, and improve operational efficiency. By understanding these demand dynamics, BoomBikes can strengthen its position in the competitive bike-sharing market as the economy recovers.


## Table of Contents
* [General Info](#general-information)
* [Conclusions](#conclusions)
* [Technologies Used](#technologies-used)


## General Information
- This project aims to model and predict the demand for shared bikes in the American market using various factors such as weather, temperature, and day of the week. The goal is to understand how these variables influence bike usage and help BoomBikes optimize its operations post-pandemic.
- BoomBikes, a bike-sharing provider in the US, has faced a significant decline in revenue due to the COVID-19 pandemic. The company aims to develop a strategy to forecast bike demand as the economy recovers, ensuring it can meet customer needs effectively.
- The business problem being addressed is predicting the demand for shared bikes in a post-pandemic market. The goal is to help BoomBikes adapt its strategies based on demand fluctuations, optimize operations, and increase profitability as the economy stabilizes.
- The dataset being used contains daily bike demand data across the American market, influenced by various factors such as weather, temperature, and people's behavior patterns. This data will be analyzed to model and predict future bike demand.


## Conclusions
Several models were built involving simple linear regression with RFE, VIF, p values, ridge regression, lasso regression.

The inference from linear regression is as follows:

- The features used in the prediction of the target variable cnt (bike bookings) are:
yr, temp, Jul, Sep, Sun, misty/cloudy, snow/rain/thunderstorm, spring, summer, winter (10 features)

- As per the absolute values of the coefficients or weights of the linear regression model, the top 3 features contributing significantly towards the demand of shared bikes are as follows:

1. temp : A one-unit increase in temp leads to 0.5044 increase in bike bookings. This suggests that warmer weather significantly drives bike demand.

2. yr : A unit increase in yr variable increases the bike hirings by 0.2328 units. This reflects a rising trend in demand over time, indicating business growth.


3. snow/rain/thunderstorm: : A unit increase in snow/rain/thunderstorm decreases bike bookings by 0.3004 units. This indicates that adverse weather conditions negatively impact bike demand.

The analysis reveals that bike demand is mainly positively influenced by warmer temperatures and an increasing trend over the years, while adverse weather conditions (snow/rain/thunderstorm) tend to decrease bike bookings. Besides, other factors like Sun, Jul, Sep, misty/cloudy, spring, summer, winter also influence bike booking demands.

The overall inference from all the models is as follows:

1. For linear regression, R2 score is 0.81 and 10 features are used which is an extremely good model.

2. For ridge regression, R2 score is 0.83 but all the features are kept with very small coefficients for the less important ones as is the nature of the ridge regression model.

3. For lasso regression, with alpha as 0.005, R2 score was 0.77 with just 7 features. We are reducing complexity of model by 75% by compromising just 7% performance. Features used:
'yr','atemp','Sun','misty/cloudy','snow/rain/thunderstorm','spring','winter'

4. For lasso regression, with alpha as 0.01, R2 score was 0.71 with just 5 features. We are reducing complexity of model by 83% by compromising just 10% performance. Features used:
'yr','atemp','misty/cloudy','spring','winter'

5. In the final model, both lasso and ridge regression were combined. From 29 features, 7 features were shortlisted from lasso regression at alpha=0.005. These features were applied on ridge regression to get a decent R2 of 0.80. We reduced 76% of complexity, with only slight compromise in performance by 3.6% as compared to original ridge regression model where all features were used and R2 score was 0.83. 

For many cases in the industry where a simpler model is prefered to a complex model while still maintaining an acceptable performance, the fifth regression model can be used as the model is maintaining simplicity as well as having acceptable r2 score.


## Technologies Used
- pandas version: 2.2.2
- numpy version: 1.26.4
- matplotlib version: 3.8.0
- seaborn version: 0.13.2
- scikit-learn version: 1.5.2
- statsmodels version: 0.14.4



## Contact
Created by Anusha Chaudhuri [@anusha761]


