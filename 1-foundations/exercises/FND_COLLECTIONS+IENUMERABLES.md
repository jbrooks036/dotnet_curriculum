# Potential Exercise Scoping for C# Foundation: Collections and IEnumerables

One aspect of C# that students often struggle with during capstone development relates to all the variations of Lists, Collections and IEnumerables, and when to use which one.  They are covered in a peremptory fashion in later koans, but that's not the same as learning how to use them in a large app.

Typically, some version of IEnumerable is returned from the repository in a list or collection form.  Choosing "which of these to use when" is the biggest stumbling block - it may seem simple when first setting up the repo and accessing it, but then when those results are getting passed around to other methods, unanticipated problems can arise.

What would be helpful would be an exercise for students to get reasonably accustomed to working with the different versions of Collections and IEnumerable - what each can and cannot do on their own - before getting mired knee-deep in capstone dependencies, that then are hard to disentangle all the way through.
* e.g. I ran into problems when these issues intersected with dotnet's built-in user management and identity/account classes.

### Useful Websites:
* https://msdn.microsoft.com/en-us/library/9eekhta0(v=vs.110).aspx
* https://msdn.microsoft.com/en-us/library/7y3x785f(v=vs.110).aspx
* http://stackoverflow.com/questions/10113244/why-use-icollection-and-not-ienumerable-or-listt-on-many-many-one-many-relatio
