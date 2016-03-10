## DotNetKoans Exercise
Walk through exercises re: ALL the intricacies of C# language
* https://github.com/CoryFoy/DotNetKoans
* => Shorten exercise, to some, limited number of Koans assigned
  * e.g. methods, strings, arrays, inheritance?, lambdas?

#### Details from Sonda's Notes
* https://github.com/CoryFoy/DotNetKoans
* Getting C Sharp Koans:
  * Fork the github project from: https://github.com/CoryFoy/DotNetKoans
  * In Visual Studio, at Team Explorer > Click the Plug icon “Connect to Team Projects” > Under local Git Repositories, click Clone > In the box, paste your repo link and hit Clone > It should now have the name on the bottom > Right click and hit Open > Double click on sln to open. if it wants 3.5, go and get it:
http://msdn.microsoft.com/en-us/library/hh506443(v=vs.110).aspx
* Go to `Build > Build Solutions`. It should run without errors in the visual studio console.
* In Command Prompt:
	* `cd Source\Repos\DotNetKoans\AutoKoanRunner`
  * `cd bin\Debug`
	* `dir` (to make sure you're in the directory with AutoKoanRunner.exe)
	* `AutoKoanRunner.exe`
* You can also run the command prompt koan runner straight from File Explorer by going to `Source\Repos\DotNetKoans\AutoKoanRunner\bin\Debug` and click `AutoKoanRunner.exe` after you build it in visual studio.

###### Handy things learned from the DotNetKoans:
* List Manipulation
  * Inserting into the middle of a list:
    * `list array (1,2,3) → list.Insert(2,6) → (1,2,6,3)`
  * Remove first instance of a list:
    * `list array(1,2,3,2) → list.Remove(2) →(1,3,2)`
* Strings:
    * One version of answers:
    https://github.com/SondaSengupta/DotNetKoans/commit/0c38dceed6966f4f29963d64defeea5ceb5be2bd


* Array Assignment:
  * Koan1: `Assert.Equal(typeof(string), name.GetType());`
  * Koan 2: `Assert.Equal(typeof(string[]), names.GetType());`
  * Koan 3a: `Assert.Equal("John", firstName);`
  * Koan 3b: `Assert.Equal("Smith", lastName);`

  * if you are making an array you still have to specify types
    * `var names = new[] { "John", "Smith" };`
       * or you can do:
    *	`string firstName = "John", lastName = "Smith";`

  *  AboutArrays:
    *	Koan 1a: `Assert.Equal(typeof(System.Object[]), empty_array.GetType());`
    *	Koan 1b:  `Assert.Equal(0, empty_array.Length);`
    *	Koan 2a:  `Assert.Equal(42, array[0]);`
    *	Koan 2b:  `Assert.Throws(typeof(System.IndexOutOfRangeException), delegate() ….`
    *	Koan 2c: `Assert.Equal((new int[] { 42, (int)13}), dynamicArray.ToArray());`   
    *	Koan 3a: `Assert.Equal("peanut", array[0]);`
    *	Koan 3b: `Assert.Equal("jelly", array[3]);`
    *	Koan 4a: `Assert.Equal(new string[] { (string)"peanut", (string)"butter" }, array.Take(2).ToArray());`
    *	Koan 4b: `Assert.Equal(new string[] { (string)"butter", (string)"and" }, array.Skip(1).Take(2).ToArray());`
    *	Koan 5a:


*  All the new methods we learned:
    *	`skip()`
    *	`take()`
    *	`slice()`
    *	`push()`
    *	`pop()`
    *	`list` is how you change arrays using `addfirst()`, `removelast()`, `removefirst()`, `addafter()`
    *	a **stack** is a temporary array in which it’s last in, first out
    *	**list** is a temporary array which acts exactly like array


*    AboutNil:
    *	Koan 1: `Assert. False`
    *	Koan 2: `Assert.Throws(typeof(System.NullReferenceException)`
    *	Koan 2b: `Assert.Contains("Object reference not set to an instance of an object", ex.Message);`
    *	Koan 3:  `Assert.True(obj == null);`
    *	Koan 4:  `Assert.Null(obj);`
    *	Koan 5:  `Assert.True(Equals(obj, null));`


*    `try/catch`:
    *	just like `Assert.throws` actually. It tries to do something, and the koan says if there is an exception, it catches it and stores into a variable.


*    `delegate()`:
    *	delegate is like a miniprogram that runs the thing inside of it.
