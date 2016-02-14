# JS: Global Variable

Variables which are used without the var keyword are automatically created in the global scope. This can create unintended consequences elsewhere in your code or when running a function again. You should always declare your variables with var

```js
// Setup
var outerWear = "T-Shirt";

function myFunction() {
  // Only change code below this line
  var outerWear = 'sweater';
  
  
  // Only change code above this line
  return outerWear;
}

myFunction();
```