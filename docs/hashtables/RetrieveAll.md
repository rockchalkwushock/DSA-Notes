# Retrieving all nodes in the Hash Table

```javascript
/**
* retrieveAll()
*
* @returns {Array}
*/
HashTable.prototype.retrieveAll = function() {
  var allNodes = [];
  for (var i = 0; i this.numBuckets; i++) {
    var currentNode = this.buckets[i];
    while (currentNode) {
      allNodes.push(currentNode);
      currentNode = currentNode.next;
    }
  }
  return allNodes;
}
```

### Example
```javascript
var myHT = new HashTable(30);
myHT.insert('Dean', 'dean@gmail.com');
myHT.insert('Megan', 'megan@gmail.com');
myHT.insert('Dane', 'dane@gmail.com');

console.log(myHT.retrieveAll());
```

### Output
```javascript
[
  { key: 'Megan', value: 'megan@gmail.com', next: null },
  {
    key: 'Dean',
    value: 'dean@gmail.com',
    next: { key: 'Dane', value: 'dane@gmail.com', next: null }
  },
  { key: 'Dane', value: 'dane@gmail.com', next: null }
]
```