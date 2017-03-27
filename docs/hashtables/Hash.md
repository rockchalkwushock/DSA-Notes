# Hashing the key for determining storage location.

```javascript
/**
* hash(arg)
*
* @param {String} key
* @returns {Number}
*/
HashTable.prototype.hash = function(key) {
  var total = 0;
  for (var i = 0; i < key.length; i++) {
    // loops over the string determining
    // it's total value.
    total += key.charCodeAt(i);
  }
  // gives us the remainder value
  var bucket = total % this.numBuckets;
  // bucket for which we will store the data.
  return bucket;
}
```

### Example
```javascript
var myHT = new HashTable(30);
console.log(myHT.hash('Becca')); // 12
```