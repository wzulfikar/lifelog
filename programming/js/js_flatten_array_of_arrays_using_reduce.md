# JS: Flatten Array of Arrays Using Reduce

```js
function flatten(arr){
  return arr.reduce(function(a, b) {
    return a.concat(b);
  }, []);
}
// flattened is [0, 1, 2, 3, 4, 5]
```