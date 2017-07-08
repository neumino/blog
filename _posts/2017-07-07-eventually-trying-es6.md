---
layout: post
category : Geek
tags : [tensorflow, python, quickstart]
title: Eventually trying ES6
---
{% include JB/setup %}

I have written some JavaScript code in the past and still do, but I still
haven't really use any ES6 features for a few different reasons:

- I feel like most of the people jumped to ES6 because it was the new shiny
thing - but without undertanding the differences.. This is very similar to
people using MongoDB because it's web scale, or React because the DOM is slow.
For example as a maintainer of
[thinky](https://github.com/neumino/thinky), I had to
[deal](https://github.com/neumino/thinky/issues/399) 
[with](https://github.com/neumino/thinky/issues/351)
[multiple](https://github.com/neumino/thinky/issues/351)
[reports](https://github.com/neumino/thinky/issues/598) of `import` not working while `require` was.
- While ES6 features could have been nice when using Node.js, you cannot expect
enough browsers to support all the new features.
- Most of the new features people were talking about were just sugar to make
JavaScript more Java/CoffeeScript like, and I personally find JavaScript's
paradigm pleasant to use (though I would probably not use it to build a company).

Anyway, as time passed, I recently looked a bit at all the new features, and here's a
quick post about what I found interesting/sneaky. I'll skip generators,
typed arrays and a few other features that I happened to have already used in
the past.

* Constants are "easier" to create (not sure if anyone was going through the
pain of doing so with ES5).

```js
const PI = 3.141593 
PI = 3 // will result in an error.
```

* Block scoped variables are nice since they reduce the scope of variables - and
make the code easier to read.

```js
for (let i=0; i<10; i++) {
  console.log(i); // 0, 1, ...
}
console.log(i); // i is undefined.
```

* Block-scoped function are a bit sneaky in my opinion considering that:

```js
{
  function foo () { return 1 }
  console.log(foo()) // Prints 1.
  {
    function foo () { return 2 }
    console.log(foo()) // Prints 2.
  }
  console.log(foo()) // Prints 1.
}
function foo () { return 3 }
console.log(foo()) // Prints 3.
{
  function foo () { return 4 }
  console.log(foo()) // Prints 4.
}
console.log(foo()) // Prints 4.
```

* Fat arrows are a nice touch to make JavaScript more similar to other languages,
and probably makes it more accessible. That being said, it doesn't
reduce the total complexity around `this` and just add a new way to think about
when evaluating `this`.

```js
let a = [10];
this.b = [];
console.log(this); // { b: [] }

a.forEach((x) => {
  console.log(this); // { b: [] }
})
a.forEach(function(x) {
  console.log(this); // this === global, or undefined if you use strict mode.
})
```

* Default parameter values are a nice python-ish touch in my opinion.

```js
function sum(x, y=4, z=5) {
  return x+y+z;
}
console.log(sum(0, 0, 0)); // 0
console.log(sum(3, 0)); // 8
console.log(sum(0)); // 9
```

* Rest parameter, which used to be available in `arguments` after a few
operations is easier to grab now - though while nice I'm not convinced this is
a very useful feature.

```js
function sum(x, y, ...rest) {
  return x+y+rest.length;
}
console.log(sum(1, 2)); // 3
console.log(sum(1, 2, 3)); // 4
console.log(sum(1, 2, 3, 3)); // 5
```

* You can also directly insert an array with the `...` operator, though
`concat` is cleaner in my opinion.

```js
let a = [10, 11, 12];
let b = [20, 21, ...a];
console.log(b); // [20, 21, 10, 11, 12]
```

* String interpolation is a nice touch, though like many ES6 features,
JavaScript engines are not quite as performant compared to doing dumb
concatenation with `+`.

```js
let data = { name: 'Michel' };
console.log(`Hello ${data.name}!`); // Hello Michel!
```

* You can also do custom interpolation, which I am not quite convinced about -
it doesn't strike me as a quite readable syntax.

```js
let data = { name: 'Michel' };
console.log(`Hello ${data.name}!`); // Hello Michel!
print`Hello ${data.name}!`; // Hello Michel!
```

* Sticky regex - these are definitively nice and should prevent some string
manipulation.

```js
let str = 'foo1foo2';
let pattern = /foo(\d+)/y; // Note the /y at the end.
let result = pattern.exec(str);
console.log(result[0]); // foo1
console.log(pattern.lastIndex); // 4

result = pattern.exec(str);
console.log(result[0]); // foo2
console.log(pattern.lastIndex); // 8
```

* Property shorthand for object declaration seems fairly useful and unreadable
in my opinion.

```js
let x = 1;
let y = 2;
let a = {x, y}
console.log(a); // { x: 1, y: 2}
```

* Directly declare function as object property. This seems to just add more
confusion to a language that has already a lot of pitfalls.

```js
let a = {
  x() { return 2 }
}
console.log(a.x()); // 2
```

* Dynamically computing the name of a property is the only reasonable change I
could find in how we can declare object properties now.

```js
let a = {
  x: 1,
  ['foo' + 'bar']: 2
};
console.log(a); // { x: 1, foobar: 2}
```

* You can directly assign portion of an array to variables (similar to Python):

```js
let list = [1, 2, 3, 4, 5];
let [a, , b, ...c] = list;
console.log(a); // 1
console.log(b); // 3
console.log(c); // [4, 5]
```

* Same with objects - though you can also do deep/partial matching, which is a
horrible syntax in my opinion.

```js
let a = {foo: 1, bar: 2}
let {foo, bar, buzz} = a;
console.log(foo); // 1
console.log(bar); // 2
console.log(buzz); // undefined
```

* New way to define "classes" and extend them, which makes JavaScript more
similar to other OOP languages like Java.

```js
class Foo {
  constructor(id) {
    this.id = id
  }
  print() {
    return `This is ${this.id}`
  }
  static default() {
    return new Foo(0);
  }
}

class Bar {
  constructor(id, bar_value) {
    super(id);
    this.bar = bar_value;
  }
}
```

While talking about classes, you also have getter/setter, which in my opinion
makes things more ambiguous.

* `Map` and `Set` which allow you to clearly define your data structure
instead of using a plain dictionary.

```js
let s = new Set();
s.add('foo').add('bar').add('foo');
console.log(s.size); // 2
console.log(s.has('foo')); // true
for (let key of s.values()) {
  console.log(key); // foo, bar
}
```

* There is one last interesting feature around internationalization with
`Intl.Collator` that seems to reorder unicode characters in different ways
according to your local. While this is quite interesting, I can imagine a
plethora of issues coming up from having different ordering according to the
user's locale.

```js
var list = [ "ä", "a", "z" ]
var l10nFR = new Intl.Collator("fr")
var l10nSV = new Intl.Collator("sv")
console.log(list.sort(l10nFR.compare)) // [ "a", "ä", "z" ]
console.log(list.sort(l10nSV.compare)) // [ "a", "z", "ä" ]
```

I think this is it for the new ES6 features that I never really looked into.
After quite some time, I eventually got poke a bit more around ES6.
