# Relational Databases

###### Everything here is from Sonda's notes

#### Document Oriented vs Relational Database
  * **Relational database**
    * Stored very similar to how data is stored in, say, excel.  
    * In tables or a grid that relate to other tables or grids.  
    * Instead of storing all the data in one place, you split it up.  For instance:    
      * Book grid with title / author / year stored in the table.  
      * Another grid with book #, chapter, and chapter text stored there.
  * **Document Oriented**
    * Like a json blob.  
    * In document oriented, there is no schema.

  * **Eliza says**
    * At least 95% of the time, you want a relational database.  But in the modern age, you don’t have to choose between one or the other.  Things like Postgres allow for storing document oriented stuff in a relational database.  We will be focusing on relational databases.
    * We have currently been thinking about storing data in a document oriented way (think JSON).  We will be moving towards Tables as the overriding metaphor, as stored data will be kept in a tabular way (or at least mimic this structure).

#### Types of Relational Databases:
  * **MySQL** → loose on rules
  * **Postgres** → strict
  * **MS SQ**L → proprietary
  * **Sqlite** → light weight
  * **Oracle** → wrote their own spec

#### Tables, Rows and Columns
* A database with one table is not very useful.  What we end up doing in databases is having multiple tables that often relate to each other in some way.
* Each database consists of N number of tables.  
* Each row in a table can be referred to as a “tuple”, or just a row of data if you prefer.  
* Columns have…
	 * name (i.e. id, title)
	 * type (i.e. integer, varchar)
	 * constraints (i.e. NOT NULL, UNIQUE, etc)
	* Typically in databases we almost always have an ID column, and they are typically sequential.

#### Talking to a Database
 * Basic Structure of a SQL statement:
	`SELECT ______   
	FROM ______
	JOIN ______ ON ______
	WHERE ______`

* Example:  `SELECT * FROM employees WHERE name LIKE ‘b%’`
   * LIKE means “matches a pattern” and % means “starts with” (wildcard).

* Example 2: `SELECT products.id, products.name FROM order_details JOIN products ON  order_details.product_id = products.id WHERE order_details.order_id = 10250`

###### How to: Insert Rows Into the Database
  * https://msdn.microsoft.com/en-us/library/bb386941%28v=vs.110%29.aspx

###### Joins
* http://blog.codinghorror.com/a-visual-explanation-of-sql-joins/
* With a join, you must specify how the table is joined using ON. Otherwise, you will get all the combinations possible of one table row matched with another table row.
  * **Inner Join** matches one table with another table row for row. If one row doesn’t have its pair on another table, it will be excluded. It will only show matching row pairs.
  * **Outer Join** matches two tables row for row but includes rows that are not paired up, aka rows that have a pair with a null in the other table.

#### Other Resources
* Eliza’s SQL homework with answers: https://gist.github.com/elizabrock/30b62c90a1ccfadbbdfe
