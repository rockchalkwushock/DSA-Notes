# Removing the Head

To do this we will need to create a prototype on the `LinkedList` constructor.

## What must the method achieve?
> 1. Must first verify their is a **Head** to remove.
> 2. If their is it must store the current value & set `this.head = this.head.next`.
> 3. Must then check if the list is now empty or not.
> 4. If empty then `this.tail = null`.
> 5. If not empty then `this.head.prev = null` because nothing can come before the **Head** node.
> 6. Must return the value of the removed node.

## Two Situations to account for when removing the Head:

> Is their not a **Head**...

If the answer is yes then we then we `return null`.

> If their is a **Head**...

- we store the current value.
- set `this.head = this.head.next`.
- Check if the _new_ **Head** exists in the list.
  - if it does set `this.head.prev = null`.
  - if not set `this.tail = null` because the list is now empty.

## Creating the `removeHead()` method:
```javascript
/**
 * removeHead()
 *
  * @returns {Number}
 */
LinkedList.prototype.removeHead = function() {
  // Case1: Empty List
  if (!this.head) return null;
  // Case2: List has a head.
  // store the current head value in a variable.
  var val = this.head.value;
  // set this.head to the next value in the list.
  this.head = this.head.next;
  // SubCase1: Is the list still populated?
  // if yes then their is nothing before the new head node.
  // set this.head.prev to null.
  if (this.head) this.head.prev = null;
  // SubCase2: Is the list empty?
  // if yes then this.tail should be set to null as well.
  else this.tail = null;
  return val;
}
```

## Examples of what will be returned:
```javascript
var LL = new LinkedList();
LL.addToHead(1000);
LL.addToHead(2000);
LL.addToHead(3000);

LL.removeHead();
// returns...
1000
```