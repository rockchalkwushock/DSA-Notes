# Depth First Traversal

## Types
> 1. [Base](#base)
> 2. [In-Order](#in-order)
> 3. [Pre-Order](#pre-order)
> 4. [Post-Order](#post-order)

## Base
Scans the BST for lowest value to greatest value.
```javascript
/**
* depthFirstTraversal(arg)
*
* @param {Function} iteratorFunc
*/
BST.prototype.depthFirstTraversal = function(iteratorFunc) {
  // if a child node exists run recursion.
  if (this.left) this.left.depthFirstTraversal(iteratorFunc);
  iteratorFunc(this.value);
  // if a child node exists run recursion.
  if (this.right) this.right.depthFirstTraversal(iteratorFunc);
}
```
### Example
```javascript
var bst = new BST(50);
bst.insert(30);
bst.insert(40);

function log(value) {
  console.log(value);
}

bst.depthFirstTraversal(log);
// 30
// 40
// 50
```

## In-Order
```javascript
/**
* depthFirstTraversal(arg, ar2)
*
* @param {Function} iteratorFunc
* @param {String} order
*/
BST.prototype.depthFirstTraversal = function(iteratorFunc, order) {
  if (this.left) this.left.depthFirstTraversal(iteratorFunc, order);
  if (order === 'in-order') iteratorFunc(this.value);
  if (this.right) this.right.depthFirstTraversal(iteratorFunc, order);
}
```
### Example
```javascript
var bst = new BST(50);
bst.insert(30);
bst.insert(40);

function log(value) {
  console.log(value);
}

bst.depthFirstTraversal(log, 'in-order');
// 30
// 40
// 50
```

## Pre-Order
```javascript
/**
* depthFirstTraversal(arg, ar2)
*
* @param {Function} iteratorFunc
* @param {String} order
*/
BST.prototype.depthFirstTraversal = function(iteratorFunc, order) {
  if (order === 'pre-order') iteratorFunc(this.value);
  if (this.left) this.left.depthFirstTraversal(iteratorFunc, order);
  if (order === 'in-order') iteratorFunc(this.value);
  if (this.right) this.right.depthFirstTraversal(iteratorFunc, order);
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

function log(value) {
  console.log(value);
}

bst.depthFirstTraversal(log, 'pre-order');
// 50
// 30
// 20
// 10
// 40
// 70
// 80
// 100
```

## Post-Order
```javascript
/**
* depthFirstTraversal(arg, ar2)
*
* @param {Function} iteratorFunc
* @param {String} order
*/
BST.prototype.depthFirstTraversal = function(iteratorFunc, order) {
  if (order === 'pre-order') iteratorFunc(this.value);
  if (this.left) this.left.depthFirstTraversal(iteratorFunc, order);
  if (order === 'in-order') iteratorFunc(this.value);
  if (order === 'post-order') iteratorFunc(this.value);
  if (this.right) this.right.depthFirstTraversal(iteratorFunc, order);
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

function log(value) {
  console.log(value);
}

bst.depthFirstTraversal(log, 'post-order');
// 10
// 20
// 40
// 30
// 100
// 80
// 70
// 50
```