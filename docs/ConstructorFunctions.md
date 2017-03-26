# Constructor Functions & Prototypes

## Constructor Functions
Constructors are written with capitalization so they are easily denoted as constructors & not simply functions.

### The JavaScript keyword `this`:
- [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/this)
- [StackOverflow](http://stackoverflow.com/questions/3127429/how-does-the-this-keyword-work)

_User Constructor_
```javascript
/**
 * User(arg, arg2, arg3, arg4)
 *
 * @param {String} firstName
 * @param {String} lastName
 * @param {Number} age
 * @param {String} gender
 */
function User(firstName, lastName, age, gender) {
  this.firstName = firstName;
  this.lastName = lastName;
  this.age = age;
  this.gender = gender;
}
```
_Using the User Constructor_
```javascript
var user1 = new User('John', 'Smith', 26, 'male');
var user200 = new User('Jill', 'Robinson', 25, 'female');
```

_What does it return?_
```javascript
// user 1
User {
  age: 26,
  firstName: "John",
  gender: "male"
  lastName: "Smith",
}
// user 200
User {
  age: 25,
  firstName: "Jill",
  gender: "female"
  lastName: "Robinson",
}
```

## Prototypes
An object that multiple other objects can refer too.

> A prototype is only accessible from the objects made by the constructory function the prototype was added.

>In the below example `emailDomain` will only be accessible on objects created by `User()`. If we had another constructor creating objects, say `Account()` and created an object `account1` this object would never have access to `emailDomain` unless we add it as a _prototype_ to `Account()`.

```javascript
User.prototype.emailDomain = '@facebook.com';
// user 1
User {
  age: 26,
  firstName: "John",
  gender: "male"
  lastName: "Smith",
  __proto__: Object
    constructor: User(firstName, lastName, age, gender)
    emailDomain: "@facebook.com"
}
user200.emailDomain // "@facebook.com"
```
_Functions as prototypes_
```javascript
User.prototype.getEmailAddress = function() {
  return this.firstName + this.lastName + this.emailDomain;
}
// user 1
User {
  age: 26,
  firstName: "John",
  gender: "male"
  lastName: "Smith",
  __proto__: Object
    constructor: User(firstName, lastName, age, gender)
    emailDomain: "@facebook.com"
    getEmailAddress: ()
      arguments: null
      caller: null
      length: 0
      name: ""
}
user200.getEmailAddress(); // JillRobinson@facebook.com
```