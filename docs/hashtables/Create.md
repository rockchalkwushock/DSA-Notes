# Creating a Hash Table

When creating a Hash Table the constructor function will need to accept the size in which we want to initialize the Hash Table too.

## Hash Table Constructor
```javascript
/**
* HashTable(arg)
*
* @param {Number} size
* @returns {Object}
*/
function HashTable(size) {
  this.buckets = Array(size);
  this.numBuckets = this.buckets.length;
}
```

### Example
```javascript
var myHT = new HashTable(30);
console.log(myHT);
```

### Output
```javascript
{
  buckets: [30],
  numBuckets: 30
}
```

## Hash Node Constructor
```javascript
/**
* HashTable(arg, arg2, arg3)
*
* @param {String} key
* @param {String} value
* @param {Object} next
* @returns {Object}
*/
function HashNode(key, value, next) {
  this.key = key;
  this.value = value;
  this.next = next || null;
}
```

### Example
```javascript
var myHT = new HashTable(5);
// following code would reside inside a prototype method.
var index = 2;
this.buckets[index] = new HashNode('Matt', 'matt@aol.com', null);
console.log(myHT.buckets);
```

### Output
```javascript
[
  ,
  ,
  { key: 'Matt', value: 'matt@aol.com', next: null }, // index 2
  ,
  ,
]
```