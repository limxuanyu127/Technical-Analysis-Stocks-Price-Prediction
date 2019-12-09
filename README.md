# Technical-Analysis-Stocks-Price-Prediction
Investigated the potential of technical analysis, by comparing the effectiveness of stock price prediction between a univariate model (ARIMA) and multivariate models (Random Forest Regression, Multiple Linear Regression)

## Research Description (unfinished)

# Exploring predictive models for stock prices



1. Problem Statement
2. Methodology overview
  1. Using technical indicators, try to identify a multivariate model that performs better than a univariate model(benchmark)
    1. Compare RMSE values between models
3. Selecting datasets for prediction
  1. 2 companies&#39; stock
  2. Companies of different sizes and industries
4. Feature selection
  1. 4 technical indicators from 4 broad categories of technical indicators
    1. Average True Range (volatility)
    2. Moving Average Convergence Divergence (trend)
    3. Accumulation Distribution INdex (volume)
    4. Rate of Change (momentum)
  2. Percentage change in close price on days -1, -2, -3
5. Features analysis (explore relationships between features)
  1. Analyse correlation between features, and between features and target variables
  2. Talk about unexpected discovery: low correlation between percentage change in close prices on days -1, -2, -3 vs percentage change in price on day 0
  3. Talk about Possibility of changing target variable
6. Model 1 - ARIMA
7. Model 2 - random forests
8. Model 3 - Multi regression

For models:

- Explain the difference in results when different target variables are used (percentage change vs close price)
- Hyperparameter tuning if there&#39;s time



1. Compare results
  1. Determine which is a better method
  2. Identify possible reasons as to why a certain model work better than others
2. Difficulties faced and possibility of future work to overcome them

### Problem Statement

In stock price prediction, there are 2 schools of thought: the Effecient Market Hypothesis(EMH) and Adapative Market Hypothesis (AMH). AMH states that stock prices are predictable and can be profited from. In this project, I want to explore the possibility of that.

There are many factors that affect the price movements of stocks. However, it is a difficult feat to identify all of them. Moreover, it is impossible to encapsulate all these factors in a model as the problem size will be too huge for computation. Thus, in this project I will focus on a few technical indicators as features for my machine learning models

The ultimate aim of this project is not to predict stock prices accurately as that is virtually impossible given my level of expertise. Rather, I will be comparing various methods and models to predict stock prices, and identify what makes them successful or unsuccessful. In my attempt to predict percentage change in stock prices, I will be looking at 2 broad categories of models: univariate and multivariate. The univariate model will serve as a benchmark for my project. Ultimately, I hope to be able to design a multivariate model that works better than the univariate model. In doing so, I will have successfully utilise the various technical indicators, and also develop a simple framework that can be used to predict changes in stock prices more accurately.

### Methodology

Due to the complexity and uncertainty of this problem, I have redesigned the methodology multiple times. After much contemplation, I have broken down my methodology into the following steps

1. Feature Selection
  1. Generate technical indicators that will be used as input variables for my model
2. Target selection
  1. Due to the unpredictability of stock price movements, it may or may not be easy to predict percentage changes in stock prices. Feature-target correlation will have to be analysed to determine that
3. Model Selection
  1. Choosing which univariate model to use
  2. Choosing which multivariate models to use
4. Model assessment
  1. Train the models and use them to predict results
  2. Compare results across all models (RMSE values)
5. Model Evaluation
  1. Determine which models work better, and try to identify what elements of those models make them more successful

### Feature Selection

There are 4 major categories of technical indicators:

1. Volatility
2. Trend
3. Momentum
4. Volume

Due to time constraints, I was unable to select the best amongst the many different indicators that are commonly used. However, I decided to use at least 1 indicator from each category for my model. This is to ensure that my project covers the minimum breath or scope of technical indicators.

Aside from these technical indicators, other possible features would include the percentage change in price 1,2 and 3 days ago, as these intuitively seem to carry information of what tomorrow&#39;s percentage change in price would be.

Fundamental indicators was removed from the scope of the project. This is because it is difficult to identify strong fundamental indicators, especially for short-term price predictions.

Target selection

After consulting seniors, setting percentage change in stock prices as a target variable/ dependent variable seemed logical because afterall, traders are more interested in the percentage change in stock prices rather than its absolute value when traders trade stocks.

However, when identifying relationships between the features and this target variable, the correlation is weak, showing a possibility that these features might actually have negligible influence on the percentage changes in stock prices. The way to resolve this issue is to either change the features, or change the target variable.
