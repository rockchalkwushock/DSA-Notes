# Linear Runtime

As the input grows so do the number of operations that must be performed; thus a linear progression. As the array passed to `logAll()` increases in length the number of times the `for` loop must be performed increases proportionally.

_Written as:_
```plaintext
O(n)
```

```javascript
function logAll(array) {
  for(var i = 0; i < array.length; i++) {
    console.log(array[i]);
  }
}

logAll([1, 2, 3, 4, 5]);
logAll([1, 2, 3, 4, 5, 6]);
logAll([1, 2, 3, 4, 5, 6, 7]);
```