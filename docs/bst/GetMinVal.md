# Get the Minimum Value present in the BST

```javascript
/**
* getMinVal()
*
* @returns {Number}
*/
BST.prototype.getMinVal = function() {
  if (this.left) return this.left.getMinVal();
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

bst.getMinVal(); // 10
```