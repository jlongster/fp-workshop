
# Convenience Methods

Underscore offers a range of convenience methods that make it easy to
apply operations to data. You could do everything with map, filter,
and reduce, but that gets very tedious.

A few examples are [`_.pluck`](http://underscorejs.org/#pluck) and
[`_.every`](http://underscorejs.org/#every). Using these two methods, validate an array of data that the `age` property on all of the items is greater than 13.

Constraint: you are not allowed to declare any variables.

Here you can really start to see how functional programming can be far
more concise and clear than imperative style. An imperative
implementation would look like (requires declaring variables):

```js
var data = [{ age: 15 }, { age: 18 }, { age: 30 }];

var ages = [];
for(var i=0; i<data.length; i++) {
  ages.push(data[i].age);
}

var validated = true;
for(var i=0; i<ages.length; i++) {
  if(ages[i] <= 13) {
    validated = false;
  }
}

console.log(validated);
```

View the full list of methods provided by underscore [here](underscorejs.org).

[edit on jsbin](http://jsbin.com/curemune/1/edit?js,console)