# Coding Challenges

# 01


 * Let's learn method chaining!
 * Write a function `start` which takes
 * as input a number.
 * Calling the method `.add` on the result
 * of start will add a specific number.
 *
 * var res = start(5).add(2).add(3);
 * console.log(res); // 10
 *
 * Good luck!
**/
```js
function start (num) {
  // code here
}
```

## Solution
```js
function start(num){
            var store=num;
            var obj={
              add:function(num1){
                store = store + num1;
                return obj;
              },
              result : function(){
                return store;
              }
            }
            return obj;
          }
            var res = start(5).add(2).add(3).add(20).result();
             console.log("res "+res);
             ```

-----------

# 02

 * Let's build a template engine.
 * Write a function `block` which takes
 * as input a template string e.g. `<p>{{text}}</p>`
 * Returns something, with a method `.render`
 * which takes as input an object e.g. `{text:'Hello'}
 * and returns the final string e.g. `<p>Hello</p>`.


```js
function block (/* args */) {
  // code here
}

var template =
   '<div class="container">'
 +   '<h1 class="title">{{content}}</h1>'
 + '</div>'
 + '<div class="body">'
 +   '<p>{{myText}}</p>'
 + '</div>';

block(template).render({
  content: 'Hello GSG',
  myText: 'We are developers'
});

```

  Result should be:
```js
<div class="container">
  <h1 class="title">Hello GSG</h1>
</div>
<div class="body">
  <p>We are developers</p>
</div>
```

## Solution

```js
var TemplateEngine = function(tpl, data) {
Object.keys(data).forEach(function(key){
  console.log(key);
  tpl = tpl.replace("{{"+key+"}}", data[key])
})
  return tpl;
}
var template =
 '<div class="container">'
+   '<h1 class="title">{{content}}</h1>'
+ '</div>'
+ '<div class="body">'
+   '<p>{{myText}}</p>'
+ '</div>';

TemplateEngine(template, {
content: 'Hello GSG',
myText: 'We are developers'
});
```
---------

# 03

 * Let's build JQuery.
 * Create a function `$` which takes as input a
 * query selector e.g. `$('.className') or $('#id')`.
 * The result of `$()` can be chained with different
 * methods:
 *  - $(selector).toggleClass('.info');
 *  - $(selector).height(200).width(200).backgroundColor('red');

```js
function $ (selector) {
  // code here
}
```

## Solution

```js
function change(selector){
 console.log("test",selector);
 var div1 = document.querySelector(selector);
 console.log("div1",div1);
   var obj = {
     height:function(height){
       div1.style.height = height;
       return obj;
     },
     width: function(width){
       div1.style.width = width;
       return obj;
     },
     backgroundColor:function(color){
       div1.style.backgroundColor = color;
       return obj;
     }
   }
   return obj;
 }
change('div').height('200px').width('200px').backgroundColor('BLACK');
```
------------

# 04


 * Write a function `test` which takes two arguments.
 * The first argument is a `string` while the second is a `function`.
 * Every time the function `test` executes it should log the text in
 * the first argument and also check if the two arguments of `t` are equal.
 * If the two arguments of `t` are equal should print `OK:<message text>`.


```js
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

![alt text](https://raw.githubusercontent.com/besarthoxhaj/breakfast/master/_assets/repl_logs_tape.png)

Please don't look around the internet, will not help you much, even if you find the solution. Note how the second argument of the test function is another function.

Let's have a look at the first example. At runtime the arguments of test are:

message = 'First'

// while

```js
callbackFun = function (t) {
  t.equal(1,1,'one is equal to one');
}
```
to complete the requirements you need to log message and to evaluate and log what's in the body of callbackFun. How can you do that? By calling callbackFun itself! Note however that you have to pass one argument (t) to callbackFun.

## Solution

```js
function test (message,callbackFun) {
  console.log("#"+message);
  callbackFun({
    equal:function(num1,num2,msg){
      if(num1==num2){
        console.log("OK :"+ msg);
      }else{
        console.log("Error: "+msg);
      }
    }
  })
}

test('First',function(r) {
  r.equal(1,1,'one is equal to one');
});

test('Second', function(t) {
  t.equal(2,3,'two is equal to two');
});

test('Third', function(t) {
  t.equal(3,3,'three is equal to three');
});
```
----------

# 05



 * Sometimes we want to test more complicated data structures
 * than string or number. We may want to check if two objects
 * or to arrays got the same elements. Write a function which
 * compares two nested objects or arrays.

```js
var deepEqual = function(/* .... */) {
  // code here
};

console.log(deepEqual(
  [{a:3},{b:4}],
  [{a:'3'},{b:'4'}]
)); // -> false

console.log(deepEqual(
  {a:[2,3],b:[4]},
  {b:[4],a:[2,3]}
)); // -> true

console.log(deepEqual(
  'hello',
  'hello'
)); // -> true
```

## Solution
```js
var deepEqual = function(a,b) {
if(typeof a !== 'object' && typeof b !== 'object'){ return a === b;}

if (Object.keys(a).length !== Object.keys(b).length) return false;
return Object.keys(a).every(function(elm){
return deepEqual(a[elm],b[elm]);
});
};
```
-------------
# 06


 * Write a function remove which
 * takes as input and array of objects
 * and a number id.
 * The function should remove the element
 * with the corresponding id.

```js
function remove (store,id) {
  // code here
}

var data = [
  {name:'Foo',id:1,age:25},
  {name:'Bar',id:2,age:35},
  {name:'Zoo',id:3,age:18},
  {name:'Lii',id:4,age:20}
];

remove(data,2);

console.log(data);

  [
    {name:'Foo',id:1,age:25},
    {name:'Zoo',id:3,age:18},
    {name:'Lii',id:4,age:20}
  ]

```

## Solution
```js
function remove (store,id) {
  var deleteindex = store.map(function(elm){
   return elm.id;
  }).indexOf(id);
  store.splice(deleteindex,1);
  return store;
}

var data = [
  {name:'Foo',id:1,age:25},
  {name:'Bar',id:2,age:35},
  {name:'Zoo',id:3,age:18},
  {name:'Lii',id:4,age:20}
];

remove(data,2);
remove(data,4);
```
------------
# 07


 * Given an array of string with your names.
 * Write a function `randomSelect` which
 * takes an array and return one random
 * element inside that array.

```js
function randomSelect(list) {
  // code here
}

var names = [
  'Abdallah Ali Al-Shaikh Ali',
  'Ghada Ibrahim',
  'Mohammed Naji',
  'Akram Awni Badah',
  'Abeer Alshaer',
  'Shahenaz Mazen Monia',
  'Nizar Albanna',
  'Muhammed Mahdy Mushtaha',
  'Alaa Ahmed Khattab Khattab',
  'Zahra Al Ashi',
  'Sameh Habash',
  'Wasim Ayesh',
  'Rana Alqrenawi',
  'Alaa Al Ashi',
  'Mohammed Alshorafa'
];

```
## Solution

```js
function randomSelect(list) {
  var randName = list[Math.floor(Math.random() * list.length)];
  return randName;
}

randomSelect(names);
```
----------------
# 08
```js
var numberOfTimes = {
  'Abdallah Ali Al-Shaikh Ali': 0,
  'Ghada Ibrahim': 0,
  'Mohammed Naji': 0,
  'Akram Awni Badah': 0,
  'Abeer Alshaer': 0,
  'Shahenaz Mazen Monia': 0,
  'Nizar Albanna': 0,
  'Muhammed Mahdy Mushtaha': 0,
  'Alaa Ahmed Khattab Khattab': 0,
  'Zahra Al Ashi': 0,
  'Sameh Habash': 0,
  'Wasim Ayesh': 0,
  'Rana Alqrenawi': 0,
  'Alaa Al Ashi': 0,
  'Mohammed Alshorafa': 0
};
```

 * Loops 1000 times to make sure that all
 * names get called randomly and all the
 * same time



## Solution

```js
for (var i = 0 ; i < 10000; i++){ var randomName= randomSelect(names); numberOfTimes[randomName]++; }
```
------------
# 09

```js
var list = [
  ['name:Zoo','age:24','language:javascript'],
  ['name:Bar','age:21','language:python'],
  ['name:Foo','age:20','language:php'],
  ['name:Luu','age:32','language:ruby']
];
transform (list)
/**
 * Transform the data above to the following
 * format.
 * DO NOT USE FOR LOOPS.
 *
 * Hint: google `map` and `reduce`
 *
**/

var c = [
  {name:'Zoo',age:24,language:'javascript'},
  {name:'Bar',age:21,language:'python'},
  {name:'Foo',age:20,language:'php'},
  {name:'Luu',age:32,language:'ruby'},
];
```
## Solution

```js

function transform(list){
  return list.map(function(elem){
     return elem.reduce(function(object,value){

      object[value.split(":")[0]] = value.split(":")[1];

      return object

    },{});

  });

}
```
-------------
# 10

```js
/**
 * Create a fake `document` object which looks
 * exactley like the real one.
 * The fake document should behave in the
 * function `jQuery` expects it.
**/

var jQuery = function(document) {
  return function(selector) {
    var element = document.querySelector(selector);
    var obj = {};

    obj.addClass = function (newClass) {
      element.classList.add(newClass);
      return obj;
    };

    obj.text = function (text) {
      element.innerHTML = text;
      return obj;
    };

    return obj;
  };
};

var fakeDoc = {
  // challenge is here
  // write something
};

var $ = jQuery(fakeDoc);

$('#one').text('Hello World!');
```
## Solution
```js
var fakeDoc = {
  querySelector:function(sel){
    return {
      classList:{
        add:function(cls){
         console.log("test",cls)
        }
      }
    }
  }


};

var $ = jQuery(fakeDoc);
$('#one').addClass('my class!');
$('#one').text('Hello World!');
```
---------------
# 11


 *  Create a function called 'pipe'
 *  which takes as arguments other functions and returns
 *  another function. The new function behaves as a
 *  chain of all the functions put together.

```js
var pipe = function() {
  // code here
};

function add_one (n) {
  const total = n + 1;
  return total;
}

function less_one (n) {
  const total = n - 1;
  return total;
}

function multiply_two (n) {
  const total = n * 2;
  return total;
}

function start (n) {
  return parseInt(n);
}

var parse_add_multiply_subtract = pipe(
  start,
  add_one,
  multiply_two,
  less_one
);

parse_add_multiply_subtract('1'); // => 3

function add() {
  console.log(arguments);
  console.log(arguments.reduce); // undefined?! <== google how to fix it
}

add('hello',1,'GSG',2,3);

```

## Solution

```js
var pipe = function() {

     var args = Array.prototype.slice.call(arguments);

  return function(n){
    return args.reduce(function(acc,elem){
      return elem(acc);
     },n);
  }
};

function add_one (n) {
  const total = n + 1;
  return total;
}

function less_one (n) {
  const total = n - 1;
  return total;
}

function multiply_two (n) {
  const total = n * 2;
  return total;
}

function start (n) {
  return parseInt(n);
}
var parse_add_multiply_subtract = pipe(
  start,
  add_one,
  multiply_two,
  less_one
);

parse_add_multiply_subtract('2');
```
--------------
# 12


 * Implement a waterfall function.
 * This function works very similarly to what we
 * saw yesterday with `pipe`.

```js
var waterfall = function(arg, tasks, cb) {
  // code here
}

function add_one (n,cb) {
  setTimeout(function(){
    const total = n + 1;
    cb(total);
  },200);
}

function less_one (n,cb) {
  setTimeout(function(){
    const total = n - 1;
    cb(total);
  },200);
}

function multiply_two (n,cb) {
  setTimeout(function(){
    const total = n * 2;
    cb(total);
  },200);
}

function start (n,cb) {
  setTimeout(function(){
    const total = parseInt(n)
    cb(total);
  },200);
}

waterfall('1', [
  start,
  add_one,
  multiply_two,
  less_one
], function(res) {
  console.log(res); // => 3
});

/**
 * You have to replicate something like
 * this.
 */
start('1',function(n){
  // console.log(n);
  add_one(n,function(n2){
    // console.log(n2);
    multiply_two(n2,function(n3){
      // console.log(n3);
      less_one(n3,function(n4){
        console.log(n4);
      });
    });
  });
});
```
## Solution
```js
var waterfall = function(value, arg ,cb) {

  if( arg.length === 0){
    cb(value);
 }

  arg[0](value,function(total){
     waterfall(total,arg.slice(1),cb)
  });
}

function add_one (n,cb) {
  setTimeout(function(){
    const total = n + 1;
    cb(total);
  },200);
}

function less_one (n,cb) {
  setTimeout(function(){
    const total = n - 1;
    cb(total);
  },200);
}

function multiply_two (n,cb) {
  setTimeout(function(){
    const total = n * 2;
    cb(total);
  },200);
}
function start (n,cb) {
  setTimeout(function(){
    const total = parseInt(n)
    cb(total);
  },200);
}

waterfall('5', [
  start,
  add_one,
  multiply_two,
  less_one
], function(res) {
  console.log(res); // => 3
});
```
-------------
# 13


 * Complete the 'parallel' function. It should fire
 * all the tasks at the same time, and invoke the
 * final callback when they are all done.
 * In case of an error should fire the final callback
 * immediately.
 * More spec http://caolan.github.io/async/docs.html#parallel

```js
function parallel(tasks,finalCallback) {
  // code here
}

parallel([
  function(callback) {
    setTimeout(function() {
      callback(undefined,1);
    },2000);
  },
  function(callback) {
    setTimeout(function() {
      callback(undefined,2);
    },1000);
  },
  function(callback) {
    setTimeout(function() {
      callback(undefined,3);
    },1500);
  },
  // function(callback) {
  //   setTimeout(function() {
  //     callback('boom',undefined);
  //   },1200);
  // }
], function(err,result) {
  console.log('err ',err); // undefined
  console.log('result ',result); // [1,2,3]
});
```
## Solution
```js
function parallel(tasks,finalCallback) {

  var task = tasks.length,
      results = [];


  tasks.forEach(function(taskfn,index) {
    taskfn( function callback(err, result) {
      if (err) {
        finalCallback && finalCallback(err);
      } else if (--task === 0) {
        results[index]=result;
        finalCallback && finalCallback(null, results);
      } else{
        results[index]=result;
      }
   });
 });
}

parallel([
  function one(callback) {
    setTimeout(function() {
      callback(undefined,1);
    },2000);
  },
  function two(callback) {
    setTimeout(function() {
      callback(undefined,2);
    },4000);
  },
  function three(callback) {
    setTimeout(function() {
      callback(undefined,3);
    },1500);
  },

], function(err,result) {
  console.log('err ',err); // undefined
  console.log('result ',result); // [1,2,3]
});
```
----------
# 14
```js
/**
 * Checks the last name and returns the statistics
 * of the recurrence of that name give the first letter.
 * @param  {String} nameFirstLetter a string letter of the alphabet
 * @param  {Object} data              the data where names are stored
 * @return {Object}                 object statistics e.g.
 *
 * {
 *  letter: 'd',
 *  recurrence: 3,
 *  data: ['daves','dan',diren]
 * }
 */
function analyse (lastFirstLetter,data) {
  // code here
}

var obj = {
  frank: {
    lastName: 'len'
  },
  jane: {
    lastName: 'diren'
  },
  dave: {
    lastName: 'bolt'
  },
  sarah: {
    lastName: 'can'
  },
  karl: {
    lastName: 'daves'
  },
  jim: {
    lastName: 'dan'
  },
  dan: {
    lastName:'boo'
  },
  reb: {
    lastName: 'soo'
  },
  bar: {
    lastName:'foo'
  }
};
```
## Solution
```js
function analyse (lastFirstLetter,data) {
  return Object.values(data).filter(function(element){
  return element.lastName.slice(0,1)===lastFirstLetter;
  }).reduce (function(acc,elem,index){

      acc.letter= lastFirstLetter;
      acc.recurrence= index+1;
      acc.data[index]=elem.lastName;
      return acc;
  },{data:[]});}

  analyse("d",obj);
```
