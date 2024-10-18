# Stateful Machine learning neural network strategy
This is an example of a trading strategy that utilizes a neural network to predict price movements in the S&amp;P 500 stocks
## How to Run the Strategy
### In an Online Environment

The strategy can be executed in an online environment using Jupiter or JupiterLab on the [Quantiacs personal dashboard](https://quantiacs.com/personalpage/homepage). To do this, clone the template in your
personal account.

### In a Local Environment

To run the strategy locally, you need to install the [Quantiacs Toolbox](https://github.com/quantiacs/toolbox).

## Strategy Overview

### Key Features:
-Universe: S&P 500 stocks

-Trading Logic: A neural network predicts the probability of price movements for selected stocks. 
The strategy takes positions based on these predictions, with exits defined for take profit, stop loss, and holding period limits.

-Indicators Used: Average True Range (ATR), Relative Strength Index (RSI) and  candlestick pattern.

-State Management: Utilizes the Quantiacs state management system to maintain and update strategy state across different days.

## Strategy Overview

This strategy uses a stateful approach to manage  positions with exits.
It operates on S&P 500 stocks, dynamically selects the 15 least volatile
and uses feedforward neural network to predict whether the price will rise
and  create entry trading signals based on predictions. For exit take profit,
stop loss, and holding period limits are used.

### Strategy Components:
1. Data Loading and Preparation:
   Load stock data using qndata.stocks.load_spx_data
2. Strategy Function:
   Define the strategy function which computes the weights  based on entry and exit signals.
3. State Management:
   Use state to manage positions, model and exits dynamically.
   Due to the state requirement, this strategy and the exits only work with the multipass 
4. Backtesting:
   Use the backtest_ml to evaluate the strategy .
