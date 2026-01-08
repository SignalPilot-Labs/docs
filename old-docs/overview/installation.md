Signalpilot | #1 AI Agent for Jupyter Lab
Guide































Installation
Get SignalPilot up and running in minutes with one of three installation methods.

📦 Prerequisites
Before installing, make sure your system meets the following requirements:

Python: 3.10 or higher

JupyterLab: ≥ 4.0.0 (Does not work with Jupyter Notebook classic or vscode)

STRONGLY Recommended libraries to install:

pandas, numpy, matplotlib, scikit-learn, seaborn

Internet connection

Option 1: Conda Environment (Recommended)

We strongly recommend installing conda for package management.

(Optional) Step 1: Install Conda on MacOS, if not installed

wget https://repo.anaconda.com/miniconda/Miniconda3-latest-MacOSX-x86_64.sh -O ~/miniconda.sh
bash ~/miniconda.sh -b -p $HOME/miniconda
shell
For other OS / other methods check: https://docs.conda.io/projects/conda/en/stable/user-guide/install/macos.html

Step 2: Create and Activate Conda Environment named

conda create --name spilot
conda activate spilot
shell
Step 3: Install packages inside conda environment

pip install signalpilot-ai jupyterlab 
pip install pandas numpy seaborn scikit-learn
shell
Option 2: Direct pip Installation

pip install signalpilot-ai jupyterlab 
pip install pandas numpy seaborn scikit-learn
shell
Option 3: UV Based Installation

If you use uv, the Rust-based fast package installer.
(Optional) Install UV: https://docs.astral.sh/uv/getting-started/installation/

Then Install Packages:

uv init --python 3.11
uv pip install signalpilot-ai jupyterlab 
uv pip install pandas numpy seaborn scikit-learn
shell
🚀 Verify and Launch Jupyter
After installation, verify that SignalPilot is working:

Check versions

Python: 3.10 or higher

JupyterLab: ≥ 4.0.0

python --version
jupyter lab --version
shell
Start JupyterLab

# conda
jupyter lab
# or uv
uv run jupyter lab
shell
Confirm extension

Open JupyterLab

Look for the SignalPilot icon in the sidebar and sign in/sign up

Manage Subscriptions and Account: app.signalpilot.ai

Open it and run a quick test notebook

🛠️ Troubleshooting
Common Issues
Extension not showing up

Restart JupyterLab

Clear browser cache

Ensure JupyterLab ≥ 4.0

Python version mismatch

Upgrade to Python 3.10 or higher

On macOS/Linux:

pyenv install 3.12
pyenv global 3.12
shell
🤝 Support
Docs: docs.signalpilot.ai

Email: info@signalpilot.ai


Previous
Quickstart

Next
Concepts
On This Page
📦 Prerequisites
Option 1: Conda Environment (Recommended)
Option 2: Direct pip Installation
Option 3: UV Based Installation
🚀 Verify and Launch Jupyter
🛠️ Troubleshooting
Common Issues
🤝 Support
© 2025 SignalPilot | All Rights Reserved