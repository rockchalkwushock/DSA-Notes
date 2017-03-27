# Breadth First Traversal

```javascript
/**
* breadthFirstTraversal(arg)
*
* @param {Function} iteratorFunc
*/
BST.prototype.breadthFirstTraversal = function(iteratorFunc) {
  // [this] refers to root node
  var queue = [this];
  // loop will run until queue.length = null.
  while (queue.length) {
    var treeNode = queue.shift();
    iteratorFunc(treeNode);
    if (treeNode.left) queue.push(treeNode.left);
    if (treeNode.right) queue.push(treeNode.right);
  }
}
```

### What is happening?
> 1. We set our `queue` equal to an array with the context `this` or in other words we populate `queue` with our root node where `queue[0] = 50`.
> 2. Now when our `while` loop starts it will run continuously until `queue.length = null`.
> 3. The `treeNode` represents the value stored at `queue[0]`(_follow the link below to learn about `shift()`_).
> 4. Then our callback handles the `treeNode`. After this we look for a `left` & `right` child node and `push` them to the `queue`.

The following shows what is happening:
```javascript
// Iteration 1:
  [50] // starts with root node
  iteratorFunc(50);
// Iteration 2:
  [30, 70] // children of root node
  iteratorFunc(30);
// Iteration 3:
  [70, 20, 40] // children of 30 added
  iteratorFunc(70);
// Iteration 4:
  [20, 40, 80] // children of 70 added
  iteratorFunc(20);
// Iteration 5:
  [40, 80, 10] // children of 20 added
  iteratorFunc(40);
// Iteration 6:
  [80, 10] // 40 has no children
  iteratorFunc(80);
// Iteration 7:
  [10, 100] // children of 80 added.
  iteratorFunc(10);
// Iteration 8:
  [100] // 10 has no children
  iteratorFunc(100);
// Iteration 9:
// while loop terminates on queue.length = null.
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

function log(node) {
  console.log(node.value);
}

bst.breadthFirstTraversal(log);
// 50
// 30
// 70
// 20
// 40
// 80
// 10
// 100
```

## Resource Links
- [MDN Array.prototype.shift](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/shift)