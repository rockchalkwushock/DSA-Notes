# Hashing the key for determining storage location.

```javascript
/**
* get(arg)
*
* @param {String} key
* @returns {String}
* @returns {Null}
*/
HashTable.prototype.get = function(key) {
  // hash the key
  var index = this.hash(key);
  // if no data at that bucket return null.
  if (!this.buckets[index]) return null;
  else {
    // otherwise traverse the Linked List
    // searching for the key.
    var currentNode = this.buckets[index];
    while (currentNode) {
      // if a match found return the value of the node.
      if (currentNode.key === key) return currentNode.value;
      currentNode = currentNode.next;
    }
    // if no matching key exists in the list
    // then return null.
    return null;
  }
}
```

### Example
```javascript
var myHT = new HashTable(30);
myHT.insert('Dean', 'dean@gmail.com');
myHT.insert('Megan', 'megan@gmail.com');
myHT.insert('Dane', 'dane@gmail.com');

console.log(myHT.get('Megan')); // megan@gmail.com
console.log(myHT.get('Tom')); // null
```

