# Binary Search Trees

## Table of Contents
1. [Recursion](https://github.com/rockchalkwushock/DSA-Notes/blob/master/docs/bst/Recursion.md)
2. [Creating a BST](https://github.com/rockchalkwushock/DSA-Notes/blob/master/docs/bst/Creating.md)
3. [Inserting a node](https://github.com/rockchalkwushock/DSA-Notes/blob/master/docs/bst/Insert.md)
4. [Does the BST contain a given value](https://github.com/rockchalkwushock/DSA-Notes/blob/master/docs/bst/Contains.md)
5. [Depth First Traversal](https://github.com/rockchalkwushock/DSA-Notes/blob/master/docs/bst/DepthFirstTraversal.md)
6. [Breadth First Traversal](https://github.com/rockchalkwushock/DSA-Notes/blob/master/docs/bst/BreadthFirstTraversal.md)
7. [Finding the Minimum Value](https://github.com/rockchalkwushock/DSA-Notes/blob/master/docs/bst/GetMinVal.md)
8. [Finding the Maximum Value](https://github.com/rockchalkwushock/DSA-Notes/blob/master/docs/bst/GetMaxVal.md)

## What is a Binary Search Tree?
A Binary Search Tree or BST is known as a collection of nodes that are connected in a specific way. Each node will have up to 2 child nodes and each node will have a value stored within it.

> Nodes to the left of the parent will hold a lesser
> value than that of the parent; contrary to the
> nodes to the right of the parent which will hold
> greater values than the parent.

We will no long look at _nodes_ as _nodes_ but as individual BST's of the greater BST. When looking at a diagram we can see that each node has is a sub-BST containing a _parent node_ with up to _2 children nodes_.

## Performance
It has the _highest_ performability when the tree is _balanced_.

### Logarithmic `O(log n)`
- Adding/Removing a node.
- Searching the BST.

_examples for BST usage_
- Dictionary
- Phone Book
- Users