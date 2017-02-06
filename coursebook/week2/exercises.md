# Exercises
These are a set of exercises to learn and consolidate your javascript skills.
They all **MUST** be tackled following a TDD approach.

Form new groups of two people by drawing out a name from the basket.

# url splitting
If you are wondering what is an URL checkout wikipedia [here](https://goo.gl/5EwlvL).

Write a function which takes a URL string and returns an object:

```js
function splitUrl(url) {
  // code here
}

// these are some example of possible ur
var simple = 'https://www.google.com';
var medium = 'https://www.google.com/blog?name=Bes';
var hard = 'https://www.google.com:8080/blog/trend?name=Bes&age=26#modal';
```

The **object** returned should have the following properties:
```js
// for `hard` example
{
  protocol: 'http',
  host: 'google',
  path: '/blog/trend',
  query: {
    name: 'Bes',
    age: 26
  },
  fragment: 'modal'
}
```

# todo
Write a function named `todo`, which behaves as follows:
```js
function todo() {
  // code here
}

var list_work = todo();

list_work.addTask('Study javascript');
list_work.addTask('Go to the shop and buy falafel');
list_work.addTask('Push directly to master');
list_work.addTask('Write tests for todo app');

list_work.showList(); // returns
/**
 * [
 *  {
 *    text: 'Study javascript',
 *    id: 1
 *  },
 *  {
 *    text: 'Go to the shop and buy falafel',
 *    id: 2
 *  },
 *  {
 *    text: 'Push directly to master',
 *    id: 3
 *  },
 *  {
 *    text: 'Push directly to master',
 *    id: 4
 *  }
 * ]
 */

list_work.done(3);
list_work.done(1);

list_work.showList(); // returns
/**
 * [
 *  {
 *    text: 'Go to the shop and buy falafel',
 *    id: 2
 *  },
 *  {
 *    text: 'Push directly to master',
 *    id: 4
 *  }
 * [
 */
```