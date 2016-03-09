# Controllers
* A controller handles the flow of information between front end and back end.
* Controller will change over time.
  * Business logic belongs in Repository, not Controller.
* The name of each controller ends in "...Controller", and inherits from .NET `System.Web.Mvc.Controller` class.
* Each controller method connects a particular request route from a client to a particular response action that the server performs.


* Most web pages are dynamically generated these days.
 * Each controller injects data into a corresponding `View`.
 * Document types include html, json, soap, xml, csv, pdf.


 * `ActionResults` of a controller match the View with the same name.

* `ViewBag` - for passing data (via variables) from Controller to View.  
  * Connects all way from db to views (full stack)
  * Works like a dictionary, not a class or property.  Uses attribute, which is a  <key, value> pair, with no restrictions on it.
   * e.g. Angular's ng-view; Bootstrap and Foundation each have their own attributes.  Html built on top of XML - made to be extensible.
   * Can embed additional attributes to any tag created.
 * One View Bag is unique for each call to a page.  
 * Can be manipulated inside controller, and/or cshtml.
 * ViewBag is a dynamic object and therefore has no IntelliSense support; errors will not be discovered during compile, only at runtime
 * ViewBag - for passing var's around.
"{}"  could be in code, or in html


* Controllers can also be used with template engines in the MVC framework to present (a list of) objects to the View.
