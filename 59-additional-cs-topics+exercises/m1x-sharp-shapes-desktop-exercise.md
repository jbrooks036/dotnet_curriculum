# Sharp Shapes Exercise (per Eliza)

* https://github.com/elizabrock/SharpShapes

* Shapes:
  * We care about shapes because we want a 90s desktop screen and it’s also a good learning exercise about classes.
  * Shapes have an x number of lines, with area, height, width, and perimeter.
  * We should be able to calculate area and perimeter of circle, ovals, squares, rectangles, triangles and octagon and pentagon.

###### Sonda's Notes on How-To Make Shapes (Exercise) in VS:
  * if you want to make a new Shape, you can right click it to make a constructor
  * if you want to pass in an argument in your method, you can right click first to
  * testm + tab + tab gives you a test method
  Creating Shapes:
  -We made a Class Library as a new project called SharpShapes, and renamed the cs file to “shape.cs”.
  -To add another library, you sometimes will have to not only say you are using this reference at the top, but also add it as a reference manually by checking its box:
  http://blogs.msdn.com/b/csharpfaq/archive/2004/04/29/why-did-i-receive-the-error-the-type-or-namespace-lt-namespace-name-gt-does-not-exist-in-the-class-or-namespace-lt-parent-namespace-gt-are-you-missing-an-assembly-reference.aspx

  Add Tests to Current Project:
  -In your current project > New > Project > In C, Click on Test > Unit Test Project > Rename it to what you want “TestSharpShapes” and under Solutions, Click Add to Solution. Then OK.
  -Under public class test method. To add code snippet. Ctrl + K, Ctrl + X, then scroll to test > Enter > Test Method, enter.
  -To add a solution reference so that we can see colors. Go to References on the right hand side > Add Reference > Solutions > Check the one you want. Then in your code, the one that is supposed to reference it, you can right-click > Resolve > Add the Reference you want and it will add it to your “Usings” at the top.



  Calling Methods:
  -to make methods more efficient, if you are running a method in another method, you should store the output of that method into a locally variable so that you only have to run it once.
