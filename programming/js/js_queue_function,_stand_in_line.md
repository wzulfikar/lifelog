# JS: Queue Function, "Stand in line!"
*From www.freecodecamp.com/challenges/stand-in-line*

Queue is data structure in js.

```js
function queue(arr, item) {
  // Your code here
  return arr.push(item) && arr.shift();
}

// Test Setup
var testArr = [1,2,3,4,5];

// Display Code
console.log("Before: " + JSON.stringify(testArr));
console.log(queue(testArr, 6)); // Modify this line to test
console.log("After: " + JSON.stringify(testArr));
```