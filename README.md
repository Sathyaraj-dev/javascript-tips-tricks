# javascript-tips-tricks

**How JS Works even if the file is empty**

The shortest code in Js is an empty file. Even if the file is empty, a Global Execution Context is created along with a global object

**Nullish coalescing operator (??)**

The nullish coalescing (??) operator is a logical operator that returns its right-hand side operand when its left-hand side operand is null or undefined, and otherwise returns its left-hand side operand. 

> const foo = null ?? 'default string';

> console.log(foo);

// Expected output: "default string"

> const baz = 0 ?? 42;

> console.log(baz);

// Expected output: 0


**Optional chaining '?.'**

The optional chaining ?. is a safe way to access nested object properties, even if an intermediate property doesn’t exist.  
If the object accessed or function called using this operator is undefined or null, the expression short circuits and evaluates to undefined instead of throwing an error.

> const dogName = adventurer.dog?.name;

> console.log(dogName);

// Expected output: undefined


**JavaScript Array flat():**

The flat() method creates a new array with all sub-array elements concatenated:

> const arr1 = [0, 1, 2, [3, 4]];

> console.log(arr1.flat());
// Expected output: Array [0, 1, 2, 3, 4]


**JavaScript Array with():**

The with() method of Array instances is the copying version of using the bracket notation to change the value of a given index. It returns a new array with the element at the given index replaced with the given value.

> const arr = [1, 2, 3, 4, 5];

> console.log(arr.with(2, 6)); // [1, 2, 6, 4, 5]

> console.log(arr); // [1, 2, 3, 4, 5]

**Primitive Type vs Reference Types**

Primitives:

🎇 They are immutable

🎇 They are compared by value

🎇 They are stored in call stack

Reference Types:

🎆 They are Mutable

🎆 They are compared by reference

🎆 They are stored in Heap

**Imperative Programming and Declarative Programming**

🔥 Imperative Programming:

🎆 Describes "how" to achieve a task with explicit step-by-step instructions, often involving loops and mutable state.

🔥 Declarative Programming:

🎆 Describe "what" you want to achieve without specifying step-by-step instructions, relying on higher-level abstractions and expressions.


**General guidelines for the plus operator:**

>var bar = true;

>console.log(bar + 0); // 1

>console.log(bar + "xyz"); // truexyz

>console.log(bar + true); // 2

>console.log(bar + false); // 1

* Number + Number -> Addition,
* Boolean + Number -> Addition,
* Boolean + Boolean -> Addition,
* Number + String -> Concatenation,
* String + Boolean -> Concatenation,
* String + String -> Concatenation

**Math.round()**

The Math.round() static method returns the value of a number rounded to the nearest integer

>console.log(Math.round(0.95)); // Expected output: 1

>console.log(Math.round(5.95), Math.round(5.5), Math.round(5.30)); 
// Expected output: 6 6 5

**Math.ceil()**

The Math.ceil() static method always rounds up and returns the smallest integer greater than or equal to a given number.

>console.log(Math.ceil(.95));  // Expected output: 1

>console.log(Math.ceil(5.35)); // Expected output: 6

**Math.floor()**

The Math.floor() static method always rounds down and returns the largest integer less than or equal to a given number.

>console.log(Math.floor(5.35)); // Expected output: 5

**parseFloat()**

The parseFloat() function parses a string argument and returns a floating point number.

>parseFloat("401.00") // 401

>parseFloat("   400 50") // 40

>parseFloat("40 years") // 40

>parseFloat("H40") // NaN

**Polyfill in Javascript**

Polyfills are pieces of code that provide modern functionality to older browsers that lack native support for those features. 


**Currying In JavaScript**

It is a process that allows you to transform a function with multiple arguments into a sequence of nesting functions.

Example: add(1, 2, 3) into callable as add(1)(2)(3).

**Octals and Hexadecimal**

Decimal literals can start with a zero (0) followed by another decimal digit, but if all digits after the leading 0 are smaller than 8, the number is interpreted as an octal number.

>0888 // 888 parsed as decimal 

>0777 // parsed as octal, 511 in decimal


**Deep Copy vs. Shallow Copy**

In Deep copy, when we assign a variable to another variable assignment using the operator, we are actually assigning only value and both of these variables are pointing to different locations which means if I change one, then it will not get reflected in both. All primitive data types are deep copied.

>const a = 10

>let b = a // copy

>b = 5

>console.log(b) // 5

>console.log(a) // 10

In Shallow copy, when we assign a variable to another variable using the assignment operator, We are actually assigning its reference to another variable, which means both variables point to the same memory location. If we change any of them, it will be reflected in both. All non-primitive data shallow JS types are copied.

>const a = {
>task: 'Hello',
>person: 'World'
>}

>let b = a // shallow copy

>b.person = 'Javascript';

>console. (b.person) // Javascript

>console.log(a.person) // Javascript

**Eval can be harmful (no-eval). What are the Alternatives to eval in JavaScript?**

`Function() is a faster and more secure alternative to eval().

> let operation = "2 * 5 + 10"

> let evaluation = Function("return " + operation)()

> console.log(evaluation) // logs correct result: 20

**What is Package.Lock.json? Should we commit to git?**

- Package.Lock.json stores the exact version of any package that is being used.

- Sometimes a package is updated and its version is changed so we have to store this information somewhere that all the developers have the same version of that package.

- Here Package.Lock.json comes into the picture. It saves the. exact version of the package.

- Yes it should be committed to Git.

**Difference between package.json and package-lock.json**

 - The package.json file focuses on project metadata and specifies the desired versions of dependencies.
   
 - The package-lock.json file ensures deterministic installations by locking the exact versions of dependencies and their dependencies. 
