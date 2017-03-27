# Contains a given value

```javascript
/**
* contains(arg)
*
* @param {Number} value
* @returns {Boolean}
*/
BST.prototype.contains = function(value) {
  // Base case
  if (value === this.value) return true;
  // Traverse Left side of tree.
  else if (value < this.value) {
    // Child node does not exist.
    if (!this.left) return false;
  // Recursive case
    else return this.left.contains(value);
  }
  // Traverse Right side of tree.
  else if (value > this.value) {
    // Child node does not exist.
    if (!this.right) return false;
  // Recursive case
    else return this.right.contains(value);
  }
}
```

## What is happening?
_Left Side_
> 1. Initially we check if the node we are on holds the search value.
> 2. We traverse the left side of the tree if the value is _less than_  the value of the current node.
> 3. If a child node does not exist at `this.left` we `return false`.
> 4. If their is a child node present we run recursion to compare the value of the child node to the search value.

_Right Side_
> 1. Initially we check if the node we are on holds the search value.
> 2. We traverse the right side of the tree if the value is _less than_  the value of the current node.
> 3. If a child node does not exist at `this.right` we `return false`.
> 4. If their is a child node present we run recursion to compare the value of the child node to the search value.

### Example
```javascript
var bst = new BST(50);

bst.insert(30);
bst.insert(40);

bst.contains(50); // true
bst.contains(40); // true
bst.contains(80); // false
```