# Views and Controllers: Set up

Business logic goes in Repository.

## Controllers
* A controller handles the flow of information between front end and back end.
* Each controller method connects a particular request route from a client to a particular response action that the server performs.
* Controller injects data into View.
 * Document types include html, json, soap, xml, csv, pdf.
* Most web pages are dynamically generated these days.
* Helper methods - facilities to help develop views.
* Controllers can be used with template engines in the MVC framework
 * To present (a list of) objects to the View.
* ActionResults of a controller match the View with the same name.
* View Bag - for passing data from controller to View.  Works like a dictionary, not a class or property.  One View Bag is unique for each call to a page.  Can be manipulated inside controller, and/or cshtml.
 * Attribute = <key, value> pair, with no restrictions on it.
   * e.g. Angular's ng-view; Bootstrap and Foundation each have their own attributes.
   * Html built on top of XML - made to be extensible. Can embed additional attributes to any tag created.
   * Even classes can be dynamic: "@class" does not call C# class, but escapes .css class.
 * ViewBag is a dynamic object and therefore has no IntelliSense support - errors will only be discovered at runtime (not during compile)

## Views
* View - named same as controller (again, built into .NET as convention).
* .cshtml - filetype specific to Microsoft's MVC.
  * Supports use of embedded C# inside html-syntax files using Razor syntax.
  * Razor engine then interprets embedded C# into pure html file on the server (before reaching browser).
  * "@" delimits C# code and prefixes C# variables
 * .cshtml files can be shared by multiple views, e.g.
   * _Layout
   * _Partials

* Q: What is the syntax for injecting a View into layout?
* A: "@RenderBody()" helper function ("lazy evaluator") - waits until last minute, when view is thrown at it during rendering of Index.
* Action Links - method calls used to create anchor tags (`<href>`).
 * E.g.
@Html. ActionLink("Home", "Index", "Home"), where:
   *	first "Home" is visible on the page
   *	"Index" is the name of method to be called
   *	second "Home" is prefix of controller.

## Routing
* Convention is `{controllerName}/{action}/{:id}`
* E.g.: Home/User/12   =>   Gets the page of the user with the id of 12

Default MVC "About" page url:  ./Home/About
* The syntax for the url in this case is:
  *	"Home" = prefix of controller class (by convention), via routes
  *	"About" = controller action, an instance method; returns an "Action Result" that refers to the view that will get data injected, as part of .NET's MVC package.  Works as a regular method for testing and utilities.


#### RESTfulAPIs (convention)
* GET Account/User   => returns list of users
* GET Account/User/:id => returns individual id
  * Typical development process is to work on one model at a time.

Bundles - provide additional resources to project
Move NavBar out of shared _Layout, and turn it into a partial.