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

>Also use bracket notation for properties with a space in their name.

---

Nested JSON & array:

```js
var myPlants = [
  { 
    type: "flowers",
    list: [
      "rose",
      "tulip",
      "dandelion"
    ]
  },
  {
    type: "trees",
    list: [
      "fir",
      "pine",
      "birch"
    ]
  }  
];

var secondTree = myPlants[1].list[1]; // "pine"
```