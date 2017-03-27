# Logarithmic Runtime

As the number of inputs increase the number of operations that run will not grow proportionally but logarithmically. Logarithmic growth is the _inverse_ of Exponential growth.

_Written as:_
```plaintext
O(log n)
```
```javascript
function binarySearch(array, key) {
  var low = 0;
  var high = array.length - 1;
  var mid;
  var element;

  while(low <= high) {
    // Go to the middle of the array.
    mid = Math.floor((low + high) / 2, 10);
    element = array[mid];
    // if element is less than the key
    if (element < key) {
      // throw out everything before mid
      // including itself.
      low = mid + 1;
      // if element is greater than the key
    } else if (element > key) {
      // throw out everything after mid
      // including itself.
      high = mid - 1;
    } else {
      // or if mid is not greater than or
      // less than it must be mid === mid.
      return mid;
    }
  }
  return -1;
}

var alphabet = ['A', 'B', 'C', ...];

binarySearch(alphabet, 'H');
// Iteration 1: 'M'
// Iteration 2: 'F'
// Iteration 3: 'I'
// Iteration 4: 'H'
// 26 elements, only 4 operations.
```