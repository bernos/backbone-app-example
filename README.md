Introduction
============

This is an example project that shows how to set up a large scale js project
by breaking functionality down into smaller 'apps'. We use the term 'app' here
rather than potentially more appropriate names like 'module' to distinguish our
'app' concept from established javascript 'module' patterns such as AMD. Indeed,
in this example we will make heavy use of the requirejs AMD library.

Each 'app' is a self contained package, that can function in its own right. Apps
generally adhere to the established MVC architecture, though not all apps will
provide their own models, views and controllers.

App are encapsulated in AMD module definitions, and we should need only to 
include a reference to the app's modulename.app.js file in order to access all
the functionality offered by the app.

Apps should implement the popular Facade pattern to expose their APIs. The
piewpiew Backbone Facade library provides a simple implementation of an app
Facade that can be used as-is or extended as needs be.

Apps should communicate between each other only by using a loosely coupled event
model, such as Backbone.Events. This allows for apps to be more easily reused
in other projects, and in a more combinations.

By convention, most projects will contain a 'root' or 'shell' app which is 
responsible for loading all our required apps and wiring everything together.
The root/shell app might provide some project-specific models, views and 
controllers in addition to this.

Wishlist
========

How might we cleanly override templates provided by apps with a project specific
theme? Maybe the i18n plugin for requirejs could help.

How can we 'rebase' routes?