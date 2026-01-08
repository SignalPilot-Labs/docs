
S
Signalpilot AI
Open Menu

Signalpilot | #1 AI Agent for Jupyter Lab
Guide
Reference

Show



































Bring Your Own Data (BYOD)
Do AI-assisted analysis on your custom datasets

Not all data lives on Yahoo Finance. With Bring Your Own Data (BYOD), you can add any dataset to your SignalPilot notebook and let the agent use it seamlessly in analysis.

How BYOD Works
Download or prepare your dataset – in CSV format.

Save it in the /data folder of your SignalPilot notebook.

Agent becomes aware – once stored, the agent can automatically detect and load the file.

Chat-driven analysis – simply ask the agent to explore, clean, or visualize your data.

What You Can Use It For
Scientific data (e.g., climate, biology, health records).

Product data (e.g., customer record, A/B test, growth).

Public datasets (e.g., Kaggle, government portals).

Custom exports (e.g., CRM reports, log files).

Any CSV-based dataset you need for analysis.

Example Interaction
You: “I uploaded a dataset on customer churn. Load it and build a model predicting churn probability.”
Agent: Detects churn.csv in /data, loads it into a dataframe, runs preprocessing, trains a model, and reports performance.

FAQ
Q: What file formats are supported?
Currently, SignalPilot supports CSV files for BYOD.

Q: Where should I save my data?
Save it to the /data folder in your notebook. SignalPilot agents automatically check this location.

Q: Do I need to tell the agent the file name?
Not always. If your dataset has a clear name, you can just describe it in chat, and the agent will match it automatically. You can also @mention it in the context.

Q: Can I use multiple datasets together?
Yes. You can ask the agent to join, merge, or compare across multiple BYOD CSVs.

Q: Is my data private?
Yes. BYOD data never leaves your notebook environment. SignalPilot follows a zero data retention policy.

Q: Do I need to write code to load my BYOD data?
No. Just ask the agent in chat, and it will handle loading and preparing the dataset for you.


Previous
Financial Data

Next
Overview
On This Page
How BYOD Works
What You Can Use It For
Example Interaction
FAQ
© 2025 SignalPilot | All Rights Reserved