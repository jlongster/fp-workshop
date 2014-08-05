
# Partial Application

## Exercise #1

`bind` implements a form of "partial application". This means that you
can fill in arguments for a function in steps, and delay actually
calling the function. `bind` only lets you specify arguments in
left-to-right order, however. Real partial application lets you bind
any argument.

Implement a function named `bind2` that allows you to delay specifying
1 function argument. We won't do full partial evaluation to keep it
simple. Your `bind2` function would let you write code like this:

```js
var _arg = {};
function bind2(func, context /* args... */) {
  // code here
}

function nums(x, y, z) {
  return [x, y, z];
}

var n = bind2(nums, null, 1, _arg, 3);
console.log(n(2));

// -> [1, 2, 3]
```

We use a special `_arg` object to indicate the "slot" for the argument
that we will fill in later.

[edit on jsbin](http://jsbin.com/melahoja/1/edit?js,console)

## Exercise #2

As you've noticed by now, the underscore style of code is to wrap
function calls that looks like this `_.method1(_.method2(obj, ...), ...)`. This can get annoying if you are doing a lot of chaining.

Now that you have `bind2`, implement a `run` function that lets us specify transformations in sequential order. `run` should let you do this:

```js
var result = run(
  [1, 2, 3, 4, 5],
  bind2(_.filter, null, _arg, function(x) {
    return x % 2 === 0;
  }),
  bind2(_.map, null, _arg, function(x) {
    return x * 10
  }),
  bind2(_.reduce, null, _arg, function(acc, x) {
    return acc + x;
  })
)

console.log(result);

// -> 60
```

[edit on jsbin](http://jsbin.com/yogeboge/1/edit?js,console)