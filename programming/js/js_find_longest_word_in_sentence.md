# JS: Find Longest Word in Sentence

```
function findLongestWord(str) {
  var lengths = str.split(' ').map(function(val){
    return val.length;
  });
  return Math.max.apply(null, lengths);
}

findLongestWord("The quick brown fox jumped over the lazy dog");
```