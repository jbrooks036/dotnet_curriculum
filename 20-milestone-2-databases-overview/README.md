# Introduction to Databases

* https://en.wikipedia.org/wiki/Database
###### Sonda's Notes:  What is a database?
A database is a data store. Databases logically organize data into an abstraction of real-world concepts.
Database is often abbreviated to DB.

### ACID Model
* http://databases.about.com/od/specificproducts/a/acid.htm

"In computer science, ACID (Atomicity, Consistency, Isolation, Durability) is a set of properties that guarantee that database transactions are processed reliably. In the context of databases, a single logical operation on the data is called a transaction. For example, a transfer of funds from one bank account to another, even involving multiple changes such as debiting one account and crediting another, is a single transaction." [Wikipedia]


###### Sonda's Notes on DBs
* A DBMS is a database management system.
* Databases and database management systems are different concepts.
   * The database is the data and the metadata (for example, indexes) about that data.
   * The database management system is the software used to access and manipulate the data stored in the database.
* Accessing and manipulating the data in the DB is typically referred to as the CRUD operations (Create, Read, Update, Delete).
*  How to view your Table in your Database:
  * Open Server Explorer > Click on your Database Connection > Tables > Right Click on ObjectName > Show Table Data
*  To Delete your Database (in case you’re having connection errors):
  * Open Microsoft SQL Server Management
  * Click OK if that’s the Server you’re working with
  * Click Database > Your Database > Right Click > Delete > Make sure close connection is checked.
* To Make a New Connection:
  * Right-Click Data Connection from Server Explorer.
  * Now add a Connection > Server Name .\SQLEXPRESS > Under Connect to database add ProjectName.ObjectContext (Or whatever your project name.ObjectContext).
  * You can test it and then add it.
  * It should populate in Server Explorer with tables, views, etc.
* To Make a New Database First, then create a Connection:
  * Right-Click Data Connection from Server Explorer.
  * Now Create New SQL Server > Server Name .\SQLEXPRESS > Under Connect to database add ProjectName.ObjectContext.
  * You can test it and then add it.
  * It should populate in Server Explorer with tables, views, etc.
* Add Connection makes a connection and then new Object.Context, realizes there is not a database yet, and then makes a database.
* Create SQL DB - creates a new database first, thus the database is empty for while, and then the code runs to add/delete/and such.





### Outline of Databases Topics (per Eliza?)
*	Intro to Databases
*	ACID
*	Entity-Relation Diagrams
*	Intro to SQL
*	Creating Databases
*	Table definitions
*	Constraints
*	Indexing
*	Transactions
*	Locks
*	Normalization
*	Joins
*	Projects
*	Overview of:
  * Sprocs
  * Views
  * Query Optimization

### Jurnell may have materials for teaching:
  * Basics of Databases/Modeling
  * Learning SQL
