# Get the Maximum Value present in the BST

```javascript
/**
* getMaxVal()
*
* @returns {Number}
*/
BST.prototype.getMaxVal = function() {
  if (this.right) return this.right.getMaxVal();
  else return this.value;
}
```

### Example
```javascript
var bst = new BST(50);
bst.insert(10);
bst.insert(20);
bst.insert(30);
bst.insert(40);
bst.insert(70);
bst.insert(80);
bst.insert(100);

bst.getMaxVal(); // 100
```