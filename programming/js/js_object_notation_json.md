# JS: Object Notation (JSON)

There are two ways to access the properties of an object: the dot operator (.) and bracket notation ([]), similar to an array.

accessing object's property using variable:
```js
// Setup
var testObj = {
  12: "Namath",
  16: "Montana",
  19: "Unitas"
};

var playerNumber = 16;
var player = testObj[playerNumber];   // Change this Line
```

>Use bracket notation for properties with a space in their name.