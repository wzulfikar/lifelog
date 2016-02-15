# JS: Card Counting Blackjack

```js
var count = 0;

function cc(card) {
  // Only change code below this line
  var cardVal = {
    '0':[7,8,9],
    '-1':[10,'J','Q','K','A'],
    '1':[2,3,4,5,6]
  };
  
  Object.keys(cardVal).forEach(function(key,index) {
    cardVal[key].forEach(function(val){
      if(val == card) count += Number.parseInt(key);
    });
  });
  
  return count + ' ' + (count <= 0 ? 'Hold':'Bet');
}

// Add/remove calls to test your function.
// Note: Only the last will display
cc(2); cc(3); cc(7); cc('K'); cc('A');
```