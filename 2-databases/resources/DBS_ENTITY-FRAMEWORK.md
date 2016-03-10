# Entity Framework

* https://msdn.microsoft.com/en-us/data/ee712907

###### N.B. Everything here is from Sonda's Notes, but not in the same order that she had them.  This file probably needs major review / checking / correction.

### Making your Project Entity-Friendly:
* Go the project and right-click to Add > Manage Nuget > Search and install EntityFramework.
* Make a class called ObjectContext.cs within the ProjectName namespace and use the interface DbContext with a semicolon. Make another class called Event.cs
* Add the using System.Data.Entity at the top and Using ProjectName
* Within ObjectContext.cs add the property DBSet and make it public, that allows you to pull a set of entities from the database. In SQL, there are the same as query sets.
* Within the Object.cs add a field ObjectID which is an observable collection that represents the actually data(??)
* Right-Click Data Connection from Server Explorer. Now add a Connection > Server Name .\SQLEXPRESS > Under "Connect to database" add ProjectName.ObjectContext. You can test it and then add it. It should populate in Server Explorer with tables, views, etc.
* Technically, the connection belongs in the Object class, but we’ll move it to the mainwindow.cs because it’s where the program begins. So we’ll move the observable collection line here. So when the window starts up, it makes a new instance of the Objects collection.

### Connecting all the things
##### Connections
* there are already connections that are in place between your program and your database. There is already a pool of connections in place where depending upon the operation, any call to pool data, and will use the connection to talk to the database.
* In the code, it will specify preregistered pathways that can be used and then you can use those connections over and over again, so the wait time is not as long for the O\RM

###### So how does this look?
* In our program, manage nuget package manager > Search EntityFramework > Install EntityFramework.
* Accept Terms. Now it should be added to the references.
* Add reference has a using in your program.
* Then add another class with DbContext as an addition using a semicolon (ex: `public class ShapesContext : DbContext`).
  * You can use DbSet to link up the database with the class.
* Then within your main, you must make a new instance of your database (new ShapeContext ()).
* Make a new rectangle. Use .Add to prep what you want into the databases and then .SaveChanges to actually add them to database.

##### Closing Connections
* When you close a program, you must close the connection as well.
  * Otherwise, they stay persistently open and you will have a zombie database that will be kept alive even though you are not using the database for anything. The connection will stay open eating up space and memory.
* When you’re done, close your database connection with something like db.Close().
* But programmers are awfully forgetful people, so they made something called a using to close the connection for you. You wrap all your database connection code within a using(). When that reaches the end of the code block, then it closes itself.

##### How do I write a unit test to see whether the connection to database is working?
* Make a TestPersistance.cs in your project.
* Go back and add (or prep) a line to the database using db.Add in the MainWindow.cs.
* This is a Code First technique where we first write the code to make .NET generate the database for us.

### Misc Other Notes?
* In reality, the mainwindow should not care about data events. There should be a class for business logic (our main window) and interacting with the queries of the database (DAL such as LINQ or queries or accessing the data). So we should have a level of abstraction that decouples the two, so we have a repository in the middle.
* Lazy Evaluation - allow the platform underneath you to control data access for you. For example, the LINQ query is not evaluated until the foreach gets evaluated. So you can make as many queries as you want and then evaluate them.
* We make a repository to handle the LINQ logic, and one popular pattern is to generalize it such that your tests are actually querying a list and the list happens to have plugins to access your database. In this way, you make an interface such that you can use a different database type if you wish later, and the rest of the program does not have to worry about what that is because the interface ensures that the data and its methods get handled the same way no matter what data type it is throughout your whole program.
* So you can create an interface such as IObjectRepository.cs within a new folder called Repository. In this interface, you must add the names for the methods that you want used for any class that is using this interface such as Add, Delete, etc.
* Next we can create an ObjectRepository.cs class and use interface as semicolon. If you click on option > Implement Interface, then it will repopulate the page with all those empty methods that the interface requires.
* If you want something back that you can do stuff with, you will use IQueryable to query the data
* A **predicate** is a statement that filters your queryable. It’s a collection that you can run a query through.
* Now with an interface and ObjectRepository.cs class in place, you can make a ObjectRepositoryTest.cs to test these methods that are in your ObjectRepository.cs class. The first things you can do in the class is implement a constructor to open your database
* **##CSharp** is the IRC Channel where all the C sharp nerds hang out.
* `DataContext db = new DataContext(@"c:\Northwnd.mdf");`
