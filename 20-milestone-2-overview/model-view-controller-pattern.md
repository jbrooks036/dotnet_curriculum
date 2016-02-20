# Model View Controller Pattern (MVC)

## Overview
MVC, which stands for Model, View, Controller, is an architecture pattern for organizing software applications.  Each component manages a specific purpose, and serves to make your code more organized and modular.  In addition to defining the three components, MVC describes the actual relationship between the components.

## Model

The Model serves as the central component. It's responsible for talking to the database and represents your applications business logic and data. In other words, your model should contain the code that you'd typically find in an object oriented class.

## View

Views are the presentation layer for the MVC pattern.

## Controller
A controller does exactly what its name implies. It serves as the hub of your app, receiving and routing requests between routes, models and views. In a typical request cycle, the controller starts off receiving a request, and routes that request to the appropriate model. The model then talks to the database and sends data back to the controller.  Finally, the controller renders the originally request view with the appropriate data.

## Source / Further Reading

* [Wikipedia] (http://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93controller)
