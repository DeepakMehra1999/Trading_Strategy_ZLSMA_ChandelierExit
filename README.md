# ZLSMA - Zero Lag LSMA & Chandelier Exit Strategy

This script implements the ZLSMA (Zero Lag Least Square Moving Average) and Chandelier Exit strategy in TradingView's Pine Script.

## Functionality

This script combines the ZLSMA indicator and the Chandelier Exit strategy to generate trading signals. The ZLSMA indicator is a variation of the Linear Regression Moving Average that aims to reduce lag. The Chandelier Exit is a volatility-based stop-loss indicator. It works best on 5 minute timeframe.

## Inputs

- `ATR Period`: The period used for calculating the Average True Range (ATR). Here I am using it 1. 
- `ATR Multiplier`: The multiplier applied to the ATR to calculate the stop-loss levels. Here I am using it 2.
- `Show Buy/Sell Labels?`: Determines whether to display labels for buy and sell signals.
- `Use Close Price for Extremums?`: Specifies whether to use the close price or the highest/lowest price for calculating the stop-loss levels.
- `Highlight State?`: Enables highlighting the long and short states on the chart.

## Entry and Exit Conditions

The script defines the following entry and exit conditions:

- Entry conditions for long position:
    - `Long Condition 1`: Buy signal when the close price is greater than the ZLSMA plus 10.
    - `Long Condition 2`: Buy signal when the close price is less than the ZLSMA minus 10.
- Exit conditions for long position:
    - `Long Exit Condition 1`: Sell signal or the close price drops below the ZLSMA.
    - `Long Exit Condition 2`: Sell signal or the close price rises above the ZLSMA.
- Entry conditions for short position:
    - `Short Condition 1`: Sell signal when the close price is greater than the ZLSMA plus 10.
    - `Short Condition 2`: Sell signal when the close price is less than the ZLSMA minus 10.
- Exit conditions for short position:
    - `Short Exit Condition 1`: Buy signal or the close price drops below the ZLSMA.
    - `Short Exit Condition 2`: Buy signal or the close price rises above the ZLSMA.

