# Modern Portfolio Theory (MPT) - Portfolio Optimization Project:

# Introduction
This project aims to construct an optimal portfolio by applying Modern Portfolio Theory (MPT) using historical data from multiple asset classes. 
The code leverages Python libraries to calculate key portfolio metrics such as expected return, volatility, and Sharpe ratio, and then optimizes the asset allocation to maximize the risk-adjusted return.

# Assets and Time Range
The portfolio consists of five tickers representing different asset classes:
- SPY (S&P 500 ETF)
- BND (Bond ETF)
- GLD (Gold ETF)
- QQQ (NASDAQ ETF)
- VTI (Total Stock Market ETF)

The data is retrieved for a period of 5 years ending today.

# Data Collection
Historically adjusted close prices are retrieved using the Yahoo Finance API (`yfinance`). 

Logarithmic returns are computed based on these prices to assess historical performance and risk.

# Portfolio Metrics
The following portfolio metrics are calculated:
- Expected Return: Annualized mean of the log returns weighted by asset allocation.

- Volatility: Portfolio standard deviation computed from the covariance matrix.


   ![image](https://github.com/user-attachments/assets/b449783a-e952-4ea7-9bb2-c6ebd03edcd7)

The Assumed Risk-Free Rate is 2% in most of the Finance textbooks. 
However, for accurate results we’ll be using the 10-year US Treasury yield as the risk-free rate (retrieved via Federal Reserve Economic Data (FRED) service API which stands for Application Programming Interface).

![image](https://github.com/user-attachments/assets/b3cf3751-e4f5-45ba-9031-508edc0a0999)

Get your Own Free Fred API Key from: https://fred.stlouisfed.org/docs/api/api_key.html

# Portfolio Optimization
Using the `scipy. optimize.minimize` function, the Sharpe Ratio is maximized under the following constraints:
- The sum of weights must equal 1.

- No asset can have more than 5% allocation (i.e., upper bound of 0.05 per asset).

The objective function minimizes the negative Sharpe Ratio to find the optimal asset allocation.

![image](https://github.com/user-attachments/assets/2105e5e7-b4ca-41f1-b49c-a5b15150c832)

Constraints ensure that the total portfolio weights sum to 1, representing full investment. This is done using an equality condition (type='eq') with a function that checks the sum.
Bounds restrict each portfolio weight to a specific range—in this case, between 0 and 1—to limit overexposure to any single asset.

It is important in Portfolio Optimization because Constraints ensure our portfolio behaves like the real one and Bounds add control for instance, to avoid investing money in risky asset class.

# Optimal Portfolio Weights
•	Now we are going to set the initial weight that just says each portfolio or each security in the portfolio is equally weighted.
•	These weights represent the optimal allocation under the defined constraints.

![image](https://github.com/user-attachments/assets/24bce7e6-ce1f-4cb3-985c-a5f2ca157edc)

#  Conclusion
The code successfully demonstrates the use of Modern Portfolio Theory to construct an optimized portfolio with maximum risk-adjusted return. 
By using real-world data and economic indicators, the model ensures practical relevance. Such optimization techniques can be valuable tools in asset management, wealth advisory, and personal investment planning. From the model we get the Optimal Weights as:

Optimal Weights:

•	SPY: 0.5000

•	BND: 0.0000

•	GLD: 0.5000

•	QQQ: 0.0000

•	VTI: 0.0000

•	Expected Annual Return: 0.1378

•	Expected Volatility: 0.1250

•	Sharpe Ratio: 0.7490

# Displaying the Plot Figure

![image](https://github.com/user-attachments/assets/ff201dd5-9d67-4cfa-8c55-0b0fd274ca43)

# Youtube Video:
https://www.youtube.com/watch?v=oszqwwDoFqQ&t=31s

# Video Tutorial:
https://www.youtube.com/watch?v=9GA2WlYFeBU











