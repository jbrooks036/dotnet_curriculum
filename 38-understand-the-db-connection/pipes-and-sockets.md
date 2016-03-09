
# Pipes and Sockets (all from Sonda's Notes)

* Pipes and sockets = Unix
* lo is loopback interface.
* network address spaces

* For one port and one address, only one connection can be open (multiplexing is outside this topic scope).

* What if there are multiple things on the server that need to talk to itself, how do you allow multiple things to listen to same server and save database and make sure that all these application can talk to this?
  * We then use sockets and named pipes.
  * Sockets are files saved only in memory that point to a reference to the database.
  * It has a prefix called .sock, a location in memory that points to home and it’s a local connection.
    * Thus it bypasses the TCP/IP stack (what you use for internety things on the WWW).
    * Since you know you're receiving and sending to itself, you don’t need that extra packet info.


* For the server, all it knows is to manage the database and is none the wiser as to who is connecting to it. It just knows that it listens for connections. Thus, it also doesn’t know who is connecting to the database.

* That’s where the authentication comes in. So we also need something called “connection strings” that will allow your app to authenticate with the server.
  * Connection strings are defined within your app.
  * Typically, there is a centralized system to handle credentials, in a totally different server than where your database is stored.


* Active Directory(AD), then you have your app (which is a client to the database but a server to your user), your DB on a server.
  * AD doesn’t care where it is located but it checks the credentials and gives the type of authorization is needed for a certain username and password.
  * The AD will then grant a token which authorizes you for an hour to access the database. Usually, the server has this token.


* There is also something called the “web of trust” which  means that if an app has a “secret handshake” and the database has the same “secret handshake” and the intermediaries can verify that it’s all the same, then the app can be trusted.
