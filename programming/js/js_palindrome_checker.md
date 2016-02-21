# JS: Palindrome Checker

```
function palindrome(str) {
  // Good luck!
  var onlyWord = str.toLowerCase().replace(/(\W|_)+/g,'');
  return onlyWord == onlyWord.split('').reverse().join('');
}

palindrome("0_0 (: /-\ :) 0-0");

```

### Test
```js
console.assert(false);
```