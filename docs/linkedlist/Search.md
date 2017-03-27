# Searching the List

To do this we will need to create a prototype on the `LinkedList` constructor.

## What must the method achieve?
> 1. Must be able to search the entire list from **Head** to **Tail**.
> 2. Must be able to differentiate if a node exists or not.
> 3. Must return value searched if present in the list.

## Creating the `search()` method:
```javascript
/**
 * search(arg)
 *
 * @param {Number} searchValue
 * @returns {Number}
 * @returns {Null}
 */
LinkedList.prototype.search = function(searchValue) {
  // Starting point of search.
  var currentNode = this.head;
  while(currentNode) {
    if (currentNode.value === searchValue) return currentNode.value;
    // prevents infinite loop.
    currentNode = currentNode.next;
  }
  return null;
}
```

## Examples of what will be returned:
```javascript
var LL = new LinkedList();
LL.addToHead(100);
LL.addToHead(200);
LL.addToHead(300);
LL.addToTail(10);
LL.addToTail(20);
LL.addToTail(30);
```
### Value in List
```javascript
console.log(LL.search(300)); // 300
```
### Value not in List
```javascript
console.log(LL.search(222)); // null
```