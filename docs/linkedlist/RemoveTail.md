# Removing the Tail

To do this we will need to create a prototype on the `LinkedList` constructor.

## What must the method achieve?
> 1. Must first verify their is a **Tail** to remove.
> 2. If their is it must store the current value & set `this.tail = this.tail.prev`.
> 3. Must then check if the list is now empty or not.
> 4. If empty then `this.head = null`.
> 5. If not empty then `this.tail.next = null` because nothing can come after the **Tail** node.
> 6. Must return the value of the removed node.

## Two Situations to account for when removing the Tail:

> Is their not a **Tail**...

If the answer is yes then we then we `return null`.

> If their is a **Tail**...

- we store the current value.
- set `this.tail = this.tail.prev`.
- Check if the _new_ **Tail** exists in the list.
  - if it does set `this.tail.next = null`.
  - if not set `this.head = null` because the list is now empty.

## Creating the `removeTail()` method:
```javascript
/**
 * removeTail()
 *
 * @returns {Number}
 */
LinkedList.prototype.removeTail = function() {
  // Case1: Empty List
  if (!this.tail) return null;
  // Case2: List has a tail.
  // store the current tail value in a variable.
  var val = this.tail.value;
  // set this.tail to the previous value in the list.
  this.tail = this.tail.prev;
  // SubCase1: Is the list still populated?
  // if yes then their is nothing after the new tail node.
  // set this.tail.next to null
  if (this.tail) this.tail.next = null;
  // SubCase2: Is the list empty?
  // if yes then this.head should be set to null as well.
  else this.head = null;
  return val;
}
```

## Examples of what will be returned:
```javascript
var LL = new LinkedList();
LL.addToHead(1000);
LL.addToHead(2000);
LL.addToHead(3000);

LL.removeTail();
// returns...
3000
```