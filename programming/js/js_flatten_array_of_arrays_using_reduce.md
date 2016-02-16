# JS: Flatten Array of Arrays Using Reduce

```js
function flatten(arr){
  return arr.reduce(function(prev, current) {
    return prev.concat(current);
  }, []); // initalize value with []
}
var arr_of_arrays = [[0, 1], [2, 3], [4, 5]];
console.log(flatten(arr_of_arrays)); // [0, 1, 2, 3, 4, 5]
```

Another way to flatten array is using `concat` with `apply`:

```js
var arrays = [[0, 1], [2, 3], [4, 5]];
var merged = [].concat.apply([], arrays);
```

In above code, `var merged` is equivalent to:  
`[].concat([0, 1], [2, 3], [4, 5])`