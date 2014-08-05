# 01-map

```js
function multiplyArray(arr, n) {
  return _.map(arr, function(x) { return x * n; });
}
```

# 02-filter

```js
var result = _.filter(_.map(messages, function(m) {
  return m.message;
}), function(str) {
  return str.length < 50;
});
```

# 03-reduce

```js
var counts = _.reduce(strings, function(counts, str) {
  counts[str] = str in counts ? counts[str] + 1 : 1;
  return counts;
}, {});
```

# 04-convenience

```js
_.every(_.pluck(arr, 'age'), function(age) {
  return age > 13;
});
```

# 05-objects

## Exercise #1

```js
var data = _.values(sales);
var avg = _.reduce(data, function(sum, sale) {
  return sum + sale;
}, 0) / data.length;
```

## Exercise #2

With mutation:

```js
_.each(_.keys(sales), function(k) {
  sales[k] *= 2;
})
```

Without mutation:

```js
var data = _.object(_.keys(sales), _.map(_.values(sales), function(x) {
  return x * 2;
}));
```

# 06-impl

```js
function reduce(arr, func, start) {
  var acc = start;
  _.each(arr, function(item) {
    acc = func(acc, item);
  })
  return acc;
}
```

With recursion:

```js
function reduce(arr, func, start) {
  if(arr.length) {
    return func(reduce(arr.slice(1), func, start), arr[0])
  }
  return start;
}
```

# 07-bind

```js
function log(type, message) {
  console.log('[' + type + '] ' + message)
}

// create `info` and `error` functions
var info = _.bind(log, null, 'info');
var error = _.bind(log, null, 'error');

info('some info');
error('an error!');
```

# 08-partial

```js
var _arg = {};

function bind2(func, context /* args... */) {
  var args = Array.prototype.slice.call(arguments, 2);
  
  return function(arg) {
    args = _.map(args, function(a) {
      if(a === _arg) {
        return arg;
      }
      return a;
    })
    
    return func.apply(context, args);
  }
}
```