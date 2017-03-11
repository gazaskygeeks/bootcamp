## Build web apps using frameworks

This week you will be introduced to a Node framework, called *hapi.js* and to a
JavaScript templating engine, called *Handlebars.js*. You will then write your
own hapi server and build a blog site using a PostgreSQL database and server-side
template rendering.

As this is the first week when you are introduced to a framework, it's worth
saying a few words about abstractions, libraries and frameworks before diving
into hapi.js.

### Intro to abstractions/libraries/frameworks
Abstraction is a key concept in computer science and can be described as:
> a manner in which a person interacts with a program or system without directly
working with more complex details "under the hood". Complex details that may not
be of interest are abstracted away so that the programmer works with only what
is necessary to him.
-[CS50 wiki](http://cs50.wiki/Abstraction)

There are different levels of abstraction that make it easier for the programmer
to interact with the language, e.g. use function calls without needing to know
what exactly happens when the function is called.

Examples of different levels of abstraction are the *low-level languages* (closer
to the machine language) and *high-level languages* (closer to the human language).

Libraries and frameworks are built on the idea of abstraction.

## What is a library?
A library is a collection of prewritten code bundled together to provide
functionality for a specific area. We can incorporate libraries into our projects
to make use of already available code and be more efficient.

#### What is a framework?
A framework is a more complex level of abstraction that may include libraries,
a compiler and other programs used in the software development process. As the
name suggests, a framework serves as a foundation on which we can build programs
and applications.

## What is hapi.js?

hapi.js is an open-source framework that provides us with different objects and
methods for abstracting HTTP and importantly gives us the ability to easily build
in other capabilities using plugins. Hapi has a powerful plugin system, that
allows us to use smaller, independent modules (i.e. plugins) by registering them
directly into the instance of the server we are working on.

> hapi is a simple to use configuration-centric framework with built-in support
for input validation, caching, authentication, and other essential facilities
for building web and services applications. hapi enables developers to focus on
writing reusable application logic in a highly modular and prescriptive approach.  
-[hapi.js repo on GitHub](https://github.com/hapijs/hapi)

## What is Handlebars.js?

Handlebars.js is one of the most popular JavaScript templating engines that builds
on top of the Mustache templating engine. A template engine is basically software
that is designed to combine templates with data in order to generate HTML.
Handlebars can be used for both client-side and server-side rendering.

Handlebars templates are reusable and look like regular HTML with embedded
placeholders that can "hold" data. It is generally good practice to separate the
view (presentation/ aesthetics) and the model (actual data), as this encourages
clean code organisation.

hapi has extensive support for template rendering and can load and leverage Handlebars.js
with the full use of layouts (i.e. templates), partials (smaller templates within
templates) and helpers (functions used in templates to manipulate data) to
ultimately render views.

### Week structure

#### Sunday
- 9:00 - 13:00 - [Make me Hapi workshop](https://github.com/hapijs/makemehapi)
- LUNCH -
- 14:00 - 17:00 - [Make me Hapi workshop](https://github.com/hapijs/makemehapi)

#### Monday
- 09:00 - 09:30 - Introduce [research topics](./research.md)
- 09:30 - 13:00 - Research
- LUNCH -
- 14:00 - 16:00 - Research
- 16:00 - 16:30 - Review and present research topics
- 16:30 - 17:00 - Introduce [project](./project.md)

#### Tuesday
- 09:00 - 10:00 - Planning projects
- 11:00 - 13:00 - Projects
- LUNCH -
- 14:00 - 17:00 - Projects

#### Wednesday
- 09:00 - 13:00 - Projects
- LUNCH -
- 14:00 - 17:00 - Projects

#### Thursday
- 09:00 - 11:00 - Code review
- 11:00 - 12:45 - Respond to issues
- 12:45 - 13:00 - Plan presentations
- LUNCH -
- 14:00 - 15:00 - Presentations
- 15:00 - 16:00 - Stop-Go-Continue
