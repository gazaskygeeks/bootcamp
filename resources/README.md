## Resources

# How to set up codeclimate test coverage

* Check out the link to the documentation.
https://docs.codeclimate.com/docs/setting-up-test-coverage

* Go to test coverage troubleshoot.
* got JavaScript link.
* Generate coverage data in Lcov format
* Install codeclimate-test-reporter's NPM package
* Specifying your repo token as an environment variable,
send lcov coverage data to the codeclimate-test-reporter npm script.

```js
CODECLIMATE_REPO_TOKEN= < > ./node_modules/.bin/codeclimate-test-reporter < ./coverage/lcov.info
```

### It should work now!

#### Also make sure to add all the CI the badges.

### Talks

This is a list of useful resources in form of talks, libraries and articles.

- [Simplicity Matters by Rich Hickey.](https://youtu.be/rI8tNMsozo0) About the
  importance of writing **simple** understandable software, which is different
  from **easy**.

- [Programming Style & Brain by Douglas Crockford.](https://youtu.be/_EANG8ZZbRs)
  A must to understand best practices about Javascript.

- [The Myth of the Genius Programmer by Google.](https://youtu.be/0SARbwvhupQ)

### Blogs

- [antirez:](http://antirez.com) main contributor of [Redis](https://redis.io/),
  Italian developer living in the beautiful Sicily.


### YouTube channels

- [Computerphile:](https://www.youtube.com/channel/UC9-y-6csu5WGm29I7JiwpnA)
