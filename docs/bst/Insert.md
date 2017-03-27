# Inserting more nodes in the BST

```javascript
/**
* insert(arg)
*
* @param {Number} value
* @returns {Object}
*/
BST.prototype.insert = function(value) {
  // Traverse Left side of BST.
  if (value <= this.value) {
    // if no child node exists create
    if(!this.left) this.left = new BST(value);
    // recursive case
    else this.left.insert(value);
  // Traverse Right side of BST.
  } else if (value > this.value) {
    // if no child node exists create
    if(!this.right) this.right = new BST(value);
    // recursive case
    else this.right.insert(value);
  }
}
```

## What is happening?
Should the value being inserted be _less than_ or _equal to_ the current node's `value` then we first check:
> Does a child node to the `left` exist
> 1. **No**: Create a child node `new BST(value)`.
> 2. **Yes**: run recursion comparing the submitted value against the left child node that was found previously `this.left.insert(value)`.

Should the value being inserted be _greater than_ the current node's `value` then we first check:
> Does a child node to the `right` exist
> 1. **No**: Create a child node `new BST(value)`.
> 2. **Yes**: run recursion comparing the submitted value against the right child node that was found previously `this.right.insert(value)`.


### Example
```javascript
var bst = new BST(50);

bst.insert(30);
// 30 <= 50
// this.left = null, so no child. exists.
// this.left = new BST(30);
bst.insert(40);
// 40 <= 50 (left side)
// this.left = 30
// a child node exists to left of the root node, run recursion.
// 40 > 30 (right side)
// this.right = null, so no child.
// this.right = new BST(40);
```
### Output
```javascript
console.log(bst);
{
  value: 50, // root node
  left: {
    value: 30, // child node to left of root node
    left: null,
    right: {
      value: 40, // child node to right of parent node.
      left: null,
      right: null
    }
  },
  right: null
}
```

So in this example their are ostensibly _2_ BST's. The first being 50 with a child of 30 on the left side & the second being 30 with a child of 40 on the right side.