# JS: Multiply All Number in Array

```js
function multiplyAll(arr) {
  return arr
    // flatten
    .reduce(function(prev, current){
      return prev.concat(current);
    }, [])
    // multiply
    .reduce(function(prev, current){
      return prev * current;
    }, 1);
}

// Modify values below to test your code
multiplyAll([[1,2],[3,4],[5,6,7]]);
```
