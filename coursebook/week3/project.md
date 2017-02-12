# Project

Your project this week is to build a simple web app using test driven development
that queries at least two APIs and uses the retrieved data to update the DOM.
What you choose to build with this data and how you choose to display it is up
to you. We suggest you spend any time you have on:

- exploring APIs that you are interested in working with
- coming up with ideas and picking the one you'll work on this week
- deciding what you need to build for your Minimum Viable Product (MVP) and splitting up the tasks

On Thursday we'll have final presentations in the afternoon.

APIs, you are free to use any APIs you would like, but we recommend the following:

- [Guardian](http://open-platform.theguardian.com/)
- [OMDb](http://www.omdbapi.com/)
- [NASA](https://api.nasa.gov/)
- [Star Wars API](https://swapi.co/)
- Google geolocation or maps

**Notes:**

Most APIs provide a HTTP interface, where you query URLs to receive data. Some
provide a javascript library (sometimes called an SDK) that packages up these
requests for you. You are permitted (though not particularly encouraged) to use 
these kinds of APIs.

Some APIs will work fine when queried from local files, but some wont. The reason
for this is not that interesting, but if you find yourself unable to use an API
because you are getting an error that looks like this:

```
Origin null is not allowed by Access-Control-Allow-Origin
```

Then you have two options:
1. Choose a different API to work with
2. Serve your files from a simple HTTP server

To achieve the second option, cd into your project directory and run the following command:

```
$ python -m SimpleHTTPServer 4000
```

This will serve up your directory from `http://localhost:4000`. Mac OSX and Linux
systems will already have python pre-installed. Let one of us know if you have
problems with this option.

**Core features:**

- Use more than one API
- Responsive design
- TDD (Look into stubbing/mocking functions to help test API requests)
- Dynamic content
- A solid README

**Bonus features:**

- Mobile first
- Nice design (CSS!!!)
- Use local storage or session storage

**Keep in mind:**

- Hiding confidential information. When querying APIs with API keys, don't push
  these to Github! (`.gitignore`)

- DOM manipulation is expensive. Think of ways that you can minimise the number
  of DOM insertions in your code.

- Don't repeat yourself. If you catch yourself repeating blocks of code with
  minor variations: stop it and refactor.

- Everyone on the team must write at least one test.