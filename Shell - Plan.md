# Plan to develop a Shell for C# DotNet Exercises.

The plan is to develop a boilerplate **shell** that students can pull down from github to use as a sandbox for some of the Visual Studio-based exercises in Milestone 1 (Foundations - VS, C# & OOP) and Milestone 2 (Databases ++).  

Milestone exercises could then be worked on inside of the shell, with the students able to focus only on the Foundations and Database materials, without having to think about MVC.  This seems important especially for topics that normally require some sort of front end.

Using the shell for a variety of exercises would also help prepare students for taking on Milestone 3 (MVC) since they'd already be familiar with some of how MVC functions, before they start coding one of their own.  

### Some exercises where this would be useful:

##### Exercises that require some kind of a Viewer
* M1 (C#) - Conway's Game of Life.  This exercise needs more scaffolding for most of the students, and some kind of plug-and-play viewer support (whether bounded or boundless) would help many of them.
* M1 (OOP) - Eliza's SharpShapes exercise is a really good OOP exercise, but it requires a Viewer, which she originally designed via WPF.  Since WPF is no longer an active part of the curriculum, it would be good to have one more adaptable to MVC.

##### Exercises that would strongly benefit from a Webpage front-end
* M1 (Working with VS)- Debugging in Visual Studio - clicking on "Run" normally brings up a webpage view. Would be good for students to learn where VS debugging stops and browser inspector debugging starts, before they tackle MVC per se.
* M2 (Databases) - User Management (Authorization / Authentication) - this topic normally relies upon a front end (Register/Login page) to work w/ dotnet framework.

##### Exercises that would strongly benefit from a Webpage front-end
* M3 (MVC) - an elementary M3 exercise could have students pull down a specific object model (template) class, that they then have to write Controllers and Views for.

## Implementation Details
* Presumably the Shell will be implemented in MVC (or possibly Web API?).  
* Each exercise could then also require a particular C# file, and/or particular .css file.
