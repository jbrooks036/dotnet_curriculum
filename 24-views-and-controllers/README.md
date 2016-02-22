# Views and Controllers: Set up

### Views and Controllers
*	Action Results
*	RESTful APIs
*	Helper Methods
*	UI/UX, Design

Business logic goes in Repository.

## Controllers
* A controller handles the flow of information between front end and back end.
* The name of each controller ends in "...Controller", and inherits from .NET `System.Web.Mvc.Controller` class.
* Each controller method connects a particular request route from a client to a particular response action that the server performs.
 * Most web pages are dynamically generated these days.
* Each controller injects data into a corresponding `View`.
 * Document types include html, json, soap, xml, csv, pdf.
* "Helper methods" - facilities to help develop Views.
* Controllers can also be used with template engines in the MVC framework
 * to present (a list of) objects to the View.
* `ActionResults` of a controller match the View with the same name.
* `ViewBag` - for passing data from controller to View.  Works like a dictionary, not a class or property.  One View Bag is unique for each call to a page.  Can be manipulated inside controller, and/or cshtml.
 * Attribute = <key, value> pair, with no restrictions on it.
   * e.g. Angular's ng-view; Bootstrap and Foundation each have their own attributes.
   * Html built on top of XML - made to be extensible. Can embed additional attributes to any tag created.
   * Even classes can be dynamic: `@class` does not call C# class, but escapes .css class.
 * n.b. ViewBag is a dynamic object and therefore has no IntelliSense support; errors will not be discovered during compile, only at runtime

## Views
* `View` - named same as controller prefix (built into .NET by convention).
* `.cshtml` - filetype specific to Microsoft's MVC.
  * Supports use of embedded C# inside html-syntax files using Razor syntax.
  * Razor engine then interprets embedded C# into pure html file on the server (before reaching browser).
  * `@` delimits C# code and prefixes C# variables
 * .cshtml files can be shared by multiple views, e.g.
   * `_Layout`
   * `_Partials`
* Q: What is the syntax for injecting a View into layout?
* A: `@RenderBody()` helper function ("lazy evaluator")
    * Waits until last minute, when view is thrown at it during rendering of `Index`.
* ActionLink methods - method calls used to create anchor tags (`<href>`).
 * E.g.
@Html.ActionLink("Home", "Index", "Home"), where:
   *	first "Home" is visible on the page
   *	"Index" is the name of method to be called
   *	second "Home" is prefix of controller.
* for more info, see: https://msdn.microsoft.com/en-us/library/system.web.mvc.html.linkextensions.actionlink%28v=vs.118%29.aspx

## Adding Views to Project
* https://github.com/NashvilleSoftwareSchool/jitter-juniper/commit/7f9e28efd5cd6812b85cc95f5d8bdc15d1ee9ad2
* https://gist.github.com/lynnsamuelson/8321571192ea0e3d62a1    [Adding Views on Capstone Project.md]

## Routing
* Convention is `{controllerName}/{action}/{:id}`
* E.g.: Home/User/12   =>   Gets the page of the user with the id of 12

Default MVC "About" page url:  ./Home/About
* The syntax for the url in this case is:
  *	"Home" = prefix of controller class (by convention), via routes
  *	"About" = controller action, an instance method; returns an "Action Result" that refers to the view that will get data injected, as part of .NET's MVC package.  Works as a regular method for testing and utilities.

#### RESTful APIs (convention)
* GET Account/User   => returns list of users
* GET Account/User/:id => returns individual id
  * Typical development process is to work on one model at a time.

Bundles - provide additional resources to project
Move NavBar out of shared `_Layout`, and turn it into a partial.
