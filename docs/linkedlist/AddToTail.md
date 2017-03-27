# Adding to the Tail

To do this we will need to create a prototype on the `LinkedList` constructor.

## What must the method achieve?
> 1. Create a new node at the end of the list.
> 2. Wire up the node for knowing where it resides in the list using _prev_ & _next_ values.
> 3. Make sure the **Tail** pointer is now pointing at this new node since it is the **Tail** of our Linked List now.

## Creating the `addToTail()` method:
```javascript
/**
 * addToTail(arg)
 *
 * @param {Number} value
 * @returns {Object}
 */
LinkedList.prototype.addToTail = function(value) {
  // Set the next node equal to null since their
  // should be no node after the tail.
  // Set the prev node to the current tail, this.tail.
  // Set the new Node's value.
  var newNode = new Node( null, this.tail ,value);
}
```

## Two Situations to account for when adding to the Tail:

> If Linked List is empty...

If the answer is yes then we will point _both_ the **Head** & **Tail** pointers at this node.

> If Linked List is _not_ empty...

- make sure the _next_ & _prev_ properties are referencing the correct nodes.
- make sure the **Tail** pointer is pointing to the _new_ **Tail** node.

## Handling these situations in the `addToTail()` method:
```javascript
LinkedList.prototype.addToHead = function(value) {
  var newNode = new Node(this.head, null ,value);
  // if this.tail = true
  // NOTE: reference links below about 'null'
  if (this.tail) {
    // In this instance a tail exists and
    // set this.tail.next = to the newNode.
    this.tail.next = newNode;
  } else {
    // In this instance we are adding the first node
    // to the list so we point both Head & Tail pointers
    // at this node.
    this.head = newNode;
  }
  // Finally set this.tail to the newNode value
  this.tail = newNode;
}
```

## Examples of what will be returned:

### Empty List
```javascript
var LL = new LinkedList();
LL.addToTail(10);
// returns...
{
  head: { next: null, prev: null, value: 10 },
  tail: { next: null, prev: null, value: 10 }
}
```
### Non-Empty List
- `[Circular]` lets us know the 2 nodes are referencing each other.
```javascript
LL.addToTail(20);
LL.addToHead(30);
// returns...
{
  head: {
    next: {
      next: Node, // Tail node
      prev: Node, // Head node
      value: 20
    }
    prev: null, // Head node, nothing before.
    value: 10
  },
  tail: {
    next: null, // Tail node, nothing after.
    prev: {
      next: Node, // Tail node, 30
      prev: {
        next: Node, // 20
        prev: null, // Head node, nothing before.
        value: 10 // Head node.
      }
      value: 20
    }
    value: 30
  }
}
```

## Reference Links
- [MDN: Null ](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/null)
- [MDN: Equality Comparisons](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Equality_comparisons_and_sameness)
- [JavaScript Types](http://es5.github.io/#x8.2)
