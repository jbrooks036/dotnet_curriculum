# Object-Relational Mapping

* https://en.wikipedia.org/wiki/Object-relational_mapping

###### Sonda's Notes
* ORM is Object Relational Mapping.
* ORM is the translator mapping between the model and the specific database type so that they are able to talk to each other.
* Object Relational Mapping means that it takes the objects in your code and lines them up with the data you have in your database.
  * A model is simply a class. The attributes you care about are what make the model unique, and you specify these as properties in your class.
* The Entity Framework is a type of ORM and applies the repository pattern to the program.

#### LINQ
* **Dialect** - specific database-specific version of SQL language in order to query the database from your code. The ORM does that for you, so that you don’t have to learn dialects. The ORM automatically figures out what database you are running and then links the commands together.
  * In Microsoft, it’s called LINQ, a query language that provide assemblies to use the .NET framework with SQL databases.
  * You can use LINQ to talk to the ORM which translates the statement so the database can understand what you want it to do.
  * LINQ uses commands very very similar to SQL but not quite (so don’t assume you know what the command does just cause you saw it in SQL) to query your database from your code.
  * The return of a LINQ query is a .NET collection that you can use regular methods on.
