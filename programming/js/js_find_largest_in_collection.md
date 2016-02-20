# JS: Find Largest in Collection

```
function largestOfFour(arr) {
  // You can do this!
  return arr.map(function(val){
    return Math.max.apply(null, val);
  });
}

largestOfFour([[4, 5, 1, 3], [13, 27, 18, 26], [32, 35, 37, 39], [1000, 1001, 857, 1]]);
```

### Test
```js
console.assert(false);
```