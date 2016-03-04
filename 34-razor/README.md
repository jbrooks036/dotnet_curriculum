# Views and Controllers: Set up

#### Views and Controllers
*	Action Results
*	RESTful APIs
*	Helper Methods
*	UI/UX, Design

### Controllers
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
* `ViewBag` - for passing data (via variables) from Controller to View.  
  * Connects all way from db to views (full stack)
  * Works like a dictionary, not a class or property.  Uses attribute, which isa  <key, value> pair, with no restrictions on it.
   * e.g. Angular's ng-view; Bootstrap and Foundation each have their own attributes.  Html built on top of XML - made to be extensible.
   * Can embed additional attributes to any tag created.
 * One View Bag is unique for each call to a page.  
 * Can be manipulated inside controller, and/or cshtml.
 * ViewBag is a dynamic object and therefore has no IntelliSense support; errors will not be discovered during compile, only at runtime
 * ViewBag - for passing var's around.
"{}"  could be in code, or in html


* Controller will change over time.
  * Business logic belongs in Repository, not Controller.

### Views
* `View` - named same as controller prefix (built into .NET by convention).
* `.cshtml` - filetype specific to Microsoft's MVC framework
  * Supports use of embedded C# inside html-syntax files using Razor syntax.
  * Razor engine then interprets html with embedded C# into pure html file - this happens on the server, before html reaches browser
  * `@` delimits C# code and prefixes C# variables
     * Even classes can be dynamic: `@class` does not call C# class, but escapes .css class.
  * .cshtml files can be shared by multiple views, e.g.
   * `_Layout`
   * `_Partials`
     * "Partial" = view not rendered by Controller, but called by other views
* Q: What is the syntax for injecting a View into layout?
* A: `@RenderBody()` helper function ("lazy evaluator")
    * Waits until last minute, when view is thrown at it during rendering of `Index`.
* `ActionLink` methods - method calls used to create anchor tags (`<href>`).
 * E.g.
@Html.ActionLink("Home", "Index", "Home"), where:
   *	first "Home" is visible on the page
   *	"Index" is the name of method to be called
   *	second "Home" is prefix of controller
* for more info, see: https://msdn.microsoft.com/en-us/library/system.web.mvc.html.linkextensions.actionlink%28v=vs.118%29.aspx

#### Adding Views to Project
* https://github.com/NashvilleSoftwareSchool/jitter-juniper/commit/7f9e28efd5cd6812b85cc95f5d8bdc15d1ee9ad2
* https://gist.github.com/lynnsamuelson/8321571192ea0e3d62a1    [Adding Views on Capstone Project.md]
* Move NavBar out of shared `_Layout`, and turn it into a partial.
* Bundles - provide additional resources to project
* [from Sonda's notes:] You don’t want to put Using statements into the views because the views are supposed to be a dumb kind of thing that just shows things, not handles any logic. That being said, the generated code has a Using in the `_LoginPartial` to show your user email when greeting you.


### Helper Methods
* Facilities to help develop views
* ?? What else to say about Helper Methods??
