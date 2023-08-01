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

Number + Number -> Addition
Boolean + Number -> Addition
Boolean + Boolean -> Addition
Number + String -> Concatenation
String + Boolean -> Concatenation
String + String -> Concatenation
