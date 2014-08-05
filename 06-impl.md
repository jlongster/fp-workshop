
# Implementation Details

Implement [`_.reduce`](http://underscorejs.org/#reduce). You are free to for loops if you want, or use `_.each`. The function will look like this:

```
function reduce(arr, func, start) {
  // code here
}
```

Use the following as a test case. This should print out `6`:

```
console.log(reduce([1,2,3], function(acc, x) {
  return acc + x;
}, 0))
```

Hint: you need to manually store the accumulated value in a variable and pass it in to `func`

[edit on jsbin](http://jsbin.com/xadaxice/1/edit?js,console)

## Advanced

Implement `_.reduce` using recursion. No local variable definitions are allowed. Recursive functions are functions that call themselves and have a stopping case, such as:

```js
function recur(n, func) {
  if(n > 0) {
    return [func(n)].concat(recur(n - 1, func));
  };
  return [func(0)];
}

console.log(recur(10, function(x) {
  return x * 2;
}));

// -> [20, 18, 16, 14, 12, 10, 8, 6, 4, 2, 0]
```

This program defines `recur` which takes a number, creates an array of that length with each number from `n` to 0, and applies a user-defined function to each element. This is actually pretty similar to [`_.range`](http://underscorejs.org/#range).

Implement `_.reduce` so that is recursively calls itself to apply the user-defined function for each element, and accumulates all the results into a single values.

[edit on jsbin](http://jsbin.com/paxosore/1/edit?js,console)