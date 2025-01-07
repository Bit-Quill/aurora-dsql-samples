# Using DataGrip to interact with Aurora DSQL

This section describes how to use DataGrip from JetBrains to interact with Aurora DSQL.

DataGrip is a powerful, cross-platform database management tool, designed for database developers and administrators. It provides a comprehensive environment for working with relational databases, offering a wide range of features to streamline database management, development, and analysis.

Before you begin, make sure that you have completed the following prerequisites.

- Created a cluster in Aurora DSQL.
- Created an AWS account and configured the credentials and AWS Region.

## Steps to use DataGrip

**1. Install DataGrip:**

Ensure you have DataGrip installed. You can download it from the [official website](https://www.jetbrains.com/datagrip)

**2. Create a new Project:**

  <image src="images/image1.png" width="600" height="audio" />

**3. Enter Project name:**

  <image src="images/image2.png" width="400" height="audio" />

**4. Create a New PostgreSQL (AWS Wrapper) Data Source:**

  <image src="images/image3.png" width="600" height="audio" />

In the Database tool window (usually on the left side), click the "+" icon and select Add Data Source > PostgreSQL (AWS Wrapper). This will automatically set up the connection type for PostgreSQL (AWS Wrapper).

**5. Configure the Connection:**

In the Data Source Properties window, you will need to enter the following details:

- Host: DSQL Cluster Endpoint.
- Port: The port on which PostgreSQL is running. The default port is 5432, but if your DSQL is running on a custom port, use that instead.
- Database: The name of the database you want to connect to.
- User: The username to authenticate with the database
- Password: The password for the specified username.

  **Note**: User / Password can be retrieved using the ‘Connect’ button next to the Cluster Endpoint on the Aurora DSQL web page.

<image src="images/image4.png" width="600" height="audio" />

**6. JDBC Driver Setup:**

DataGrip automatically includes the PostgreSQL JDBC driver, so you should not need to download it manually. However, if for some reason the driver is missing or outdated, DataGrip will prompt you to download it.

<image src="images/image5.png" width="400" height="audio" />

**7. Test the Connection:**

- Once you've entered all the details, click the ‘Test Connection’ button at the bottom of the window.
- If the connection is successful, you will see a green check mark indicating everything is set up correctly.
- If there's an error, DataGrip will provide more details on the issue (such as incorrect login credentials, database name, or network connectivity problems).

**8. Save the Data Source:**

- After successfully testing the connection, click OK to save the data source. Your PostgreSQL (AWS Wrapper) connection will now appear in the Database tool window.

**9. Start Querying:**

- You can now expand the connection in the Database tool window to see the list of schemas, tables, views, etc.
- Open a new SQL console by right-clicking the database name in the Database window and selecting New Console.
- Write and execute your SQL queries as usual.

## Known Issues

- DataGrip fails to list tables in schema, a example workaround to list tables is to run the following query.

    ````
    SELECT *
    FROM information_schema.tables
    WHERE table_schema = 'public';
    ````

## Additional Tips

- Auto-Completion and Code Assistance: DataGrip will provide SQL auto-completion, syntax highlighting, and other PostgreSQL-specific features like functions and data types.
- Database Navigation: You can use the Database tool window to explore tables, views, indexes, and other objects, and right-click on any object to perform actions like opening it in the editor or generating SQL scripts.

**Connection Issues:** If the connection fails, check the following:

- Ensure your Aurora DSQL cluster is accessible from your machine.
- Ensure that the username and password are correct.
- Ensure that firewall or network settings allow connections on port 5432.
