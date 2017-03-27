# Hashing the key for determining storage location.

```javascript
/**
* insert(arg, arg2)
*
* @param {String} key
* @param {Number} value
* @returns {Object}
*/
HashTable.prototype.insert = function(key, value) {
  // hash the key to find out what buckets
  // the data should be stored in.
  var index = this.hash(key);
  if (!this.buckets[index]) {
    // if that bucket is empty populate it.
    this.buckets[index] = new HashNode(key, value);
    // if the initial bucket has a matching key
  } else if (this.buckets[index].key === key) {
    // set new value on that node.
    this.buckets[index].value = value;
  } else {
    // if that bucket does have data there
    // then we traverse the node(s) and create
    // a new node on the Linked List at that
    // bucket.
    var currentNode = this.buckets[index];
    while (currentNode.next) {
      // if we find a matching key
      if (currentNode.next.key === key) {
        // set new value on that node.
        currentNode.next.value = value;
        return; // stop the loop
      }
      currentNode = currentNode.next;
    }
    currentNode.next = new HashNode(key, value);
  }
}
```

### Example
```javascript
var myHT = new HashTable(30);
myHT.insert('Dean', 'dean@gmail.com');
myHT.insert('Megan', 'megan@gmail.com');
console.log(myHt.buckets);
```

### Output
```javascript
[
  ...
  { key: 'Megan', value: 'megan@gmail.com', next: null }, // index 8
  ...
  { key: 'Dean', value: 'dean@gmail.com', next: null }, // index 16
]
```

## This is what it's like when worlds collide!
Example of what happens when a collision occurs.

### Example
```javascript
var myHT = new HashTable(30);
myHT.insert('Dean', 'dean@gmail.com');
myHT.insert('Megan', 'megan@gmail.com');
myHT.insert('Dane', 'dane@gmail.com');
console.log(myHt.buckets);
```

### Output
```javascript
[
  ...
  { key: 'Megan', value: 'megan@gmail.com', next: null }, // index 8
  ...
  {
    key: 'Dean',
    value: 'dean@gmail.com',
    next:  { key: 'Dane', value: 'dane@gmail.com', next: null }
  }, // index 16
]
```

## Updating a bucket
### Example
```javascript
var myHT = new HashTable(30);
myHT.insert('Dean', 'dean@gmail.com');
myHT.insert('Megan', 'megan@gmail.com');
myHT.insert('Dane', 'dane@gmail.com');
myHT.insert('Megan', 'megansmith@gmail.com');
console.log(myHt.buckets);
```

### Output
```javascript
[
  ...
  { key: 'Megan', value: 'megansmith@gmail.com', next: null }, // index 8
  ...
  {
    key: 'Dean',
    value: 'dean@gmail.com',
    next:  { key: 'Dane', value: 'dane@gmail.com', next: null }
  }, // index 16
]
```