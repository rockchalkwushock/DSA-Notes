# Creating a Linked List

We will need 2 constructor functions:
- `LinkedList()`
- `Node()`

_Linked List Constructor_
```javascript
/**
 * LinkedList()
 */
function LinkedList() {
  this.head = null;
  this.tail = null;
}
```

_Node Constructor_
```javascript
/**
 * Node(arg, arg2, arg3)
 *
 * @param {String} next
 * @param {String} prev
 * @param {Number} value
 */
function Node(next, prev, value) {
  this.next = next;
  this.prev = prev;
  this.value = value;
}
```

## Using the Constructors
```javascript
var LL = new LinkedList();
console.log(LL);
// Our Linked List
{
  head: null,
  tail: null
}

var node1 = new Node('node2', null, 100);
console.log(node1);
// Our first node
{
  next: 'node2',
  prev: null,
  value: 100
};
```