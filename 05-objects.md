
# Objects

So far we've only worked with arrays. You can also iterate over
objects in a similar fashion using a few object-specific methods from
underscore.

## Exercise #1

Given the following data, calculate the average number of sales using [`_.values`](http://underscorejs.org/#values). Note: I am only mentioning new methods, you may have to use ones you've already used beore.

Constraint: do not create any helper functions or use a for/while loop.
Hint: it's ok to stash the result of `_.values` into a temporary variable.

```js
var sales = {
  joe: 34,
  bill: 12,
  alice: 22,
  james: 23,
  becca: 45,
  emily: 15
};
```

The imperative solution looks like:

```js
var i = 0;
var avg = 0;
for(var k in sales) {
  avg += sales[k];
  i++;
}
avg /= i;

console.log(avg);
```

[edit on jsbin](http://jsbin.com/wayiquza/1/edit?js,console)

## Exercise #2

Given the same dataset, multiply each sales number for each person by 2 using [`_.each`](http://underscorejs.org/#each) and [`_.keys`](http://underscorejs.org/#keys) by mutating the original dataset.

Imperative solution:

```js
for(var name in sales) {
  sales[name] *= 2;
}
```

[edit on jsbin](http://jsbin.com/qikofuye/1/edit?js,console)

Now do the same thing without mutating the original object. You should check out [`_.object`](http://underscorejs.org/#object).

Imperative solution:

```js
var data = {};
for(var name in sales) {
  data[name] = sales[name] * 2;
}
```

This is a trivial example, and the imperative solution may look better to you. However, in more complex code you will find the functional code to be better composable when you need to pass around the keys or values.

[edit on jsbin](http://jsbin.com/nufuyuku/1/edit?js,console)