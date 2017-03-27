# Constant Runtime

As input size increase the number of operations that we perform never changes. `log()` will only logout the first two elements of the array.

_Written as:_
```plaintext
O(1)
```

```javascript
function log(array) {
  console.log(array[0]);
  console.log(array[1]);
}

log([1, 2, 3, 4]);
log([1, 2, 3, 4, 5, 6, 7, 8, 9, 10]);
```