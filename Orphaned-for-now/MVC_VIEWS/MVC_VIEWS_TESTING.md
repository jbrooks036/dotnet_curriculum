# Tests [from Sonda's Notes]

http://www.teststack.net/

* BDDfy Documentation: http://bddfy.teststack.net/

* BDD Story Keywords:
  * Given - the state of the system before user does anything
  *	Given That… - a statement about the state of the system and the behavior of that program at that moment, before the user performs an action.
    * Example: Given that the login works, as a paid user in order to see his transaction will be taken to the landing page.
* When - the action the user is taking
* Then - stating what you expect to happen
* And then - additional things you also expect to happen.


* Implementing Tests:
  1. Clone the Repo
  2. Tools > NuGet Package Manager Console > The Package Manager Console should pop up. 3. Install-Package TestStack.White. Depending upon when you cloned this repo, you may already have it installed.
  3. Right click TestProjectName > Manage NuGet Packages > Online > Click on TestStack White to Install (to actually install) and install TestStack.BDDfy


* These tests allow you to simulate the events programmatically so teststack.white allows you to do that.
  1. Add these using to your UITest.cs such as TestStack.White; Test.Stack.Factory; TestStack.WhiteUIItem; TestStack.White.UIItems.WindowsItems; System.IO;
  2. Add your project as a reference through right-clicking the test project > Add Reference > Solution > Add your project.
  3. You need to initialize the boilerplate by adding  [ClassInitialize] with a method inside to find the file path of the test, launch it, and connect it to the MainWindow’s title.
  4. Now you can write your tests
  5. You also need a  [TestMethod]
```
          public void ExecuteStoryTest()
          {
              this.BDDfy();
          }
```
  so that the BDDfy will run in the file that is going through your user stories.

* After all the tests there is a [ClassCleanup] that is a method that wipes the project issues from memory back to its original settings and to also close the application
* The test will only order AndThen chronologically by how you write them. But it will always order “Given” first, then the AndThens. It follows the keywords given by a story.

* 5Nines - this has to do with the percentage of uptime you have in the form of 99.999%. Meaning you are down for about 5 minutes a year, which is nigh impossible and you should quit if your manager tells you optimize such. Sometimes, your site will go down because of who you are using, such as AWS having downtime or utility to your fiber cables, etc. Much more doable to doable if you say you’ll have half an hour of downtime each quarter or maybe 1Nine.

* Requirements
  * MUST - same as REQUIRED or SHALL, meaning that the definition is an absolute requirement.
  * SHOULD - same as RECOMMENDED meaning that there may be valid reasons as to why they are not implemented in certain circumstances.

* As a user type, in order to accomplish goal, I want to perform x task.

* Cucumber
  * https://cucumber.io/
  * a BDD testing environment where you make plain text file with user stories, called cukes. Then write the definition in Ruby[?], and run and fix and pass it until the test is “green like a cuke”.
