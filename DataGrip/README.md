# Using DataGrip to interact with Aurora DSQL

This section describes how to use DataGrip to interact with Aurora DSQL.
Before you begin, make sure that you have completed the following prerequisites.
•	Created a cluster in Aurora DSQL.
•	Created an AWS account and configured the credentials and AWS Region.

Steps to use DataGrip
1.	Install DataGrip:

Ensure you have DataGrip installed. You can download it from https://www.jetbrains.com/datagrip/.

2.	Create a new Project:


















3.	Enter Project name:





4.	Create a New PostgreSQL (AWS Wrapper) Data Source:

In the Database tool window (usually on the left side), click the "+" icon and select Add Data Source > PostgreSQL (AWS Wrapper). This will automatically set up the connection type for PostgreSQL (AWS Wrapper).

















 
5.	Configure the Connection:

In the Data Source Properties window, you will need to enter the following details:

o	Host: DSQL Cluster Endpoint.
o	Port: The port on which PostgreSQL is running. The default port is 5432, but if your DSQL is running on a custom port, use that instead. 
o	Database: The name of the database you want to connect to.
o	User: The username to authenticate with the database
o	Password: The password for the specified username.

Note: User / Password can be retrieved using the ‘Connect’ button next to the Cluster Endpoint on the Aurora DSQL web page.

















6.	JDBC Driver Setup:

DataGrip automatically includes the PostgreSQL JDBC driver, so you should not need to download it manually. However, if for some reason the driver is missing or outdated, DataGrip will prompt you to download it.


7.	Test the Connection:

o	Once you've entered all the details, click the Test Connection button at the bottom of the window.
o	If the connection is successful, you will see a green check mark indicating everything is set up correctly.
o	If there's an error, DataGrip will provide more details on the issue (such as incorrect login credentials, database name, or network connectivity problems).

8.	Save the Data Source:

o	After successfully testing the connection, click OK to save the data source. Your PostgreSQL (AWS Wrapper) connection will now appear in the Database tool window.

9.	Start Querying:

o	You can now expand the connection in the Database tool window to see the list of schemas, tables, views, etc.
o	Open a new SQL console by right-clicking the database name in the Database window and selecting New Console.
o	Write and execute your SQL queries as usual.
Additional Tips
•	Auto-Completion and Code Assistance: DataGrip will provide SQL auto-completion, syntax highlighting, and other PostgreSQL-specific features like functions and data types.

•	Database Navigation: You can use the Database tool window to explore tables, views, indexes, and other objects, and right-click on any object to perform actions like opening it in the editor or generating SQL scripts.

•	Connection Issues: If the connection fails, check the following:

o	Verify the Aurora DSQL server is running and accessible from your machine.
o	Ensure that the username and password are correct.
o	Ensure that firewall or network settings allow connections on port 5432.
