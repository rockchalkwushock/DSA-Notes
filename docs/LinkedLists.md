# Linked Lists

## Table of Contents
1. [Creating our Linked List](https://github.com/rockchalkwushock/DSA-Notes/blob/master/docs/linkedlist/Creating.md)
2. [Adding to the Head](https://github.com/rockchalkwushock/DSA-Notes/blob/master/docs/linkedlist/AddToHead.md)
3. [Adding to the Tail](https://github.com/rockchalkwushock/DSA-Notes/blob/master/docs/linkedlist/AddToTail.md)
4. [Removing the Head](https://github.com/rockchalkwushock/DSA-Notes/blob/master/docs/linkedlist/RemoveHead.md)
5. [Removing the Tail](https://github.com/rockchalkwushock/DSA-Notes/blob/master/docs/linkedlist/RemoveTail.md)
6. [Searching the List](https://github.com/rockchalkwushock/DSA-Notes/blob/master/docs/linkedlist/Search.md)
7. [Finding all the indexes of a value](https://github.com/rockchalkwushock/DSA-Notes/blob/master/docs/linkedlist/indexOf.md)

## What is a Linked List?
A linked list is a linear data structure where each element is a separate object.

## Types
- Singly Linked
> Only has reference to the node after it.
- Doubly Linked
> Each node has reference to the node before and after it.

## What must a Linked List know?
For a linked list to function properly it only needs to know about 2 nodes:
- The Head Node/Pointer
- The Tail Node/Pointer

## Basic Operations
There are 5 main operations we would want to be able to perform on our Linked List:
1. Add a node to the **Head**.
2. Add a node to the **Tail**.
3. Removing the **Head**.
4. Remove the **Tail**.
5. Searching the Linked List.

## Performance

### Constant `O(1)`
- Adding/Removing head.
- Adding/Removing tail.

### Linear `O(n)`
- Searching the List.

## Memory Management with Linked Lists
Data doesn't have to be stored together


## Example of a node:
```javascript
{
  value: 7,
  next: nextNode,
  prev: prevNode
}
```