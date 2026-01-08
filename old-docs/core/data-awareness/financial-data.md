Signalpilot | #1 AI Agent for Jupyter Lab
Guide






































Financial Data
Automatic retrieval of financial datasets

SignalPilot agents can connect directly to Yahoo Finance to help you bring in common financial datasets without leaving your notebook. The agent can search, download, and save data in a ready-to-use format for analysis.

What You Can Get
Stocks – historical prices, volumes, and company fundamentals.

Options – chains, implied volatility, and strike-level data.

Crypto – major cryptocurrencies with historical price and volume data.

ETFs – price history, holdings, and performance metrics.

How It Works
Search – Ask the agent to look up a ticker or name on Yahoo Finance.

Example: “Search Yahoo Finance for AAPL stock data.”

Download – The agent fetches the dataset (prices, options chain, crypto, or ETF data).

Save as CSV – Files are automatically stored in your notebook’s /data folder for reuse.

Use in Analysis – Load the CSV with pandas or your preferred library, then analyze, visualize, or model directly inside SignalPilot.

Example Interaction
You: “Get the last 2 years of daily Bitcoin prices from Yahoo Finance and plot the price.”
Agent: Downloads BTC-USD data, saves it to /data folder, loads it into a dataframe, and then plots them.

FAQ
Q: What sources does SignalPilot use for finance data?
SignalPilot uses Yahoo Finance as the default source for stocks, options, crypto, and ETFs.

Q: Where are downloaded files saved?
All datasets are saved as CSV files in your notebook’s /data folder.

Q: How do I load the data after download?
You can load any dataset with:

import pandas as pd
df = pd.read_csv("data/FILE_NAME.csv")
plaintext
Q: Can I fetch live data?
Yahoo Finance provides near real-time data for some assets, but most data is delayed by a few minutes.

Q: Can I request multiple tickers at once?
Yes. You can ask the agent to fetch several tickers in a single request (e.g., AAPL, MSFT, AMZN).

Q: Does SignalPilot store my finance data outside the notebook?
No. All data is stored locally in your /data folder, following SignalPilot’s zero data retention policy.


Previous
Tools

Next
Bring Your Own Data (BYOD)
On This Page
What You Can Get
How It Works
Example Interaction
FAQ
© 2025 SignalPilot | All Rights Reserved