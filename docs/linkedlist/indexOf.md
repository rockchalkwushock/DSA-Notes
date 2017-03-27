# Finding the indexes of values in the List.

To do this we will need to create a prototype on the `LinkedList` constructor.

## What must the method achieve?
> 1. Must take in a searchValue and find every index of that value in the List.
> 2. Must return as an array all indexes the value occurs at in the List.

## Creating the `indexOf()` method:
```javascript
LinkedList.prototype.indexOf = function(value) {
  // array to store indexes of search value.
  var indexes = [];
  // beginning value for indexing the List.
  var currentIndex = 0;
  // node to start at.
  var currentNode = this.head;
  while(currentNode) {
    if (currentNode.value === value) {
      // push the index of the value to
      // the indexes array.
      indexes.push(currentIndex)
    }
    // prevents infinite loop.
    currentNode = currentNode.next;
    // increment index value on
    // every iteration.
    currentIndex++;
  }
  return indexes;
}
```

## Examples of what will be returned:
```javascript
var LL = new LinkedList();
LL.addToHead(1);
LL.addToHead(5);
LL.addToHead(3);
LL.addToTail(5);
LL.addToTail(8);
LL.addToTail(7);
LL.addToTail(5);

console.log(LL.search(5)); // [1, 3, 6]
```

