# JS: End of String Checker

```
function end(str, target) {
  return str.slice(-target.length) == target;
}

end("Bastian", "n");
```

### Test
```js
console.assert(end("John", "n") === true);
```