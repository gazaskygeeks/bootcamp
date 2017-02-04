## Sunday

```js
/**
 * Write a function `test` which takes two arguments.
 * The first argument is a `string` while the second is a `function`.
 * Every time the function `test` executes it should log the text in
 * the first argument and also check if the two arguments of `t` are equal.
 * If the two arguments of `t` are equal should print `OK:<message text>`.
 */

function test (message,callbackFun) {
  // code here
}

test('First',function(t) {
  t.equal(1,1,'one is equal to one');
});

test('Second', function(t) {
  t.equal(2,3,'two is equal to two');
});

test('Third', function(t) {
  t.equal(3,3,'three is equal to three');
});
```

When run the code should produce this output.

![repl](https://git.io/vDcYn)

**Please** don't look around the internet, will not help you much, even if you
find the solution. Note how the second argument of the `test` function is **another function**.

Let's have a look at the first example. At runtime the arguments of `test` are:

```js
message = 'First'

// while

callbackFun = function (t) {
  t.equal(1,1,'one is equal to one');
}
```

To complete the requirements you need to log `message` and to evaluate and log
what's in the body of `callbackFun`. How can you do that? By calling `callbackFun`
itself! Note however that you have to pass one argument (`t`) to `callbackFun`.

Good luck, and see you in one hour class! :)