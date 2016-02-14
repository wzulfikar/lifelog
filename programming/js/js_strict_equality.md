# JS: Strict Equality

Strict equality (===) is the counterpart to the equality operator (==). Unlike the equality operator, strict equality tests both the data type and value of the compared elements.


// Setup
function myTest(val) {
  if (val == 12) { // Change this line
    return "Not Equal";
  }
  return "Equal";
}

// Change this value to test
myTest(12);
myTest("12");
