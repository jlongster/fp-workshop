# 01-map

```
function multiplyArray(arr, n) {
  return _.map(arr, function(x) { return x * n; });
}
```

# 02-filter

```
var result = _.filter(_.map(messages, function(m) {
  return m.message;
}), function(str) {
  return str.length < 50;
});
```

# 03-reduce

```
var counts = _.reduce(strings, function(counts, str) {
  counts[str] = str in counts ? counts[str] + 1 : 1;
  return counts;
}, {});
```

# 04-convenience

```
_.every(_.pluck(arr, 'age'), function(age) {
  return age > 13;
});
```

# 05-objects

## Exercise #1

```
var data = _.values(sales);
var avg = _.reduce(data, function(sum, sale) {
  return sum + sale;
}, 0) / data.length;
```

## Exercise #2

With mutation:

```
_.each(_.keys(sales), function(k) {
  sales[k] *= 2;
})
```

Without mutation:

```
var data = _.object(_.keys(sales), _.map(_.values(sales), function(x) {
  return x * 2;
}));
```