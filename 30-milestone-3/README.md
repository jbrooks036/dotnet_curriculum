## Milestone 3:  Building an API
#### Topics (to be fleshed out over time)
* Web API
* Routing


###### Sonda's Notes re: APIs in .NET:
* With APIs, there is the browser or something like it on one side of the internet. On the other side, you have the back-end where you have your database and your application logic and they only communicate with the user and the browser world through API (the interface).
* There is a push towards API development where you have a backend app and the browser shows it through the API.
* Different meanings of API - API actually has two meanings.
  * One means that there is the front end and back end parts and this is the interface by which they talk to each other.
  * When the web got bigger, then API meant how to use the data from another web service data.
* Quick REST recap
    * REST is a convention for building API’s and interacting with them.  
    * If you build APIs RESTful, there is a standard format/protocol that people will know how to interact with when using your API.
    * The web is built on the HTTP protocol.  Each message we send with HTTP has a couple of parts.
  	  * Headers
        * → request method (the verbs, the how, ex: HEAD/PATCH/GET/POST/PUT/DELETE)
  		  * → referrer
  		  * → requested uri (universal resource identifier, the nouns)
  	  * Body
  		...?
    * All this ties into MVC.

* The important bit is when we’re building our own API’s, we will be connecting these REST concepts with the MVC concepts.  There is almost always a 1 to 1 correspondence between our controllers and our models.  Using an airport as an example, three example controllers are:
  	GateController → Connects to the Gate model (which talks to the DB)
  	RunwayController → Connects to the Runway model (which talks to the DB)
  	PlaneController  → Connects to the Plane model (which talks to the DB)


#### Exercises
* ???

#### Group Project
???
