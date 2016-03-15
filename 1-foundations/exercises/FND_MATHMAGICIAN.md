# Mathgician Exercise

Simple fun exercise to develop C# CLI app, w/ input/output
* https://github.com/elizabrock/mathgician

## Mathgician Exercise [from Sonda's notes]
Completed code is @: https://github.com/elizabrock/mathgician
1. Make a whole new C# application. File > New > Project > Choose C# > Pick Console Application.
  * Call it “Mathgician” and it's ok to create a project and make sure git is checked.
2. Make a WriteLine saying Press any key to exit.
3. Then make a Readkey.
  * So now, when it runs, you press a key and it exits.
4. We want it to do math, so write: cw tab tab to make `console.writeline` “I am the MathGician. What shall I math?”
  * The options will be Fibonacci, Primes, or Integers.
5. Then to get the user to choose. `string = desiredMaths = Console.ReadLine ();`
6. `Console.WriteLine(“Ok. I’m gonna do " + Choice);`
  * The vision here is once it tells you what you want, it will spit out the numbers forever until you “ctrl exit”

* First, we have to if they ask for integers,  we do integers. * Otherwise, say “Well Actually …. I lied”
[ See Eliza’s COMMITS.]
* Now we have to populate the if statement to do what we want. We want to print every integer ever.
  * Something like PrintIntegers(), right click on it to go to Generate > Method Stub. This is how to make a static void private method, which it will do down at the bottom.
  * Inside the private method at the bottom, create a while loop with a WriteLine of nextInteger.
    * Now when, you run, and select integers, it should run selecting all the integers in the land.
[ See Eliza’s COMMITS.]

* Now we do the fibonacci sequence, which adds the two after.
  * So create an else if.
  * Within the if statements, make PrintFibonacciSequence(), right click > Generate > Method Stub.
  * Within the private method at the bottom, we’ll make an int variable that is 0 and 1.
  * Do another while true and within it, we first do a write line of the two variables.
  * Then we use three variables to calculate the sequence.
  * We will put a wait since it goes by so quickly with a Thread.Sleep(100). Now it will make a readable sequence in the console.
  * If you want to change the name, right click > Refactor > Rename it and it ok. So that’s how we named prev to current.

* For prime theoretically:
  * Ask whether a variable is divisible by any of these numbers (2, 3, 4, 5, 11, 13).
  * If variable is divisible by {2, 3, 4, 5, 11, 13},  add i to the primes list, and print i
