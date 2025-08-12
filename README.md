# $TRUMP Sentiment Analysis & Cryptocurrency Price Prediction

## Overview
This project analyzes the relationship between cryptocurrency price movements and market sentiment, with a primary focus on the $TRUMP token. To provide context and comparison, four additional cryptocurrencies are included: Bitcoin (BTC), Ethereum (ETH), Chainlink (LINK), and Dogecoin (DOGE).

The aim is to investigate whether market sentiment — measured using the Crypto Fear & Greed Index — has a measurable and predictive influence on crypto prices, and to evaluate different modeling approaches for forecasting.

---

## Datasets
1. **Price Data**  
   - Source: [AlphaVantage API](https://www.alphavantage.co/documentation/)  
   - Assets: $TRUMP, BTC, ETH, LINK, DOGE  
   - Data: Daily OHLCV (Open, High, Low, Close, Volume) values.

2. **Sentiment Data**  
   - Source: [Alternative.me Crypto Fear & Greed Index](https://alternative.me/crypto/fear-and-greed-index/)  
   - Data: Daily sentiment scores (0–100) and sentiment labels (e.g., "Extreme Fear", "Greed").

---

## Methodology

### Data Preparation
- Imported historical price data for all coins using the AlphaVantage API.
- Downloaded and cleaned sentiment data from Alternative.me.
- Merged datasets to align daily prices with corresponding sentiment scores.
- Performed exploratory data analysis (EDA) to understand trends, volatility, and sentiment patterns.

### Feature Engineering
- Created lagged features (previous day’s close and sentiment).
- Computed rolling averages and volatility measures.
- Derived daily returns as percentage changes.
- Encoded sentiment labels for modeling.

### Analysis & Modeling
The following techniques were implemented:
1. **Statistical Tests**  
   - Normality tests, T-tests, ANOVA, and Chi-Square to validate relationships and differences.
2. **Dimensionality Reduction**  
   - PCA to remove redundancy and simplify the feature space.
3. **Time Series Forecasting**  
   - Prophet model for trend-seasonality analysis and forecasting.
4. **Clustering**  
   - Grouped similar market behavior periods using unsupervised learning.
5. **Regression & Classification**  
   - Tree-based models (Random Forest, XGBoost) and classifiers to predict prices or direction.
6. **Probabilistic Reasoning**  
   - Modeled the probability of specific market outcomes given sentiment and historical patterns.

---

## Key Findings
- Market sentiment affects coins differently: speculative tokens like $TRUMP are more sensitive to sentiment swings than BTC or ETH.
- Statistical tests confirmed meaningful differences between assets and their sentiment–price relationships.
- Dimensionality reduction improved model interpretability but did not significantly boost predictive accuracy.
- General-purpose ML models struggled with high volatility and irregular trends.
- The **Prophet model** consistently provided the most accurate and stable forecasts, especially when incorporating sentiment as a regressor.

---

## Final Hypothesis
Market sentiment, measured via the Fear & Greed Index, exerts a stronger and more immediate influence on speculative tokens like $TRUMP than on established cryptocurrencies. Integrating sentiment into forecasting models should improve short-term predictions for these assets.

---

## Conclusion
While multiple analytical methods were applied to meet course requirements — statistical testing, dimensionality reduction, clustering, regression, classification, and probabilistic reasoning — their practical contribution to forecasting accuracy was limited.  
The **Prophet model** outperformed all other approaches in balancing accuracy, interpretability, and robustness. Its ability to model irregular but trend-driven price movements, augmented by sentiment data, makes it the most suitable tool for this task.

---

## Requirements
- Python 3.8+
- Packages: `pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn`, `xgboost`, `prophet`, `tensorflow` (if experimenting with deep learning)

---

## How to Run
1. Clone this repository.
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
