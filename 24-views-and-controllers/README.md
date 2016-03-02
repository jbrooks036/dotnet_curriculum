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

### Routing
* Routing in MVC by default follows this setup which is run when the app starts up:
```
public static void RegisterRoutes(RouteCollection routes)  
{
    routes.MapRoute(
        name: "Default",
        url: "{controller}/{action}/{id}",
        defaults: new { controller = "Home", action = "Index", id = UrlParameter.Optional }
    );
}
```
* We see here that the convention is `{controller}/{action}/{id}` (N.B. in the code configuration above, that the `id` parameter is optional). This allows a developer to create semantic and abstract urls rather than associate urls with a specific file. The end goal is to have readable and intuitive urls rather than `http://about.exofly.com/my_site?f=2enr93hv98&collect=true&blahblah=blarghdiblargh`
* Contrast an unintuitive url with these `{controller}/{action}/{id}`-patterned examples:
  * `Users/Create/`      (remember an `id` is optional)
  * `Shipments/Edit/231`
  * `Pets/Search/1`
  * `Project/Destroy/2`
* The **{action}** parameter of a route corresponds with a specific method on an MVC controller
  * Example:
    * Default MVC "About" page url:  `./Home/About` where url syntax is:
      *	"Home" = prefix of controller class (by convention), via routes
      *	"About" = controller action, an instance method; returns an "Action Result" that refers to the view that will get data injected, as part of .NET's MVC package.  
      * Works as a regular method for testing and utilities.

#### RESTful APIs (convention)
* **REST** (REpresentational State Transfer) is another set of guidelines outlining how resource endpoints are defined and behaved
* When writing a .NET Web API resource, the style of REST can help keep your controller methods focused and organized
* The typical development process is to work on one model at a time.
* In contrast to MVC routing (which allows you to dictate your own action verbs), a RESTful resource performs actions based on the combination of the url and the HTTP request's method (or "verb")
* Most often used HTTP request methods:
  * **GET**
  * **POST**
  * **PUT**
  * **DELETE**
* For any given resource (or model name), the convention for crud operations is as follows:

  | Method  | Url      | Action performed |
  | ------- | -------- | ----------------------------- |
  | GET     | Users/   | Returns a list of all users   |
  | GET     | Users/1  | Returns user with id of 1     |
  | POST    | Users/   | Creates/adds a user to set of all users |
  | PUT     | Users/1  | Updates info stored about user with id of 1 |
  | DELETE  | Users/1  | Deletes user with id of 1 |

* RESTful urls can also reflect relationships between entities. For example, say we want to find out the assignments a particular student has. An example of a RESTful url would be:
  * (GET) students/43/assignments

* Retrieving an individual assignment of that user could be:
  * (GET) students/43/assignments/2   

#### If using third party API
* Need to enable CORS on MVC App, to access `www.<Company1Name>.com` from `api.<Company2Name>.com`
