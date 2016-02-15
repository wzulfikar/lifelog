# JS: Flatten Array of Arrays Using Reduce

```js
function flatten(arr){
  return arr.reduce(function(a, b) {
    return a.concat(b);
  }, []);
}
var arr_of_arrays = [[0, 1], [2, 3], [4, 5]];
console.log(flatten(arr_of_arrays)); // [0, 1, 2, 3, 4, 5]
```