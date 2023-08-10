# javascript-tips-tricks

**Nullish coalescing operator (??)**

The nullish coalescing (??) operator is a logical operator that returns its right-hand side operand when its left-hand side operand is null or undefined, and otherwise returns its left-hand side operand. 

const foo = null ?? 'default string';

console.log(foo);

// Expected output: "default string"

const baz = 0 ?? 42;

console.log(baz);

// Expected output: 0


**Optional chaining '?.'**

The optional chaining ?. is a safe way to access nested object properties, even if an intermediate property doesn’t exist.  
If the object accessed or function called using this operator is undefined or null, the expression short circuits and evaluates to undefined instead of throwing an error.

const dogName = adventurer.dog?.name;

console.log(dogName);

// Expected output: undefined


**JavaScript Array flat():**

The flat() method creates a new array with all sub-array elements concatenated:

const arr1 = [0, 1, 2, [3, 4]];

console.log(arr1.flat());
// Expected output: Array [0, 1, 2, 3, 4]


**JavaScript Array with():**

The with() method of Array instances is the copying version of using the bracket notation to change the value of a given index. It returns a new array with the element at the given index replaced with the given value.

const arr = [1, 2, 3, 4, 5];

console.log(arr.with(2, 6)); // [1, 2, 6, 4, 5]

console.log(arr); // [1, 2, 3, 4, 5]


**General guidelines for the plus operator:**

var bar = true;

console.log(bar + 0); // 1

console.log(bar + "xyz"); // truexyz

console.log(bar + true); // 2

console.log(bar + false); // 1

* Number + Number -> Addition,
* Boolean + Number -> Addition,
* Boolean + Boolean -> Addition,
* Number + String -> Concatenation,
* String + Boolean -> Concatenation,
* String + String -> Concatenation

**Math.round()**

The Math.round() static method returns the value of a number rounded to the nearest integer

console.log(Math.round(0.95)); // Expected output: 1

console.log(Math.round(5.95), Math.round(5.5), Math.round(5.30)); 
// Expected output: 6 6 5

**Math.ceil()**

The Math.ceil() static method always rounds up and returns the smallest integer greater than or equal to a given number.

console.log(Math.ceil(.95));  // Expected output: 1

console.log(Math.ceil(5.35)); // Expected output: 6

**Math.floor()**

The Math.floor() static method always rounds down and returns the largest integer less than or equal to a given number.

console.log(Math.floor(5.35)); // Expected output: 5

**parseFloat()**

The parseFloat() function parses a string argument and returns a floating point number.

parseFloat("401.00") // 401

parseFloat("   400 50") // 40

parseFloat("40 years") // 40

parseFloat("H40") // NaN

**Polyfill in Javascript**

Polyfills are pieces of code that provide modern functionality to older browsers that lack native support for those features. 


**Currying In JavaScript**

It is a process that allows you to transform a function with multiple arguments into a sequence of nesting functions.

Example: add(1, 2, 3) into callable as add(1)(2)(3).

**Octals and Hexadecimal**

Decimal literals can start with a zero (0) followed by another decimal digit, but if all digits after the leading 0 are smaller than 8, the number is interpreted as an octal number.

0888 // 888 parsed as decimal 

0777 // parsed as octal, 511 in decimal

