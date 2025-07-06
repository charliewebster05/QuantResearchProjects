Oil Volatility Analysis: GARCH vs Rolling Standard Deviation

This project analyses how recent geopolitical stress affects oil price volatility using both simple and advanced models. We compare the performance of a 5-day rolling standard deviation with a GARCH(1,1) model on Crude Oil Futures (CL=F) data from June to July 2025.

# Objective

To understand and visualize:

How short-term volatility reacts to market shocks
How GARCH (Generalised Autoregressive Conditional Heteroskedasticity) captures volatility persistence
The difference in reactivity and interpretation between rolling and model-based volatility
Methods Used

# 5-Day Rolling Volatility:

Uses standard deviation of the last 5 daily returns
Highly reactive to recent shocks
Tends to overestimate short-lived spikes
GARCH(1,1) Model:

Captures volatility clustering and persistence
Smoother and more conservative
Useful for forecasting volatility and risk management

# Code snippet:

model = arch_model(returns, vol='Garch', p=1, q=1)
results = model.fit(disp='off')
oil['garch_vol'] = results.conditional_volatility
Visual Interpretation

# The chart compares both volatility measures over time:

A spike in rolling volatility occurred in mid-to-late June, reaching over 5.2%.
GARCH volatility responded more cautiously, peaking below 4% — reflecting its smoother, persistent nature.
By early July, rolling volatility dropped sharply while GARCH remained stable, showing GARCH’s use as a forecasting tool.

# Insights

Rolling volatility is great for detecting immediate shocks, but it’s noisy and short-term.
GARCH volatility gives a more stable, persistent estimate — making it better for trading filters, risk management, and stress testing.
The divergence between the two can signal transient market panic vs sustained regime shifts.

# Future Ideas

Backtest volatility-based trading strategies (e.g., long oil when volatility spikes)
Extend analysis to other commodities (e.g., natural gas) or equity indices
Compare GARCH to EWMA or EGARCH for asymmetric volatility response
Acknowledgements

Thanks to the Python libraries: yfinance, arch, matplotlib, pandas.
