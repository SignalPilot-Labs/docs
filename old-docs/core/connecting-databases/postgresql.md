S
Signalpilot AI
Open Menu

Signalpilot | #1 AI Agent for Jupyter Lab
Guide
Reference

Show






































Connecting a PostgreSQL Database
Instructions on connecting a PostgreSQL database on SignalPilot

To connect PostgreSQL to SignalPilot, you’ll need a few details from your database. You can usually find these in your database admin console, your cloud provider dashboard, or by asking your database administrator.

Required Information
Connection Name
A friendly name for your database (e.g., Production DB, Analytics DB).
Tip: This is just for your reference in SignalPilot.

Description (Optional)
Add any helpful notes about what this database is used for.

Database Type
Select PostgreSQL.

Connection Method

Configuration: Fill in the fields manually.

Connection URL: Paste a full connection string (see example below).

Configuration Fields
Host

The server address where your database is running.

Example:

Local: localhost

Cloud provider: something like mydb.abc123.us-east-1.rds.amazonaws.com

Port

Default: 5432 (you only need to change this if your database runs on a different port).

Database

The name of the specific PostgreSQL database you want to connect to.

Example: analytics

Username

The PostgreSQL user with permissions to access this database.

Example: db_user

Password

The password for the PostgreSQL user above.

Note: Credentials are encrypted locally using AES-256.

Connection URL (Alternative Method)
Instead of filling in fields manually, you can use a PostgreSQL connection URL.

The format is:

postgresql://<username>:<password>@<host>:<port>/<database>

plaintext
Example:

postgresql://db_user:mysecretpassword@mydb.abc123.us-east-1.rds.amazonaws.com:5432/analytics

plaintext
Paste this into the Connection URL field to connect quickly.

Testing and Creating the Connection
After filling in all required fields, click Create Connection.

SignalPilot will test the connection to ensure the details are correct.

If successful, your PostgreSQL database will be available inside SignalPilot.




Previous
Introduction

Next
Connecting a MySQL Database
On This Page
Required Information
Configuration Fields
Connection URL (Alternative Method)
Testing and Creating the Connection
© 2025 SignalPilot | All Rights Reserved