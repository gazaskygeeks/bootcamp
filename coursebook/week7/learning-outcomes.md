## Learning outcomes

#### hapi server basics
- Understand what hapi.js is
- Learn how to set up a hapi server
- Learn how to define routes using `server.route([...])`
- Understand how to get data out of the request parameters and payload
- Learn how to set up a route with a dynamic url using *wildcard* parameters
- Learn how to register plugins using the `server.register([...], cb)` method
- Learn how to serve static files using the `Inert` plugin

#### Serving files using hapi and Handlebars
- Be introduced to the MVC (Model - View - Controller) model
- Learn how to serve dynamic files using Handlebars.js templates and hapi's
  `Vision` plugin
- Learn how to use Handlebars views, layouts and partials
- Be introduced to Handlebars helpers

#### More Hapi plugins and testing
- Learn how to validate user's input using the `Joi` plugin
- Learn how session management works using cookies
- Learn how to set up a basic user login with the `Hapi Auth Basic` and `Hapi
  Auth Cookie` plugins
- Understand how to do hapi testing to make fake requests using `server.inject()`
  (i.e. call a registered route on the server without requiring the server to be
  listening on open ports)

#### Revision questions
- What is hapi.js?
- How do you set up a hapi server that listens to different endpoints?
- What is Handlebars.js?
- How do you serve static and dynamic files on a hapi server?
- How do you test a hapi server using `server.inject()`?
- How do you set up a basic user login using cookies?
