# Adding to the Head

To do this we will need to create a prototype on the `LinkedList` constructor.

## What must the method achieve?
> 1. Create a new node at the beginning of the list.
> 2. Wire up the node for knowing where it resides in the list using _prev_ & _next_ values.
> 3. Make sure the **Head** pointer is now pointing at this new node since it is the **Head** of our Linked List now.

## Creating the `addToHead()` method:
```javascript
/**
 * addToHead(arg)
 *
 * @param {Number} value
 */
LinkedList.prototype.addToHead = function(value) {
  // Set the next node equal to the current head value.
  // Set the prev node to null because this is our new
  // head and nothing precedes it.
  // Set the new Node's value.
  var newNode = new Node(this.head, null ,value);
}
```

## Two Situations to account for when adding to the Head:

> If Linked List is empty...

If the answer is yes then we will point _both_ the **Head** & **Tail** pointers at this node.

> If Linked List is _not_ empty...

- make sure the _next_ & _prev_ properties are referencing the correct nodes.
- make sure the **Head** pointer is pointing to the _new_ **Head** node.

## Handling these situations in the `addToHead()` method:
```javascript
LinkedList.prototype.addToHead = function(value) {
  var newNode = new Node(this.head, null ,value);
  // if this.head = true
  // NOTE: reference links below about 'null'
  if (this.head) {
    // In this instance a head exists and
    // set this.head.prev = to the newNode.
    this.head.prev = newNode;
  } else {
    // In this instance we are adding the first node
    // to the list so we point both Head & Tail pointers
    // at this node.
    this.tail = newNode;
  }
  // Finally set this.head to the newNode value
  this.head = newNode;
}
```

## Examples of what will be returned:

### Empty List
```javascript
var LL = new LinkedList();
LL.addToHead(100);
// returns...
{
  head: { next: null, prev: null, value: 100 },
  tail: { next: null, prev: null, value: 100 }
}
```
### Non-Empty List
- `[Circular]` lets us know the 2 nodes are referencing each other.
```javascript
LL.addToHead(200);
// returns...
{
  head: {
    next: { value: 100, next: null, prev: [Circular] },
    prev: null,
    value: 200
  },
  tail: {
    next: null,
    prev: { value: 200, next: [Circular], prev: null },
    value: 100
  }
}
```
### Adding a third node
```javascript
LL.addToHead(300);
// returns...
{
  head: {
    next: {
      next: {
        next: null, // tail node, nothing after.
        prev: Node, // 200
        value: 100
      }
      prev: Node, // the Head Node.
      value: 200
    }
    prev: null, // Head node, nothing before.
    value: 300
  },
  tail: {
    next: null, // tail node, nothing after.
    prev: {
      next: Node // tail node 100
      prev: {
        next: Node, // 200
        prev: null, // Head node, nothing before.
        value: 300
      }
      value: 200
    }
    value: 100
  }
}
```

## Reference Links
- [MDN: Null ](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/null)
- [MDN: Equality Comparisons](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Equality_comparisons_and_sameness)
- [JavaScript Types](http://es5.github.io/#x8.2)
