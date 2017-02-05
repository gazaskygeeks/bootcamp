## Build a pomodoro timer

*The Pomodoro Technique is a time management method. The technique uses a timer to break down work into intervals, traditionally 25 minutes in length, separated by short breaks.*

![](https://goo.gl/Z4EBDq)

Create a README explaining how to run your new pomodoro timer program and also how to run the tests.
- How to run?
- What?
- Why?
- How?
- Project plan

## Brief
- split into your groups of 4, then pair up within that group (1 pomodoro per pair)
- follow the TDD cycle using ping-pong
- write first all the functionality in JS
- once all the functionality is completed link it to the DOM

It's important to write first the functionality in JS because allows to define
and modularise the interface of the program. By interface we mean a list of
methods that can change/mutate the state of the program. Something like:

```js
function program(initialInput) {
  var store = initialInput;
  // some business logic
  var programInterface = {
    changeStore: function() {
      // change store
      // return something
    },
    doStuff: function() {
      // do something
      // return something
    }
  };

  return programInterface;
}
```

## Specifications
Out of the required specifications write user stories to cover all the functionality:
- set specific countdown (1min, 5min, 10min)
- start the countdown
- get time left
- pause
- unpause
- reset
- show the countdown going down and update

If you find time and want to go behind the basics think of:
- alarm when the countdown is finished
- timer accepts activity text of what is used for
- stop-delete timers and history

## Learning outcomes
By the end of the week project make sure you understand:
- what is TDD
- what is TDD life cycle
- why should you use TDD
- why should you NOT use TDD
- how to set up the environment for testing
- what is the difference between `synchronous` vs `asynchronous` code and how
  to test it
- pair following ping-pong style development

## Learning outcomes
- focus on functionality, TDD and a full set of tests before CSS
- TDD can be painful and slow but it's a key learning objective for this week,
  persevere