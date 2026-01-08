Signalpilot | #1 AI Agent for Jupyter Lab
Guide































Connecting Databricks
How to connect Databricks to Signalpilot

To connect Databricks to SignalPilot, you’ll need your Databricks workspace details and authentication credentials. These can be obtained from your Databricks workspace admin or cloud administrator.


Required Information
Connection Name
A friendly label for this connection.
Tip: This is just for your reference in SignalPilot.

Description (Optional)
Notes about what this connection is used for. Adds context to LLM

Database Type
Select Databricks.

Connection Fields

The easiest method of finding these is going to SQL Warehouses → Click on the warehouse → Connection Details


Connection URL
The URL of your Databricks workspace.

Example:

https://adb-123456789012.3.azuredatabricks.net
plaintext
Authentication Type
Choose how SignalPilot should authenticate with Databricks.

Supported options:

Access Token

Service Principal (OAuth / Client Credentials)

Access Token Authentication
Use this option when authenticating with a personal or workspace access token.

Databricks Access Token
A Databricks personal access token.

How to create it:

Go to User Settings

Open Access Tokens

Click Generate New Token

Copy the token and paste it here

Note: Tokens are encrypted locally using AES-256.

Service Principal Authentication
Use this option for production, team, or automated environments.

Client ID
The Application (Client) ID of your Databricks service principal.

Client Secret
The client secret associated with the service principal.

Note: Client secrets are encrypted locally using AES-256.

SQL Warehouse Configuration
These fields are required for querying Databricks via Databricks SQL.

Warehouse HTTP Path
The HTTP Path of the Databricks SQL Warehouse.

How to find it:

Go to SQL Warehouses

Select your warehouse

Copy the HTTP Path

Example:

/sql/1.0/warehouses/abc123def456
plaintext
Catalog
The default Databricks catalog to use.

Example:

main
plaintext
Schema (Optional)
The default schema within the selected catalog.

If left blank, SignalPilot will pull schema information from all accessible schemas.

Example:

analytics
plaintext
Testing and Creating the Connection
Once your details are filled in, click Create Connection.

SignalPilot will:

Validate authentication

Test connectivity to the SQL Warehouse

Discover available catalogs, schemas, and tables

If successful, your Databricks database will be ready to use inside SignalPilot.

Previous
Connecting a Snowflake Database

Next
Connecting a PostgreSQL Database

© 2025 SignalPilot | All Rights Reserved


Previous
Connecting a Snowflake Database

Next
How to Use AI Agents in Jupyter Notebook in 2025
On This Page
Required Information
Connection Fields
Connection URL
Authentication Type
Access Token Authentication
Databricks Access Token
Service Principal Authentication
Client ID
Client Secret
SQL Warehouse Configuration
Warehouse HTTP Path
Catalog
Schema (Optional)
Testing and Creating the Connection
© 2025 SignalPilot | All Rights Reserved