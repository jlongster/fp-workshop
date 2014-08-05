
# Filter

You have an array of objects that each have a message field, like so:

```js
var messages = [
    { message: 'Curabitur scelerisque leo hendrerit mauris tincidunt sodales.' },
    { message: 'Vestibulum sed magna id orci mollis pellentesque.' },
    { message: 'Curabitur at nisi nec magna mollis luctus id sed turpis.' }
]
```

Using [`_.filter`](http://underscorejs.org/#filter), transform this
into an array that has all messages (just the strings) that are less
than 50 characters. No helper functions and no for/while loops
allowed. Hint: use `_.map` first and then `_.filter`.

The imperative solution is:

```js
var result = [];
for(var i=0; i<messages.length; i++) {
  if(messages[i].message.length < 50) {
    result.push(messages[i].message);
  }
}
```

[edit on jsbin](http://jsbin.com/howuquhe/1/edit?js,console)