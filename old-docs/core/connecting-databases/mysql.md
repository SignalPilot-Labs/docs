S
Signalpilot AI
Open Menu

Signalpilot | #1 AI Agent for Jupyter Lab
Guide
Reference

Show






































Connecting a MySQL Database
Instructions on how to connect a MySQL Database to SignalPilot

To connect MySQL to SignalPilot, you’ll need a few details from your database. These can usually be found in your MySQL server settings, your cloud provider dashboard, or from your database administrator.

Required Information
Connection Name
A friendly name for your database (e.g., Staging DB, Customer DB).
Tip: This is just for your reference in SignalPilot.

Description (Optional)
Add notes about what this database is used for.

Database Type
Select MySQL.

Connection Method

Configuration: Fill in the fields manually.

Connection URL: Paste a full connection string (see below).

Configuration Fields
Host

The server address where your MySQL database is running.

Example:

Local: localhost

Cloud: something like mydb.abc123.us-east-1.rds.amazonaws.com

Port

Default: 3306 (only change if your database uses a non-standard port).

Database

The name of the specific MySQL database you want to connect to.

Example: customer_data

Username

The MySQL user with access to this database.

Example: db_user

Password

The password for the MySQL user above.

Note: Credentials are encrypted locally using AES-256.

Connection URL (Alternative Method)
Instead of filling in fields manually, you can use a MySQL connection URL.

The format is:

mysql://<username>:<password>@<host>:<port>/<database>

plaintext
Example:

mysql://db_user:mysecretpassword@mydb.abc123.us-east-1.rds.amazonaws.com:3306/customer_data

plaintext
Paste this into the Connection URL field to connect quickly.

Testing and Creating the Connection
After entering your details, click Create Connection.

SignalPilot will test the connection to confirm access.

Once successful, your MySQL database will be ready to use inside SignalPilot.




Previous
Connecting a PostgreSQL Database

Next
Connecting a Snowflake Database
On This Page
Required Information
Configuration Fields
Connection URL (Alternative Method)
Testing and Creating the Connection
© 2025 SignalPilot | All Rights Reserved