# Recursion

> Recursion is when a function calls itself.

_example_
```javascript
function func() {
  if (/*base case*/) {
    return something;
  } else { // recursive case.
    func();
  }
}
```

> All Recursive functions have 2 cases:
> 1. The base case.
> 2. The recursive case.

_example_
```javascript
/**
* factorial(arg)
*
* @param {Number} num
* @returns {Number}
*/
function factorial(num) {
  if (num === 1) { // base case
    return num;
  } else { // recursive case
    return num * factorial(num - 1);
  }
}
```
1. When `num = 1` the factorial of `1!` is equal to `1` therefore we can just return it as the answer.
2. Any other case we will need to run recursion.
3. Recursion will take place until the base case is returned.
4. Then the call stack will unwind returning the values of each function call.

_example of `factorial(4)`_
```javascript
factorial(4);
// Iteration 1:
  num = 4 // go to recursive case
  4 * factorial(3);
// Iteration 2:
  num = 3 // go to recursive case
  3 * factorial(2);
// Iteration 3:
  num = 2 // go to recursive case
  2 * factorial(1);
// Iteration 4:
  num = 1 // satisfies base case
  return 1;
// Call Stack unwinds returning value of function:
  factorial(1); // return 1
  factorial(2); // return 2
  factorial(3); // return 6
  factorial(4); // return 24
```