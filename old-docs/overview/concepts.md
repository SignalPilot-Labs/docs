Signalpilot | #1 AI Agent for Jupyter Lab
Guide































Concepts
Learn the key features that make SignalPilot powerful

Mental model
SignalPilot is an agentic AI layer on top of Jupyter cells.

It reads the visible notebook state (cells, kernel state, data in data folder, db connections etc),

Talks to an LLM, and proposes a plan of steps, and code diffs.

You can apply, run or restore the diffs—under your rules.

SignalPilot then analyzes the outputs and plots and gives you an in-depth analysis.

Agents
An “agent” is the AI helper that understands your notebook and goals (powered by Claude). You invoke it to complete code, explain notebooks, debug errors, or generate charts.

Invoke: type a prompt or use a shortcut (e.g., “Explain this error”).

@ Mentions
“@ Mentions” let you reference cells, dataframes, CSVs, databases in plain English so the agent can use them.

Example: find the most expensive and highly rated products in product_dataset .


Planning
SignalPilot automatically keeps a plan and updates the plan iteratively as it continues the analysis:


Prompt: Do dollar cost averaging investment in SPY every month with $1000 for the last 5 years
Modes
SignalPilot has multiple modes that allow different level of user control over the notebook analysis.

Agent Mode: For maximum AI powered notebook automation — suitable for running end to end AI powered analysis.

Hands on Mode: For better control — manually decide what gets added to AI context and modify 1-2 cell at a time.

Ask Mode: Ask questions about the notebook. AI will not make changes to notebook.

Modes can be changed on the bottom right corner input text box.

Tab Autocomplete
SignalPilot supports tab autocomplete. If enabled one tab accepts the current suggestion and esc rejects it.


Demonstration of tab autocomplete

Previous
Installation

Next
Security and Privacy
On This Page
Mental model
Agents
@ Mentions
Planning
Modes
Tab Autocomplete
© 2025 SignalPilot | All Rights Reserved