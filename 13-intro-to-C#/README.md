# Intro to C# Basics - this is all from Sonda's notes - needs to be reviewed/fixed

## Background:

In big languages, they split things to make running it more manageable. This includes
  * core languages (if, else and other keywords)
  * core libraries (string, integers)
  * standard libraries (part of the language but not accessible until you ask for them such as system for CLI, file i/o).
    * standard libraries are not generally included unless asked because they can really slow your system down because there are many of them and they are large.
  * You can also get third-party libraries (eg from github).

## Breaking Down the Boiler Plate and Method Signature:
**namespace** - bundle related-code in a scope that prevents variables from colliding together. When using standard libraries such as System.Threading.Tasks-- it’s three namespaces within each other to access the functions inside.

**class** - classes are kinda like js prototypes, but for now class can be thought of as a topic that defines properties

**method** - every method has a method signature that defines what it is. In JS, it’s usually a function name and the function itself. In strictly defined languages, it is more than that. Every method is public (others can use it) or private (only me), protected, and return type. You have to say what kind of thing each method returns.

 * method signature:	static void Main(string[] args)

  * void is the returnType
  * Main is the name of the method
  * (string[] args) is an argument called “args”  with a type of string that will produce an array []

* Note: you can have the error list tab on the bottom up by going to View > Error List
* The function readkey is that it is blocking, meaning that it is synchronous and won’t let the program go forward until the user presses something.
* Single quotes are for characters. Double quotes are for strings.


### Structure for Desktop Application
-write everything in one language
-front
	-graphical user interface
-apis for drawing such as opengl, winforms, xaml, wpf
-back
	-data persistence in a file, database
	-general business logic or business rules

### CLI
**CLI** are command line interface programs. These are application that have console interaction and business rules behind them to make them work.

### Language Structure of the Web:
#### Front-End:
	-HTML Content
	-CSS for Design
	-Javascript for Interactivity
#### Back-End:
	-Model: Data Persistence
		-File Systems
		-Database (MySQL, Postgres, MongoDB, etc)
	-Routing that communicates between front and back
	-Controllers
	-Views

views, controllers, and routing can all be done with a general purpose language (C#, Ruby, Node.js)


## Classes:
* {get : set} provide the default getter and setter
* virtual means that you are telling the constructor that its methods can be overidden
* base means calling this method from the parent class
  * Dog (properties: Dog(string name)  with methods Bark() string)
  * Chihuahua (properties: Dog(string name) with methods

* **Field** - the element an object uses to keep track of what it knows. An object field defines its state and the information it knows about the object.
* **Class** - what you use to build an object. An object is an instance of its class. Every class gets its own file in Visual Studio.
* **Parameters** - used to pass information in a method
* **Property** - Used to set an attribute on the controls and other classes.
* **Private** vs **Protected** vs **Public**  -   
  * Private means that only that class has access to that field.
  * Protected means that all subclasses of that class (its instances) have access to that field.
  * Public means that anything has access to modify and change it.


**Functional Testing** - testing where you pretend you are the user

## Control Statements:
-* you can skip brackets. you don’t need else statements. But sometimes brackets matter because if you don’t use brackets, it only pays attention to the first statement.
* if you are comparing something, put the value on the left, instead of the right so you aren’t accidentally setting it.
* int? means it can be any integer as well as null. As opposed to just int which can never be null.
* the ?? means that if int x = nullableInt ?? 42, means if null use default value which is 42. The ?? is a null operator that puts in a default fault.
* continue says skips the rest of this loop.
* break breaks you out of the loop


## Extension Methods:
* In Javascript, you can just add a method to a class. But in C sharp, when a class is made, it is closed to methods. So you have to physically add them to extend functionality to the class.
* Typically if you want a library of functionality, you would pay someone money to get that library.
* You can define an extension method by ExtensionName(this Class instance).
  * this refers to the particular instance of that class we’re dealing with.
* You can pass variable amount of arguments with extension methods
  * params means any group of things, pile it into an array and we’ll pass it in.

* anyone can ask for a public methods. Protected methods are for proprietary methods and they don’t want you to access their secret stuff in the code they are accessible to child classes and could be made public.
* Static refers to the class, not the instance.
* Metaprogramming is a class of programming of finding out how something works on a program in order to manipulate it.

## Generics:
* Define a method in which you get a type, and then use that type all over the class because in C sharp, after you make a type, you lock the class to be that type.


## Split using REGEX:
* normally you don’t need regex if you are splitting by one character.
    * For example mystring.Split(,) makes “Please, sir” would be “Please” “ sir” with spaces
* If there are two characters you want to split it with, then you use regex.
  * var regex = new System.text.RegularExpressions.Regex(“, “)
  * so it would be “Please” “sir” without spaces


## Inheritance in C Sharp vs Javascript Prototypes:
* Each class has all the values and methods of the class that is inherited from.
  * Unlike in Javascript, in which if an object doesn’t have that method it would ask its superior, in C Sharp each instance has all the methods and such its parent has and will never ask the parent.
  * It’s like Darwin and passing DNA as opposed to the Chain of Command format of prototypes in Javascript.
