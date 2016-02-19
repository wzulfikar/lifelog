# JS: Title Case

```
function titleCase(str) {
  return str.toLowerCase().split(' ').map(function(val){
    return val[0].toUpperCase() + val.slice(1);
  }).join(' ');
}

titleCase("I'm a little tea pot");
```

### Test
```js
test1 = titleCase('hello world!');
console.assert($title == 'Hello World!');

test2 = titleCase('HELLO WOrlD!');
console.assert(test2 == 'Hello World!');
```