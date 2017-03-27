# Creating a Binary Search Tree

When creating a BST the constructor function will need to accept the value being passed in and store using the `this` keyword.

The constructor will need to set the later conditions of `left` & `right` to `null` because when creating the BST the constructor function _only_ accepts one value making this the _parent_ or _root_ node of the BST.

```javascript
/**
* BST(arg)
*
* @param {Number} value
* @returns {Object}
*/
function BST(value) {
  this.value = value;
  this.left = null;
  this.right = null;
}
```

_example_
```javascript
var bst = new BST(50);
console.log(bst);
{
  value: 50,
  left: null,
  right: null
}
```