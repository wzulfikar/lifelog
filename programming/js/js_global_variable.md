# JS: Global Variable

Variables which are used without the var keyword are automatically created in the global scope. This can create unintended consequences elsewhere in your code or when running a function again. You should always declare your variables with var

It is possible to have both local and global variables with the same name. When you do this, the local variable takes precedence over the global variable.

```js
// Setup
var outerWear = "T-Shirt";

function myFunction() {
  // Only change code below this line
  var outerWear = 'sweater';
  console.log(outerWear);
}

myFunction(); // `sweater`
console.log(outerWear); // `T-Shirt`
```