# Exponential Runtime

As the input size increases the number of operations performed exponentially grows. As the number elements in the array increases that is passed to `addAndLog()` we can say think in terms of:
```javascript
var x = array.length;
var operations;
operations = x ** 2 // x^2
// 1^2 = 1
// 2^2 = 4
// ...
// 10^2 = 100
```
_Written as:_
```plaintext
O(n^2)
```
```javascript
function addAndLog(array) {
  for(var i = 0; i < array.length; i++) {
    for(var j = 0; j < array.length; j++) {
      console.log(array[i] + array[j]);
    }
  }
}

addAndLog(['A', 'B', 'C']); // 9 pairs.
addAndLog(['A', 'B', 'C', 'D']); // 16 pairs.
addAndLog(['A', 'B', 'C', 'D', 'E']); // 25 pairs.
```