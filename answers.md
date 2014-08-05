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