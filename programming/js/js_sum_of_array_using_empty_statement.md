# JS: Sum of Array Using Empty Statement

As per JS documentation:

The empty statement is a semicolon (;) indicating that no statement will be executed, even if JavaScript syntax requires one. 

```js
var arr = [1, 2, 3], sum = 0;

for (i = 0; i < arr.length; sum += arr[i++]); // empty statement

console.log(sum); // 6
```

The opposite behavior, where you want multiple statements, but JavaScript only allows a single one, is possible using a block statement; it combines several statements into a single one.