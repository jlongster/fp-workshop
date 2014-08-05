
# Bind

Underscore also has a bunch of methods for operating on functions, some of which are available in modern JavaScript. One of these functions is [`_.bind`](http://underscorejs.org/#bind). Bind returns a new function that has the specified object as its `this` context, along with additional arguments baked in. Example:

```
function method(x, y) {
  return this.base * x * y;
}

var obj = { base: 10 };
var multiply = method.bind(obj);

console.log(multiply(2, 2)); // -> 40

multiply = method.bind(obj, 2);

console.log(multiply(2)); // -> 40
```

The most common usage of `bind` is to keep the `this` context for callbacks. If you pass a callback inside a method, by default it loses the `this` context:

```
var obj = {
  base: 10,
  method: function(arr) {
    return arr.map(function(x) {
      return x * this.base;
    }.bind(this));
  }
}
```

Without the `bind`, `this.base` would have used the wrong `this` object.

**Exercise:** Using [`_.bind`](http://underscorejs.org/#bind), implement a logging function that allows you to namespace messages. Your function should look like this:

```js
function log(type, message) {
 // code here
}
```

Now that you have that, use `_.bind` to create `info` and `error` functions that take a message and automatically passes in "info" and "error" as `type` to `log`. You would call them like so:

```js
info('some info');
error('an error!');

// -> "[info] some info"
// -> "[error] an error!"
```

[edit on jsbin](http://jsbin.com/pulaquro/1/edit?js,console)