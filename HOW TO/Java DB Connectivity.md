# Java JDBC Connection Tutorial With Programming Example
Last Updated:September 29, 2022
This JDBC Connection tutorial explains basic steps to a database with examples and provides JDBC connection strings for different databases:

In the previous tutorial of the JDBC tutorial series, we learned components, architecture, and types of drivers in Java Database Connectivity (JDBC).

In this tutorial, we will discuss the steps to connect with databases using JDBC. This tutorial will show you how to do JDBC connection and the perform database operations. JDBC API acts as an interface between the Java program and Database.

At the end of this tutorial, you will be able to write Java programs to connect with databases and perform DB operations.

#JDBC Connection Steps
There are 6 basic steps to connect with JDBC. They are enlisted in the below image:
<img src="https://www.softwaretestinghelp.com/wp-content/qa/uploads/2020/06/2020-06-08_10-36-13.png">

# 1) Import Packages
First, we need to import the existing packages to use it in our Java program. Import will make sure that JDBC API classes are available for the program. We can then use the classes and subclasses of the packages.

Irrespective of the JDBC Driver, add the following import statement in the Java program.

import java.sql.*;
Import the other classes based on the functionality which you will use in the program. Download the appropriate Jar files for the database which you will use in the program.

Refer to the previous tutorial for the links to download the Jar files for your database.

JDBC API 4.0 mainly provides 2 important packages:

java.sql
javax.sql
(i) java.sql package

This package provides classes and interfaces to perform most of the JDBC functions like creating and executing SQL queries.


# 2) Load Driver
First, we should load/register the driver in the program before connecting to the Database. You need to register it only once per database in the program.

We can load the driver in the following 2 ways:

Class.forName()
DriverManager.registerDriver()
(i) Class.forName()
In this way, the driver’s class file loads into the memory at runtime. It implicitly loads the driver. While loading, the driver will register with JDBC automatically.

# 3) Establish Connection
After loading the driver, the next step is to create and establish the connection. Once required, packages are imported and drivers are loaded and registered, then we can go for establishing a Database connection.

DriverManager class has the getConnection method, we will use this method to get the connection with Database. To call getConnection() method, we need to pass 3 parameters. The 3 parameters are string data type URL, a username, and a password to access the database.

The getConnection() method is an overloaded method. The 2 methods are:

getConnection(URL,username,password); – It has 3 parameters URL, username, password.
getConnection(URL); – It has only one parameter. URL has a username and password also.

# 4) Create And Execute Statement
Once the connection has established, we can interact with the connected Database. First, we need to create the statement to perform the SQL query and then execute the statement.

(i) Create Statement
Now we will create the statement object that runs the query with the connected database. We use the createStatement method of the Connection class to create the query.

There are 3 statement interfaces are available in the java.sql package. These are explained below:

a) Statement

This interface is used to implement simple SQL statements with no parameter. It returns the ResultSet object.

Statement statemnt1 = conn.createStatement();
b) PreparedStatement

This PreparedStatement interface extends the Statement interface. So, it has more features than the Statement interface. It is used to implement parameterized and precompiled SQL statements. The performance of the application increases because it compiles the query only once.

It is easy to reuse this interface with a new parameter. It supports the IN parameter. Even we can use this statement without any parameter.

String select_query = “Select * from states where state_id = 1”;
PreparedStatement prpstmt = conn.prepareStatement(select_query);
c) CallableStatement

CallableStatement interface extends the PreparedStatement interface. So, it has more features than the PreparedStatement interface. It is used to implement a parameterized SQL statement that invokes procedure or function in the database. A stored procedure works like a method or function in a class. It supports the IN and OUT parameters.

The CallableStatement instance is created by calling the prepareCall method of the Connection object.

CallableStatementcallStmt = con.prepareCall("{call procedures(?,?)}");
(ii) Execute The Query
There are 4 important methods to execute the query in Statement interface. These are explained below:

ResultSet executeQuery(String sql)
int executeUpdate(String sql)
boolean execute(String sql)
int []executeBatch()
a) ResultSet executeQuery(String sql)

The executeQuery() method in Statement interface is used to execute the SQL query and retrieve the values from DB. It returns the ResultSet object. Normally, we will use this method for the SELECT query.

b) executeUpdate(String sql)

The executeUpdate() method is used to execute value specified queries like INSERT, UPDATE, DELETE (DML statements), or DDL statements that return nothing. Mostly, we will use this method for inserting and updating.

c) execute(String sql)

The execute() method is used to execute the SQL query. It returns true if it executes the SELECT query. And, it returns false if it executes INSERT or UPDATE query.

d) executeBatch()

This method is used to execute a batch of SQL queries to the Database and if all the queries get executed successfully, it returns an array of update counts. We will use this method to insert/update the bulk of records.

# 5) Retrieve Results
When we execute the queries using the executeQuery() method, the result will be stored in the ResultSet object. The returned ResultSet object will never be null even if there is no matching record in the table. ResultSet object is used to access the data retrieved from the Database.

ResultSet rs 1= statemnt1.executeQuery(QUERY));
We can use the executeQuery() method for the SELECT query. When someone tries to execute the insert/update query, it will throw SQLExecption with the message “executeQuery method can not be used for update”.

A ResultSet object points to the current row in the Resultset. To iterate the data in the ResultSet object, call the next() method in a while loop. If there is no more record to read, it will return FALSE.

ResultSet can also be used to update data in DB. We can get the data from ResultSet using getter methods such as getInt(), getString(), getDate(). We need to pass the column index or column name as the parameter to get the values using Getter methods.

We will get to know more about the ResultSet in the next tutorial.

# 6) Close Connection
Finally, we are done with manipulating data in DB. Now we can close the JDBC connection. We need to make sure that we have closed the resource after we have used it. If we don’t close them properly we may end up out of connections.

When we close the connection object, Statement and ResultSet objects will be closed automatically.

conn.close();
From Java 7 onwards, we can close the JDBC connections automatically using a try-catch block. JDBC connection should be opened in the parenthesis of the try block. Inside the try block, you can do the database connections normally as we do.

Once the execution exits the try block, it will automatically close the connection. In this case, we don’t need to close the connection by calling conn.close method in the Java program.

try(Connection conn = DriverManager.getConnection(url, user, password))
{   
    //database connection and operation
}
# Java JDBC Connection Example
In this example, you will see how to implement the 6 basic steps to connect with database using JDBC in Java program.

Create Table
Before that, first, create one table and add some entries into it.

Below is the SQL query to create a table.

create table employee_details (empNum number(10), lastName varchar(50),
 firstName varchar(50), email varchar(255) , deptNum number(10), salary number(10));
Created the “employee_details” table in Oracle DB.

Create employee_details

Insert Data Into Table
Using the following queries, insert the data into the “employee_details” table.

insert into employee_details values (1001, 'Luther', 'Martin', 'ml@gmail.com', 1, 13000);
insert into employee_details values (1002, 'Murray', 'Keith', 'km@gmail.com', 2, 25000);
insert into employee_details values (1003, 'Branson', 'John', 'jb@gmail.com', 3, 15000);
insert into employee_details values (1004, 'Martin', 'Richard', 'rm@gmail.com', 4, 16000);
insert into employee_details values (1005, 'Hickman', 'David', 'dh@gmail.com', 5, 17000);
