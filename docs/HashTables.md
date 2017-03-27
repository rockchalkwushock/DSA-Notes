# Hash Tables

## Table of Contents
1. [Creating a HashTable](https://github.com/rockchalkwushock/DSA-Notes/blob/master/docs/hashtables/Create.md)
2. [CharCodeAt Method & the Modulus Operator](https://github.com/rockchalkwushock/DSA-Notes/blob/master/docs/hashtables/CharCodeAt.md)
3. [Hashing the key](https://github.com/rockchalkwushock/DSA-Notes/blob/master/docs/hashtables/Hash.md)
4. [Inserting data in the table](https://github.com/rockchalkwushock/DSA-Notes/blob/master/docs/hashtables/Insert.md)
5. [Getting values from the table](https://github.com/rockchalkwushock/DSA-Notes/blob/master/docs/hashtables/Get.md)
6. [Retrieving all data from the table](
  https://github.com/rockchalkwushock/DSA-Notes/blob/master/docs/hashtables/RetrieveAll.md
)

## What is a Hash Table?
Hash Tables are used to store data that is associated in the form of a key & a value.

_example of how data is stored_
```javascript
{
  key: 'Pizza',
  value: '$2.25'
}
```
## Performance

### Constant `O(1)`
- Lookup
- Insertion

## What is collision & how does it effect performance?
Collision is when we have a bucket with data already present and try to store data in that same bucket. What we do to resolve this issue is form a simple Linked List in that bucket.

> NOTE: This will make the Hash Table less performant. _Searching_ the Hash Table would become `O(n)` when we hit the Linked List in the bucket.