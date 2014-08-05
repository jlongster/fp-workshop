
# Reduce

## Exercise #1

Given an array of strings, use
[`_.reduce`](http://underscorejs.org/#reduce) to create an object that
contains the number of times each string occurred in the array.

The imperative solution looks like this:

```js
var strings = ["lorem", "ipsum", "lorem", "amet", "amet", "amet"];

var counts = {};
for(var i=0; i<strings.length; i++) {
  var str = strings[i];
  counts[str] = str in counts ? counts[str] + 1 : 1;
}

console.log(counts);
```

[edit on jsbin](http://jsbin.com/sixizaje/1/edit?js,console)
