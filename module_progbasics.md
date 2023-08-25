# Programming Basics questions

## 1. Data basics

---
---

### 1.1. What are the differences between objects and arrays? What is the purpose of the object and what is the purpose of the array?

* ORDER

  - an object in JavaScript is an unordered collection of key-value pairs, where each key (also known as a property) is a string or a symbol, and each value can be of any data type, including other objects or functions
  - an array in JavaScript is an ordered list-like collection of values, where each value is identified by its index, starting from 0

* ACCESSING VALUES

  - object properties are accessed using their keys (e.g., object.name)
  - array elements are accessed using numeric indices (e.g., array[0])

* PURPOSE

  - objects are useful when you want to store and organize data in a way that reflects real-world entities; they provide a convenient way to group related information together and allow you to access values using descriptive keys
  - arrays are particularly useful when you need to work with a collection of items that need to maintain a specific order or when you want to perform operations like iteration, filtering, or mapping over the elements

* ITERATING

  - objects require a loop or methods like Object.keys() or Object.values() for iterating over elements
  - arrays have built-in methods (e.g., forEach, map, filter) for iterating over elements

* USE CASES

  - use objects when you need to model entities with attributes and methods, such as a user, car, or product
  - use arrays when you need to manage ordered collections of data, such as a list of numbers, names, or tasks

* DATA STRUCTURE TYPE

  - objects are key-value pairs
  - arrays are indexed collections

It's important to choose the appropriate data structure based on your specific use case to ensure efficient and organized data management in your JavaScript code.

---

### 1.2. How can you access a key's value in an object?

You can access a key's value in an object using either dot notation or bracket notation using the key of the object.

e.g.

```javascript
const person = {
  name: "John",
  age: 30,
  isStudent: false,
};
```

* Dot Notation:
```javascript
// accessing the person object's name, which is "John"
console.log(person.name);
```
* Bracket Notation: 
```javascript
// exactly the same thing
console.log(person["name"]);
```


---

### 1.3. How can you access the first and the last item of an array?

We can access the first and last items of an array using their indices. In JavaScript, array indices start from 0 for the first element and go up to array.length - 1 for the last element. Here's how you we can access the first and last items of an array:

```javascript
const exampleArray = [1,2,3,4,5,6,7];

// accessing the first element:
   const firstIndex = 0;
   const firstElement = exampleArray[firstIndex];
// accessing the last element:
   const lastIndex = exampleArray.length - 1;
   const lastElement = exampleArray[lastIndex];
```
We have built in methods for get the first and last elements from an array, but these methods also remove the element from the array.

e.g.

```javascript
// the shift method remove the first element and also return it e.g
const firstElement = exampleArray.shift();
// exactly the same thing with the pop method, but this returns the last element e.g
const lastElement = exampleArray.pop();
```

---


### 1.4. Name all the primitive types in JavaScript.

In JavaScript, a primitive (primitive value, primitive data type) is data that is not an object and has no methods or properties.

There are 7 primitive data types:

* Boolean: Represents a binary value, true or false.

* Number: Represents both integer and floating-point numbers.

* String: Represents a sequence of characters, enclosed in single ('') or double ("") quotes.

* Null: Represents the intentional absence of any value or object.

* Undefined: Represents a declared variable that hasn't been assigned a value.

* Symbol: Represents a unique and immutable value that can be used as an identifier for object properties.

* BigInt: In JavaScript, BigInt is a numeric data type that can represent integers in the arbitrary precision format. In other programming languages different numeric types can exist, for examples: Integers, Floats, Doubles, or Bignums.

These primitive types are the basic building blocks for more complex data structures and objects in JavaScript.

---
---

## 2. Algorithm basics

---
---



### 2.1. What are the assignment operators? Name some of them.

An assignment operator assigns a value to its left operand based on the value of its right operand. The simple assignment operator is equal (=), which assigns the value of its right operand to its left operand. That is, x = f() is an assignment expression that assigns the value of f() to x.


* Assignment (=)
  - this operator is used to assign a value to a variable
  - the assignment operation evaluates to the assigned value
  - chaining the assignment operator is possible in order to assign a single value to multiple variables
e.g.
```javascript
let x = 2;

console.log(x);
// Expected output: 2

```
* Addition assignment (+=) 
  - performs addition (which is either numeric addition or string concatenation) on the two operands and assigns the result to the left operand.
e.g.
```javascript
let a = 2;
let b = 'hello';

console.log((a += 3)); // Addition
// Expected output: 5

console.log((b += ' world')); // Concatenation
// Expected output: "hello world"
```
* The subtraction assignment (-=) 
  - performs subtraction on the two operands and assigns the result to the left operand
e.g.
```javascript
let a = 2;

console.log((a -= 3));
// Expected output: -1
```
* Multiplication assignment (*=)
  - performs multiplication on the two operands and assigns the result to the left operand
e.g.
```javascript
let a = 2;

console.log((a *= 3));
// Expected output: 6
```

* Division assignment (/=)
  - performs division on the two operands and assigns the result to the left operand
e.g.
```javascript
let a = 3;

a /= 2;
console.log(a);
// Expected output: 1.5

a /= 0;
console.log(a);
// Expected output: Infinity
```

* Remainder assignment (%=)
  - performs remainder on the two operands and assigns the result to the left operand
e.g.
```javascript
let a = 3;

console.log((a %= 2));
// Expected output: 1

console.log((a %= 0));
// Expected output: NaN
```

* Exponentiation assignment (**=)
  - performs exponentiation on the two operands and assigns the result to the left operand
e.g.
```javascript
let a = 3;

console.log((a **= 2));
// Expected output: 9

console.log((a **= 0));
// Expected output: 1
```

* Left shift assignment (<<=)
  - performs left shift on the two operands and assigns the result to the left operand
  - returns a number or BigInt whose binary representation is the first operand shifted by the specified number of bits to the left;
excess bits shifted off to the left are discarded, and zero bits are shifted in from the right
e.g.
```javascript
let a = 5; // 00000000000000000000000000000101
const b = 2; // 00000000000000000000000000000010
a <<= b; // 00000000000000000000000000010100

console.log(a);
// Expected output: 20
```

* Right shift assignment (>>=)
  - performs right shift on the two operands and assigns the result to the left operand
  - returns a number or BigInt whose binary representation is the first operand shifted by the specified number of bits to the right; excess bits shifted off to the right are discarded, and copies of the leftmost bit are shifted in from the left;
this operation is also called "sign-propagating right shift" or "arithmetic right shift", because the sign of the resulting number is the same as the sign of the first operand
e.g.
```javascript
let a = 5; //  00000000000000000000000000000101
const b = 2; //  00000000000000000000000000000010
a >>= b; //  00000000000000000000000000000001
console.log(a);
// Expected output: 1

let b = -5; //  11111111111111111111111111111011
b >>= b; //  11111111111111111111111111111110
console.log(b);
// Expected output: -2
```

* Unsigned right shift assignment (>>>=)
  - performs unsigned right shift on the two operands and assigns the result to the left operand
  - returns a number whose binary representation is the first operand shifted by the specified number of bits to the right;
excess bits shifted off to the right are discarded, and zero bits are shifted in from the left;
this operation is also called "zero-filling right shift", because the sign bit becomes 0, so the resulting number is always positive;unsigned right shift does not accept BigInt values
e.g.
```javascript
const a = 5; //  00000000000000000000000000000101
const b = 2; //  00000000000000000000000000000010
const c = -5; //  11111111111111111111111111111011

a >>>= b; //  00000000000000000000000000000001
console.log(a);
// Expected output: 1
c >>>= b; //  00111111111111111111111111111110
console.log(b);
// Expected output: 1073741822
```

* Bitwise AND assignment (&=)
  - operator performs bitwise AND on the two operands and assigns the result to the left operand
  - returns a number or BigInt whose binary representation has a 1 in each bit position for which the corresponding bits of both operands are 1
e.g.
```javascript
let a = 5; // 00000000000000000000000000000101
a &= 3; // 00000000000000000000000000000011

console.log(a); // 00000000000000000000000000000001
// Expected output: 1
```

* Bitwise XOR assignment (^=)
  - operator performs bitwise XOR on the two operands and assigns the result to the left operand
  - returns a number or BigInt whose binary representation has a 1 in each bit position for which the corresponding bits of either but not both operands are 1
e.g.
```javascript
let a = 5; // 00000000000000000000000000000101
a ^= 3; // 00000000000000000000000000000011

console.log(a); // 00000000000000000000000000000110
// Expected output: 6
```

* Bitwise OR assignment (|=)
  - performs bitwise OR on the two operands and assigns the result to the left operand
  - returns a number or BigInt whose binary representation has a 1 in each bit position for which the corresponding bits of either or both operands are 1
e.g.
```javascript
let a = 5; // 00000000000000000000000000000101
a |= 3; // 00000000000000000000000000000011

console.log(a); // 00000000000000000000000000000111
// Expected output: 7
```

* Logical AND assignment (&&=)
  - only evaluates the right operand and assigns to the left if the left operand is truthy
e.g.
```javascript
let a = true;
let b = false;

a &&= 2;
console.log(a);
// Expected output: 2

b &&= 2;
console.log(b);
// Expected output: 0
```

* Logical OR assignment (||=)
  - only evaluates the right operand and assigns to the left if the left operand is falsy
e.g.
```javascript
const a = { duration: 50, title: '' };

a.duration ||= 10;
console.log(a.duration);
// Expected output: 50

a.title ||= 'title is empty.';
console.log(a.title);
// Expected output: "title is empty"
```

* Nullish coalescing assignment (??=)
  - also known as the logical nullish assignment operator, only evaluates the right operand and assigns to the left if the left operand is nullish (null or undefined)
e.g.
```javascript
const a = { duration: 50 };

a.duration ??= 10;
console.log(a.duration);
// Expected output: 50

a.speed ??= 25;
console.log(a.speed);
// Expected output: 25
```


---

### 2.2. What are the arithmetic operators? Name some of them.

Arithmetic operators perform arithmetic on numbers (literals or variables).
The numbers (in an arithmetic operation) are called operands.
The operation (to be performed between the two operands) is defined by an operator.
e.g.
```javascript
let operand1 = 100;
let operand2 = 50;
console.log(operator1 + operator2)
// expected output: 150, the operator is '+'
```


* Addition (+)
  - the addition operator adds numbers
e.g.
```javascript
let x = 5;
let y = 2;
console.log(x + y)
// expected output: 7
```

* Subtraction (-)
  - the subtraction operator subtracts numbers
e.g.
```javascript
let x = 5;
let y = 2;
console.log(x - y);
// expected output: 3
```
* Multiplication (*)
  - the multiplication operator multiplies numbers
e.g.
```javascript
let x = 5;
let y = 2;
console.log(x * y)
// expected output: 10
```
* Exponentiation (ES2016) (**)
  - the exponentiation operator raises the first operand to the power of the second operand
e.g.
```javascript
let x = 5;
let y = 2;
console.log(x ** y)
// expected output: 25
```
* Division (/)
  - the division operator divides numbers
e.g.
```javascript
let x = 5;
let y = 2;
console.log(x / y)
// expected output: 2.5
```
* Modulus (Remainder) (%)
  - the modulus operator returns the division remainder
e.g.
```javascript
let x = 5;
let y = 2;
console.log(x % y)
// expected output: 1
```
* Increment (++)
  - the increment operator increments numbers
e.g.
```javascript
let x = 5;
x++;
console.log(x)
// expected output: 6
```
* Decrement (--)
  - the decrement operator decrements numbers
e.g.
```javascript
let x = 5;
x--;
console.log(x)
// expected output: 4
```
* Unary negation (-)
  - precedes its operand and negates it
e.g.
```javascript
const x = 4;
const y = -x;

console.log(y);
// Expected output: -4

const a = '4';
const b = -a;

console.log(b);
// Expected output: -4
```
* Unary plus (+)
  - precedes its operand and evaluates to its operand but attempts to convert it into a number, if it isn't already
e.g.
```javascript
const x = 1;
const y = -1;

console.log(+x);
// Expected output: 1

console.log(+y);
// Expected output: -1

console.log(+'');
// Expected output: 0

console.log(+true);
// Expected output: 1

console.log(+false);
// Expected output: 0

console.log(+'hello');
// Expected output: NaN
```



Multiplication (*) and division (/) have higher precedence than addition (+) and subtraction (-).
And (as in school mathematics) the precedence can be changed by using parentheses.
e.g.
```javascript
let x = (100 + 50) * 3;
console.log(x);
// expected output: 450
```


---

### 2.3. What are the comparison operators? Name some of them.

A comparison operator compares its operands and returns a logical value based on whether the comparison is true.
The operands can be numerical, string, logical, or object values.
Strings are compared based on standard lexicographical ordering, using Unicode values.

* Equal (==)
  - checks whether its two operands are equal, returning a Boolean result
  - unlike the strict equality operator, it attempts to convert and compare operands that are of different types
e.g.
```javascript
console.log(1 == 1);
// Expected output: true

console.log('hello' == 'hello');
// Expected output: true

console.log('1' == 1);
// Expected output: true

console.log(0 == false);
// Expected output: true
```
* Not equal (!=)
  - checks whether its two operands are not equal, returning a Boolean result
  - unlike the strict inequality operator, it attempts to convert and compare operands that are of different types
e.g.
```javascript
console.log(1 != 1);
// Expected output: false

console.log('hello' != 'hello');
// Expected output: false

console.log('1' != 1);
// Expected output: false

console.log(0 != false);
// Expected output: false
```
* Strict equal (===)
  - checks whether its two operands are equal, returning a Boolean result
  - unlike the equality operator, the strict equality operator always considers operands of different types to be different
e.g.
```javascript
console.log(1 === 1);
// Expected output: true

console.log('hello' === 'hello');
// Expected output: true

console.log('1' === 1);
// Expected output: false

console.log(0 === false);
// Expected output: false
```
* Strict not equal (!==)
  - checks whether its two operands are not equal, returning a Boolean result
  - unlike the inequality operator, the strict inequality operator always considers operands of different types to be different
e.g.
```javascript
console.log(1 !== 1);
// Expected output: false

console.log('hello' !== 'hello');
// Expected output: false

console.log('1' !== 1);
// Expected output: true

console.log(0 !== false);
// Expected output: true
```
* Greater than (>)
  - returns true if the left operand is greater than the right operand, and false otherwise
e.g.
```javascript
console.log(5 > 3);
// Expected output: true

console.log(3 > 3);
// Expected output: false

// Compare bigint to number
console.log(3n > 5);
// Expected output: false

console.log('ab' > 'aa');
// Expected output: true
```
* Greater than or equal (>=)
  - returns true if the left operand is greater than or equal to the right operand, and false otherwise
e.g.
```javascript
console.log(5 >= 3);
// Expected output: true

console.log(3 >= 3);
// Expected output: true

// Compare bigint to number
console.log(3n >= 5);
// Expected output: false

console.log('ab' >= 'aa');
// Expected output: true
```
* Less than (<)
  - returns true if the left operand is less than the right operand, and false otherwise
e.g.
```javascript
console.log(5 < 3);
// Expected output: false

console.log(3 < 3);
// Expected output: false

// Compare bigint to number
console.log(3n < 5);
// Expected output: true

console.log('aa' < 'ab');
// Expected output: true
```
* Less than or equal (<=)
  - returns true if the left operand is less than or equal to the right operand, and false otherwise
e.g.
```javascript
console.log(5 <= 3);
// Expected output: false

console.log(3 <= 3);
// Expected output: true

// Compare bigint to number
console.log(3n <= 5);
// Expected output: true

console.log('aa' <= 'ab');
// Expected output: true
```
JavaScript attempts to convert them to an appropriate type for the comparison. This behavior generally results in comparing the operands numerically. The sole exceptions to type conversion within comparisons involve the === and !== operators, which perform strict equality and inequality comparisons. These operators do not attempt to convert the operands to compatible types before checking equality.

---


### 2.4. What are the logical operators? Name some of them.

Logical operators are typically used with Boolean (logical) values; when they are, they return a Boolean value. However, the && and || operators actually return the value of one of the specified operands, so if these operators are used with non-Boolean values, they may return a non-Boolean value.

* Logical AND (&&)
  - for a set of boolean operands will be true if and only if all the operands are true, otherwise it will be false
e.g.
```javascript
const a = 3;
const b = -2;

console.log(a > 0 && b > 0);
// Expected output: false
```
* Logical OR (||)
  - for a set of operands is true if and only if one or more of its operands is true
  - typically used with boolean (logical) values
  - the || operator actually returns the value of one of the specified operands, so if this operator is used with non-Boolean values, it will return a non-Boolean value, else it will return a Boolean value
e.g.
```javascript
const a = 3;
const b = -2;

console.log(a > 0 || b > 0);
// Expected output: true
```
* Logical NOT (!)
  - takes truth to falsity and vice versa
  - typically used with boolean (logical) values
  - when used with non-Boolean values, it returns false if its single operand can be converted to true; otherwise, returns true
e.g.
```javascript
const a = 3;
const b = -2;

console.log(!(a > 0 || b > 0));
// Expected output: false
```

---


### 2.5. What is the difference between `for`, `for of` and `for in`?

* 'for'
  - creates a loop that consists of three optional expressions, enclosed in parentheses and separated by semicolons, followed by a statement (usually a block statement) to be executed in the loop
e.g.
```javascript
let str = '';

for (let i = 0; i < 9; i++) {
  str = str + i;
}

console.log(str);
// Expected output: "012345678"
```
* 'for in'
  - iterates over all enumerable string properties of an object (ignoring properties keyed by symbols), including inherited enumerable properties
e.g.
```javascript
const object = { a: 1, b: 2, c: 3 };

for (const property in object) {
  console.log(`${property}: ${object[property]}`);
}

// Expected output:
// "a: 1"
// "b: 2"
// "c: 3"
```
* 'for of'
  - executes a loop that operates on a sequence of values sourced from an iterable object
  - iterable objects include instances of built-ins such as Array, String, TypedArray, Map, Set, NodeList (and other DOM collections), as well as the arguments object, generators produced by generator functions, and user-defined iterables
e.g.
```javascript
const array1 = ['a', 'b', 'c'];

for (const element of array1) {
  console.log(element);
}

// Expected output: "a"
// Expected output: "b"
// Expected output: "c"
```
In summary:

- Use the for loop when you need to iterate a specific number of times
- Use the for...of loop to iterate over values of iterable objects
- Use the for...in loop to iterate over enumerable properties of objects (there are other methods like Object.keys() or Object.entries() for safer iteration over object properties)


---


### 2.6. How do you find the average of values in an array if you can’t use any built-in functions or methods?

We can find the average of values in an array without using any built-in functions or methods by manually summing up the values and then dividing by the number of values.
e.g.
```javascript
function calculateAverage(arr) {
  if (arr.length === 0) {
    return 0; // Handle the case of an empty array
  }
  // create a variable for the total amount
  let sum = 0;
  // loop through the array and add all values to the sum
  for (let i = 0; i < arr.length; i++) {
    sum += arr[i];
  }
  // divide the sum with the array length
  return sum / arr.length;
}
// test the function with this example array
const numbers = [5, 10, 15, 20, 25];
// call the function
const average = calculateAverage(numbers);
console.log(average);
// expected output: 15
```
In this example, the calculateAverage function takes an array as input, iterates through each element in the array, and accumulates the sum of all values. Finally, it divides the sum by the length of the array to calculate the average.


---
---


## 3. Function basics

---
---


### 3.1. What are the main parts of a function?

* Function Signature/Declaration: This is where you specify the function's name and its parameters (if any). The function name is used to call the function, and parameters are inputs that the function operates on.

* Parameters/Arguments: Parameters are variables declared in the function signature that act as placeholders for values that will be passed to the function when it is called. Arguments are the actual values passed to the function when it is invoked.

* Function Body: This is the block of code enclosed within curly braces {} that defines what the function does. It contains the instructions and logic that will be executed when the function is called.

* Return Statement: Many functions in programming return a value after performing their tasks. The return statement is used to specify the value that the function will produce and send back to the caller.

e.g.
```javascript
// functuion declaration with the 'function' and the name is 'addNumbers'
// the parameters is inside the parentheses, 'a' and 'b'
function addNumbers(a, b){
  const result = a + b; // this is the function body, contains the addition logic
  return result; // this is the return, returns the result after performing the task
}
const num1 = 2;
const num2 = 3;
// this is the function call, insert the arguments and store the result inside a constant
const additionResult = addNumbers(num1, num2);
console.log(additionResult);
// expected output: 5
```

---

### 3.2. What is the difference between parameters and arguments?
* Parameters are variables listed in the function declaration. They act as placeholders for the values that will be passed to the function when it's called. Parameters are part of the function's signature and are defined within the parentheses following the function name.
e.g.
```javascript
function addNumbers(a, b) {
    return a + b;
}

```
In this example, 'a' and 'b' are parameters. They define the inputs the function expects to work with.

* Arguments are the actual values that are passed to the function when it is called. They are the concrete values that correspond to the parameters defined in the function signature.
e.g.
```javascript
const result = addNumbers(3, 5);
```
In this case, 3 and 5 are arguments. They are the values being passed to the addNumbers function to be used as the a and b parameters.

In summary, parameters are the placeholders defined in the function declaration, while arguments are the actual values passed to the function when invoking it. The terms are often used together because they represent the connection between the function's expectations (parameters) and the data provided (arguments) when calling the function.

---


### 3.3. What are the differences between function expression and function statement?

In JavaScript, both function expressions and function statements are ways to define functions, but they have some differences in terms of how they are created and how they behave.

#### Function Expression:
* A function expression is created by assigning a function to a variable. It involves defining an anonymous function (a function without a name) and then assigning it to a variable. Function expressions are typically used when you want to create a function on the fly or pass it as an argument to another function.

e.g.
```javascript
const add = function(a, b) {
    return a + b;
};

// Calling the function
const sum = add(3, 5);
```

Key characteristics of function expressions:

    - The function doesn't need to have a name (anonymous function).
    - The function is assigned to a variable.
    - The function is only available after the line where it is defined.

#### Function Statement (Function Declaration):
* A function statement, also known as a function declaration, defines a named function in the current scope. It's created using the function keyword followed by the function name and parameters.

e.g.
```javascript
function multiply(x, y) {
    return x * y;
}

// Calling the function
const product = multiply(4, 6);
```

Key characteristics of function statements:

    - The function has a name.
    - The function is hoisted to the top of its scope during the creation phase, so it can be called before its actual declaration.
    - The function is available throughout the entire scope in which it is defined.

In summary, the main differences between function expressions and function statements are related to their naming, hoisting behavior, and the scope in which they are available. Function expressions provide more flexibility, especially when dealing with anonymous functions or functions as values, while function statements have the advantage of being hoisted and being available throughout their scope.

---
---

## 4. OOP Basics

---
---


### 4.1. What is a method?

In JavaScript, a method is a function that is associated with an object. It allows you to define behavior or actions that can be performed on or with the object. Methods are an integral part of object-oriented programming in JavaScript and are used to encapsulate functionality and data manipulation within objects.
e.g.
```javascript
// Define an object with a method
const person = {
  firstName: "John",
  lastName: "Doe",
  fullName: function() {
    return this.firstName + " " + this.lastName;
  }
};

// Calling the method
console.log(person.fullName()); // Output: "John Doe"
```
Methods are a crucial concept in JavaScript programming as they allow you to create reusable and organized code by associating functions with specific objects.

---

### 4.2. Name 3 builtin functions (and/or methods) regarding strings.

JavaScript provides various built-in methods for different types of objects. For strings have methods like toUpperCase, toLowerCase, charAt, and many more.

* toUpperCase:
  - converts all characters in a string to uppercase
```javascript
const originalString = "hello, world!";
const upperCaseString = originalString.toUpperCase();
console.log(upperCaseString); // Output: "HELLO, WORLD!"
```
* toLowerCase:
  - converts all characters in a string to lowercase
```javascript
const originalString = "Hello, World!";
const lowerCaseString = originalString.toLowerCase();
console.log(lowerCaseString); // Output: "hello, world!"
```
* charAt:
  - returns the character at a specified index in the string. Indexing starts from 0
```javascript
const myString = "JavaScript";
const charAtIndex = myString.charAt(4); // Get character at index 4
console.log(charAtIndex); // Output: "S"
```

These methods provide convenient ways to transform and access characters within strings.

---

### 4.3. Name 3 builtin functions (and/or methods) regarding arrays.

For arrays have methods like push, pop, splice, and many more.

* push:
  - adds one or more elements to the end of an array and returns the new length of the array
```javascript
const fruits = ['apple', 'banana', 'orange'];
fruits.push('grape');
console.log(fruits); // Output: ['apple', 'banana', 'orange', 'grape']
```
* pop:
  - removes the last element from an array and returns that element
```javascript
const numbers = [1, 2, 3, 4, 5];
const removedNumber = numbers.pop();
console.log(removedNumber); // Output: 5 (the pop returns the removed item)
console.log(numbers); // Output: [1, 2, 3, 4] (the pop change the original array)
```
* splice:
  - changes the contents of an array by removing or replacing existing elements and/or adding new elements in place
```javascript
const colors = ['red', 'green', 'blue'];
colors.splice(1, 1, 'yellow'); // Replace 'green' with 'yellow' (if we don't have a third parameter, the method only remove the item)
console.log(colors); // Output: ['red', 'yellow', 'blue']
```

Arrays are a fundamental data structure in the language, and these methods help you perform various operations on arrays efficiently.

---

### 4.4. Name 3 builtin functions (and/or methods) regarding numbers.

For numbers have methods like toFixed, parseInt, Math.random, and many more.

* toFixed:
  - converts a number to a string, rounding it to a specified number of decimal places, and returns the result
```javascript
const pi = 3.14159;
const roundedPi = pi.toFixed(2); // Round to 2 decimal places
console.log(roundedPi); // Output: "3.14"
```
* parseInt:
  - parses a string and returns an integer
```javascript
const binaryString = "101010";
const decimalValue = parseInt(binaryString, 2); // Parse binary string as decimal
console.log(decimalValue); // Output: 42
```
* Math.random:
  - generates a random floating-point number between 0 (inclusive) and 1 (exclusive)
```javascript
const randomValue = Math.random();
console.log(randomValue); // Output: A random value between 0 and 1
```

JavaScript provides a wide range of mathematical functions and methods in the Math object, allowing you to perform various calculations and manipulations with numbers.

---
---

## 5. FP Basics

### 5.1. What is a callback function?

In JavaScript, a callback function is a function that is passed as an argument to another function and is intended to be executed or called later, usually after a specific operation or event has occurred. Callback functions are commonly used in asynchronous programming to handle tasks that may take some time to complete, such as fetching data from a server, reading files, or responding to user interactions.
e.g.
```javascript
function doSomethingAsync(callback) {
  // Simulate an asynchronous operation (e.g., fetching data)
  console.log("Fetching data");
  setTimeout(function() {
    console.log("Async operation completed");
    callback(); // Call the callback function
  }, 1000); // Wait for 1 second
}

function handleCallback() {
  console.log("Callback function executed");
}

doSomethingAsync(handleCallback); // Pass handleCallback as a callback
```
In this example, doSomethingAsync is a function that takes a callback function as an argument. It simulates an asynchronous operation using setTimeout, and after the operation is completed, it calls the provided callback function.

Callback functions are essential for managing the flow of asynchronous code and enabling non-blocking behavior in JavaScript applications. They are commonly used in scenarios like event handling, AJAX requests, timers, and more.


---

### 5.2. What are the differences between `for` loops and `forEach`?

Both for loops and the forEach method are used in JavaScript for iterating over arrays. However, they have some differences in terms of syntax, behavior, and use cases.

* Syntax:
  - 'for' loop:
    ```javascript
    for (initialization; condition; iteration) {
      // code to be executed in each iteration
    }
    ```
  - 'forEach' method:
    ```javascript
    array.forEach(function(element, index, array) {
      // code to be executed for each element
    });
    ```
* Use Cases:
  - 'for' loop:
    - offers more flexibility and control over the iteration process
    - can be used for various types of loops, not just iterating over arrays (e.g., counting, stepping, etc.)
  - 'forEach' method:
    - designed specifically for iterating over arrays
    - provides a simpler and more concise syntax for iterating through array elements
* Break/Continue:
  - 'for' loop:
    - can use break and continue statements to control the loop flow
  - 'forEach' method:
    - cannot use break or continue statements to alter the loop flow
* Return Value:
  - 'for' loop:
    - can be used to create and return a value based on the iteration process
  - 'forEach' method:
    - does not return a value, it's meant for side effects (e.g., updating elements, logging, etc.)
* Compatibility:
  - 'for' loop:
    - supported in all JavaScript environments and versions
  - 'forEach' method:
    - introduced in ECMAScript 5 (ES5), so it might not be available in older browsers or environments

e.g.
* using 'for' loop:
```javascript
const numbers = [1, 2, 3, 4, 5];
let sum = 0;
// initialization; condition; iteration
for (let i = 0; i < numbers.length; i++) {
  sum += numbers[i];
}

console.log(sum); // Output: 15
```
* using 'forEach' method:
```javascript
const numbers = [1, 2, 3, 4, 5];
let sum = 0;
// element, index, array
numbers.forEach(function(number, index, array) {
  sum += number;
  // this is the index of the element and the whole array
  console.log(index, array);
});

console.log(sum); // Output: 15
```
In general, if we need more control over the iteration process or we have to use loop constructs beyond simple array iteration, for loops can be more appropriate. On the other hand, if we simply iterating over an array and performing some operation on each element, the forEach method provides a more concise and expressive syntax.


---
---

## 6. File basics

---
---


### 6.1. What is the difference between JavaScript data structures and JSON data structures?

JavaScript data structures and JSON (JavaScript Object Notation) data structures are related concepts, but they serve different purposes and have distinct characteristics.

#### JavaScript Data Structures:
  JavaScript data structures refer to the various ways you can organize and store data within a JavaScript program. These data structures are native to the JavaScript language and provide mechanisms for storing, manipulating, and accessing data. Some common JavaScript data structures include:

  - Arrays: Ordered lists of values that can be of different data types.
  - Objects: Collections of key-value pairs, where keys are strings and values can be of any data type.
  - Maps: Data structures that allow you to store key-value pairs where keys can have various data types, not just strings.
  - Sets: Collections of unique values.
  - Strings: Sequences of characters.
  - Numbers: Numeric data types, including integers and floating-point numbers.
  These JavaScript data structures are used to represent and work with data within the JavaScript runtime environment.

#### JSON Data Structures:
  JSON (JavaScript Object Notation) is a lightweight data interchange format. JSON data structures are a subset of JavaScript data structures, optimized for data serialization and communication. JSON is primarily used to represent structured data as text and is widely supported across different programming languages.
  JSON data structures consist of two main types:

  - Objects: Similar to JavaScript objects, these are collections of key-value pairs, where keys are strings and values can be strings, numbers, booleans, objects, arrays, or null.
  - Arrays: Similar to JavaScript arrays, these are ordered lists of values, which can be strings, numbers, booleans, objects, arrays, or null.

While JSON data structures are inspired by JavaScript objects and arrays, they are designed to be simple, easy to read, and easy to parse by both humans and machines. JSON does not support more complex data types like functions or custom prototypes, which can be found in native JavaScript objects.

In summary, JavaScript data structures are the building blocks used within JavaScript programs to organize and manipulate data, while JSON data structures are a specific format used for data interchange and communication, often between different systems or platforms.

---


### 6.2. How do you create JavaScript data structure from a JSON file's data?

#### Read the JSON File:
Use appropriate methods to read the content of the JSON file. In a Node.js environment, you can use the built-in fs module.

#### Parse JSON Data:
Parse the read JSON content using the JSON.parse() function. This will convert the JSON text into JavaScript objects or arrays.

#### Use the Parsed Data:
Once the JSON data is parsed, you can work with the resulting JavaScript objects or arrays just like you would with any other JavaScript data structures.

e.g.
```javascript
// Example JSON file content (data.json)
// {
//   "name": "John",
//   "age": 30,
//   "city": "New York"
// }

// import the fs module
import * as fs from 'node:fs';

// Read the JSON file (filename, encoding)
fs.readFile('data.json', 'utf8', (err, data) => {
  if (err) {
    // handling the errors, if the error is true
    console.error('Error reading JSON file:', err);
    return;
  }

  // Parse JSON data
  try {
    const jsonData = JSON.parse(data);

    // Use the parsed data
    console.log(jsonData.name); // Output: John
    console.log(jsonData.age);  // Output: 30
    console.log(jsonData.city); // Output: New York

    // You can create JavaScript data structures using the parsed data
    const person = {
      name: jsonData.name,
      age: jsonData.age,
      address: {
        city: jsonData.city
      }
    };

    console.log(person); // Output: { name: 'John', age: 30, address: { city: 'New York' } }
  } catch (parseError) {
    // handling the errors during the json parse
    console.error('Error parsing JSON data:', parseError);
  }
});
```

---
---

## 7. View Basics

### 7.1. What is the difference between JavaScript data structures and DOM (HTML document) data structures?

#### JavaScript Data Structures:
  JavaScript data structures refer to the various ways data can be organized and manipulated within the JavaScript programming language. These data structures are used to store and manage information in memory, making it easier to perform operations and computations on that data. Some common JavaScript data structures include:

  - Arrays: Ordered collections of elements accessed by numerical indices.
  - Objects: Key-value pairs where keys are strings and values can be any data type, including other objects and functions.
  - Sets: Collections of unique values, where each value can occur only once.
  - Strings: Sequences of characters used to represent text.
  - Numbers: Numeric data types used for mathematical operations.
  - Booleans: Data types representing true or false values.
  - Functions: Blocks of reusable code that can be invoked by name.

#### DOM Data Structures:
  The Document Object Model (DOM) is a programming interface for web documents. It represents the structure and content of an HTML document as a tree of objects. The DOM provides a way for programming languages, like JavaScript, to interact with and manipulate the content and structure of a webpage. DOM data structures include objects that represent elements, attributes, text, and other parts of an HTML document. Some important DOM data structures include:

  - Document: Represents the entire HTML document and provides methods to access and manipulate its content.
  - Element: Represents individual HTML elements (e.g., `<div>`, `<p>`, `<a>`) and provides methods and properties to manipulate their attributes and content.
  - TextNode: Represents textual content within an HTML element.
  - Attribute: Represents attributes of an HTML element (e.g., class, id, src).
  - NodeList: A collection of nodes returned by various DOM methods, often representing groups of elements based on selectors.


In summary, JavaScript data structures are used to store and manipulate data within the JavaScript programming language, whereas DOM data structures are used to represent the structure and content of HTML documents and provide a way to interact with and manipulate web content using JavaScript. They work together in web development to enable dynamic and interactive web pages.


---

### 7.2. What are the steps of changing a HTML element's content with JavaScript?

To change the content of an HTML element using JavaScript, we will need to follow a few steps.

#### Select the Element:
  First, we need to select the HTML element that we want to change the content of. We can do this using various methods, such as using the element's ID, class, tag name, or other attributes. The most common methods for selecting elements are document.`getElementById()`, `document.querySelector()`, and `document.querySelectorAll()`.
e.g.
  ```javascript
  // Step 1: Select the element
  const paragraphElement = document.getElementById("myParagraph"); // select by id
  const divElement = document.querySelector(".myDiv"); // select by class name using queryselector
  ```

#### Modify the Content:
  Once you've selected the element, you can modify its content by accessing its innerHTML property or its textContent property. The innerHTML property allows you to set or retrieve the HTML content, including any HTML tags, while the textContent property deals with just the textual content, ignoring HTML tags.
  ```javascript
  // Step 2: Modify the content (using textContent)
  const newTextContent = "This is the updated text.";
  paragraphElement.textContent = newTextContent; // update the paragraph element's text
  // Modify the content (using innerHTML)
  const newHTMLContent = "<p>This is <strong>bold</strong> text.</p>";
  divElement.innerHTML = newHTMLContent; // update the div element's html
  ```



---
---

## 8. Event basics

---
---


### 8.1. What is an event listener?

An event listener is a programming construct in web development that allows you to "listen" for specific events or interactions that occur within a web page or application and then respond to those events with custom code. Events can be various user actions, like clicking a button, submitting a form, moving the mouse, pressing a key, or resizing the window. Event listeners enable you to create interactive and dynamic web experiences by executing specific actions or functions when certain events occur.

#### Attach an Event Listener:
  You attach an event listener to an HTML element (like a button, input field, or the entire document) using JavaScript. The event listener "listens" for a specific type of event on that element.

#### Specify the Event Type and Callback Function:
  When attaching an event listener, you specify the type of event you're interested in (e.g., "click," "submit," "keydown," etc.) and provide a callback function that will be executed when the event occurs.

#### Execute Custom Code:
  When the specified event occurs on the element, the associated callback function is triggered. This allows you to define custom behavior that should happen in response to the event.

e.g.
```javascript
// Select the button element
const myButton = document.getElementById("myButton");

// Attach an event listener for the "click" event
myButton.addEventListener("click", function() {
    // This code will run when the button is clicked
    console.log("Button clicked!");
});
```
In this example, when the button with the ID "myButton" is clicked, the provided callback function will be executed, and it will log "Button clicked!" to the browser's console.

Event listeners are fundamental for creating interactive and responsive web applications. They allow you to separate the behavior (JavaScript code) from the presentation (HTML and CSS), making your codebase more modular and maintainable. By responding to events, you can update content, trigger animations, make network requests, and perform other dynamic actions to enhance the user experience on your website.

---

### 8.2. What are the steps of changing a HTML element's content when the element clicked?

#### Select the Element:
  Choose the HTML element you want to make clickable and change its content. You can select the element using methods like document.`getElementById()`, `document.querySelector()`, or other DOM selection methods.

#### Attach an Event Listener:
  Attach an event listener to the selected element for the "click" event. This will listen for a click on the element and execute a specified callback function when the event occurs.

#### Define the Callback Function:
  Define a callback function that will be executed when the element is clicked. Inside this function, you can update the content of the element using JavaScript.

#### Update the Content:
  Within the callback function, modify the content of the selected element using its textContent or innerHTML property.

e.g.
```javascript
// Step 1: Select the element
const paragraphElement = document.getElementById("myParagraph");

// Step 2: Attach an event listener for the "click" event
paragraphElement.addEventListener("click", function() { // Step 3: Define the callback function
  // Step 4: Update the content
  paragraphElement.textContent = "Content changed!";
});
```
---

### 8.3. Inside a `click` event listener, how can you access the element that has been clicked?

Inside a click event listener, you can access the element that has been clicked using the event object that is automatically passed as an argument to the event handler function. This object contains information about the event, including the target element that triggered the event. The event.target property points to the DOM element that was clicked.

```javascript
// example HTML structure
<ul id="myList">
    <li>Item 1</li>
    <li>Item 2</li>
    <li>Item 3</li>
</ul>

// Select the element
const listElement = document.getElementById("myList");

// Attach an event listener for the "click" event
listElement.addEventListener("click", function(event) {
  // Access the clicked element using event.target
  const clickedElement = event.target;

  // Check if the clicked element is an <li> element
  if (clickedElement.tagName === "LI") {
      // Modify the content of the clicked <li>
      clickedElement.textContent = "Clicked!";
  }
});
```
In this example, when any `<li>` element within the `<ul>` with the ID "myList" is clicked, the event listener function is triggered. Inside the function, event.target points to the specific `<li>` element that was clicked.


---
---

## 9. Design Basics

---
---

### 9.1. What are the differences between `display: block` and `display: inline` CSS properties?

The `display` CSS property controls how an HTML element is rendered in terms of its layout and flow within the document.

#### `display: block`:

  - elements with display: block are rendered as block-level elements
  - they start on a new line and take up the full width available within their containing element
  - block-level elements ignore adjacent elements and stack vertically, one below the other
  - can set the height, width, margins, and padding of block-level elements
  - examples of block-level elements include `<div>`, `<p>`, `<h1>` to `<h6>`, `<ul>`, `<ol>`, `<li>`, and more

#### `display: inline`:

  - elements with display: inline are rendered as inline-level elements
  - they do not start on a new line and only take up as much width as necessary to contain their content
  - inline-level elements flow within the content of a line and respect the flow of adjacent elements
  - you cannot set the height, width, margins, or padding of inline-level elements horizontally
  - examples of inline-level elements include `<span>`, `<a>`, `<strong>`, `<em>`, `<img>`, and more

Visual representation:

```javascript
display: block                    display: inline
----------------------------       ----------------------------
| Block Element 1    |           | Inline Element 1 |
|                    |           | Inline Element 2 |
|                    |           | Inline Element 3 |
|                    |           | ...              |
----------------------------       ----------------------------
```


---

### 9.2. What are the differences between `position: relative` and `position: absolute` CSS properties?

The `position` CSS property is used to control the positioning of an HTML element within its containing element. Two common values for the `position` property are `relative` and `absolute`. 

#### `position: relative`:
  - When you set an element's position to relative, it remains within the normal flow of the document.
  - The element's original position is preserved, and any subsequent elements flow as if the positioned element was still in its original place.
  - You can use the top, right, bottom, and left properties to move the element from its original position relative to itself. These properties create a "box" around the element and move it within that box.
  - Elements with position: relative can also be used as the reference point for absolutely positioned child elements. Child elements with position: absolute will be positioned relative to the nearest ancestor with a non-static position (relative, absolute, or fixed).

#### `position: absolute`:
  - When an element is set to position: absolute, it is removed from the normal document flow and positioned relative to the nearest ancestor element that has a non-static position (i.e., relative, absolute, or fixed).
  - The top, right, bottom, and left properties are used to position the element relative to its nearest positioned ancestor. If no positioned ancestor is found, it will be positioned relative to the initial containing block (usually the viewport).
  - Other elements in the document flow will ignore the space occupied by an absolutely positioned element. This can lead to elements overlapping if not carefully managed.




---

### 9.3. What is the box model, name the CSS properties connecting to it?

The box model is a fundamental concept in web design and layout that describes how elements on a webpage are structured and how their dimensions are calculated. In the box model, every HTML element is treated as a rectangular box, and it consists of several layers:

#### CSS (Cascading Style Sheets) properties that connect to the box model are as follows:

  - `Width and Height`: These properties define the dimensions of the content box, excluding padding, border, and margin.
  - `Padding` (`padding-top`, `padding-right`, `padding-bottom`, `padding-left`): These properties control the amount of space between the content and the border.
  - `Border` (`border-width`, `border-style`, `border-color`): These properties allow you to set the width, style, and color of the border around the content.
  - `Margin` (`margin-top`, `margin-right`, `margin-bottom`, `margin-left`): These properties determine the amount of space between the element's border and other elements on the page.

It's important to note that the width and height you set for an element include its content area, but not its padding, border, or margin. The total space an element occupies on the page will be the sum of its width/height, padding, border, and margin.

The CSS box model can sometimes lead to unexpected layout behavior, especially when elements have margins or padding that affect their positioning. To mitigate these issues, CSS has introduced properties like `box-sizing`, which lets you control how an element's width and height are calculated (e.g., including or excluding padding and border).


---

### 9.4. What CSS properties affect font and text appearance?

Several CSS properties can be used to control the appearance of fonts and text on a webpage.
Some key properties that affect font and text appearance:
  - `font-family`: This property specifies the font or list of fonts to be used for text content. You can provide a comma-separated list of font family names, and the browser will use the first available font in the list.
  - `font-size`: This property sets the size of the font. It can be specified in various units, such as pixels, ems, rems, percentages, etc.
  - `font-weight`: This property controls the thickness or boldness of the font. Common values include "normal", "bold", "bolder", "lighter" or numeric values like 100, 200, ..., 900.
  - `font-style`: This property defines whether the text should be displayed in a normal, italic, or oblique style.
  - `text-align`: This property determines the horizontal alignment of the text within its container. Values can be "left", "right", "center" or "justify."
  - `text-decoration`: This property adds visual decorations to text, such as underlines, overlines, line-through, and blink effects.
  - `line-height`: This property sets the vertical space between lines of text. It's often used to improve readability and spacing.
  - `letter-spacing`: This property controls the spacing between characters. It can be used to adjust the tracking of text.
  - `word-spacing`: This property sets the spacing between words in a block of text.
  - `color`: This property defines the color of the text. You can use color names, hexadecimal values, RGB values, or other color representations.
  - `text-transform`: This property changes the capitalization of text. Values include "uppercase", "lowercase", "capitalize", and "none."
  - `text-shadow`: This property adds a shadow effect to the text. You can control the color, blur radius, and horizontal/vertical offset of the shadow.
  - `white-space`: This property controls how white spaces (spaces, tabs, and line breaks) are treated within the text. Values include "normal", "nowrap" and "pre."
  - `font`: The shorthand property font allows you to set several font-related properties in a single declaration. It includes properties like `font-style`, `font-variant`, `font-weight`, `font-size`, `line-height`, and `font-family`.

By using these properties effectively, we can create visually appealing and readable text content that aligns with our design goals.

---

### 9.5. What are the steps of adding or removing a HTML element's class name?

Adding or removing a class name from an HTML element involves interacting with the element's class attribute using JavaScript.

#### Modifying a Class Name:
  - Select the Element: Use a JavaScript method to select the HTML element to which you want to add a class. Common methods include `document.getElementById()`, `document.querySelector()`, or `document.getElementsByClassName()`.
  - Add the Class: Use the `classList.add()` method on the selected element to add the desired class name. The syntax is: `element.classList.add('classname')`.
  - Remove the Class: Use the `classList.remove()` method on the selected element to remove the desired class name. The syntax is: `element.classList.remove('classname')`.
  - Toggle the Class: Use the `classList.toggle()` method on the selected element. The syntax is: `element.classList.toggle('classname')`.
  e.g.
  ```javascript
  // Example: Adding a class named "highlight" to an element with ID "myElement"
  const element = document.getElementById('myElement');
  element.classList.add('highlight');
  // Example: Removing the class named "highlight" from an element with ID "myElement"
  const element = document.getElementById('myElement');
  element.classList.remove('highlight');
  // Example: Toggling the class named "active" on an element with ID "myButton"
  const button = document.getElementById('myButton');
  button.addEventListener('click', () => {
    button.classList.toggle('active');
  });
  ```

Additionally, the `classList` methods handle adding or removing class names in a way that avoids duplication or errors.

---
---


## 10. JavaScript - language specialties

---
---

### 10.1. What is the difference between value and reference data types in terms of object and primitives?

#### Primitive Data Types (Value Types):
  - Number: Represents both integer and floating-point numbers.
  - String: Represents sequences of characters.
  - Boolean: Represents true or false values.
  - Undefined: Represents a variable that has been declared but not assigned a value.
  - Null: Represents the intentional absence of any value.
  - Symbol (added in ECMAScript 6): Represents a unique and immutable value that can be used as an object property.

#### Reference Data Types (Objects):
  - Objects: Collections of key-value pairs where values can be primitives, other objects, or functions
  - Arrays: Ordered collections of elements accessed by numerical indices
  - Functions: Blocks of reusable code that can be invoked by name
  - Custom-defined data structures

#### Differences:
  - Mutability:
    * Primitive types are immutable; their values cannot be changed after creation.
    * Reference types are mutable; their properties and contents can be modified after creation.
      ```javascript
      // example for immutability and mutability
      let num = 5;
      let arr = [1,2,3,4,5];
      // Attempting to modify the values
      num = num + 2;    // A new value is created (7), num remains unchanged (5)
      arr[0] = 'modified'; // the array is modified, the first value is changed

      console.log(num);  // Outputs: 5
      console.log(arr); // Outputs: ['modified',2,3,4,5];
      ```
  - Copying:
    * When you copy a primitive type, you create a new independent copy with its own value.
    * When you copy a reference type, you create a new reference pointing to the same underlying object.
  - Passing to Functions:
    * When you pass a primitive type to a function, changes within the function do not affect the original value outside the function.
    * When you pass a reference type to a function, changes within the function can affect the original object outside the function.
      ```javascript
      let number = 10;
      let array = [1,2,3,4,5,6,7,8]
      function changeValues(num, arr){
        num += 5;
        arr.push('changed')
      }
      changeValues(number, array);
      console.log(number); // Outputs: 10
      console.log(array); // Outputs: [1,2,3,4,5,6,7,8, 'changed']
      ```
  - Memory Usage:
    * Primitive types generally consume less memory because they store actual values.
    * Reference types consume more memory because they store references to objects, and the objects themselves are stored elsewhere in memory.
e.g.
```javascript
let prim = 8;
let prim2 = prim; // prim2 have the value of prim
const obj1 = { value: 10 };
const obj2 = obj1; // obj2 references the same object as obj1

prim2 = 15; // this will not change the prim value
obj2.value = 20;   // This will change the value for obj1 as well

console.log(prim, obj1.value); // Outputs: 8, 20
```



---

### 10.2. Is `null` an object or a primitive?

In JavaScript, `null` is a primitive value, not an object. It represents the intentional absence of any value and is often used to indicate that a variable should have no value or that an object property is intentionally empty.

While `null` is a primitive value used to represent the absence of value, JavaScript incorrectly reports its type as an object due to the aforementioned issue with the `typeof` operator. However, it's important to remember that `null` itself is not an object, and it behaves like a primitive in most contexts.
```javascript
const value = null;
console.log(typeof value); // Outputs: "object"
```


---

### 10.3. What is `undefined`?

In JavaScript, `undefined` is a primitive value that indicates the absence of a defined value. It's often used to represent a variable that has been declared but has not been assigned a value, or to indicate the absence of a property within an object.

Few scenarios where `undefined` is commonly encountered:
- Declaring a Variable Without Assignment:
  - When you declare a variable without assigning a value to it, the variable's initial value is automatically set to `undefined`.
  ```javascript
  let variableWithoutValue;
  console.log(variableWithoutValue); // Outputs: undefined
  ```
- Accessing an Object Property that Doesn't Exist:
  - If you try to access a property that doesn't exist within an object, the result will be `undefined`.
  ```javascript
  const obj = { key: "value" };
  console.log(obj.nonExistentKey); // Outputs: undefined
  ```
- Implicit Return in Functions:
  - If a function doesn't explicitly return a value, its return value will be `undefined`.
  ```javascript
  function noReturnValue() {
  // no explicit return statement
  }
  console.log(noReturnValue()); // Outputs: undefined
  ```
- Function Parameters without Arguments:
  - If a function parameter is defined but not provided an argument when the function is called, it will have the value `undefined`.
  ```javascript
  function logValue(value) {
  console.log(value);
  }
  logValue(); // Outputs: undefined
  ```
- Array Elements Beyond Length:
  - Accessing an index beyond the length of an array will result in `undefined`.
  ```javascript
  const array = [1, 2, 3];
  console.log(array[10]); // Outputs: undefined
  ```

It's important to distinguish between null and undefined. While both represent the absence of a value, null is typically used when a value is explicitly set to indicate emptiness, while undefined usually arises when a value is not yet assigned or a property is not defined.

---

### 10.4. When to use `var`, `let`, and `const`?

In JavaScript, `var`, `let`, and `const` are used to declare variables. However, they have different behaviors and scopes, so choosing the appropriate one depends on the specific use case and your coding preferences.

- `var`:
  - `var` declarations are function-scoped or globally scoped, but not block-scoped like `let` and `const`.
  - Variables declared with `var` are hoisted to the top of their scope, which means you can use them before they're actually declared (though their values will be undefined).
  - Due to its function-scoped nature and potential for hoisting-related issues, `var` is considered outdated and is not recommended for modern JavaScript development. It's generally better to use `let` or `const`.
- `let`:
  - `let` declarations are block-scoped. They are confined to the block (code within curly braces) in which they are declared.
  - Variables declared with `let` are not hoisted to the top of their scope. They are only accessible after their declaration.
  - Use `let` when you need to reassign the variable's value. It's a good choice for variables that will change their values during their lifecycle.
- `const`:
  - `const` declarations are also block-scoped, just like `let`.
  - Variables declared with `const` cannot be reassigned after their initial assignment. However, it's important to note that the immutability of `const` only applies to the binding between the variable name and the value it holds, not the value itself if the value is mutable (like an object or array).
  - Use `const` when you have a value that should not be reassigned and does not change its identity throughout the program's execution.
---

### 10.5. What is hoisting?

Hoisting is a behavior in JavaScript where variable and function declarations are moved to the top of their containing scope during the compilation phase, before the actual code execution. This can lead to some unexpected results and behaviors if not understood correctly.

#### Variable Declarations:
When a variable is declared using `var`, the declaration is hoisted to the top of the function or global scope. However, the assignment (initialization) of the variable remains in its original place.
```javascript
console.log(myVariable); // Outputs: undefined
var myVariable = 10;
// The code above is actually interpreted by JavaScript as:
var myVariable;
console.log(myVariable); // Outputs: undefined
myVariable = 10;
```
#### Function Declarations:
Function declarations are also hoisted to the top of their scope, so you can call a function before declaring it.
```javascript
sayHello(); // Outputs: "Hello!"
function sayHello() {
  console.log("Hello!");
}
// This is possible because function declarations are completely hoisted, including their body.
```
#### Function Expressions:
Function expressions (when a function is assigned to a variable) are not hoisted in the same way as function declarations. Only the variable declaration is hoisted, not the function itself.
```javascript
console.log(sayHello) // Outputs: "Undefined"
sayHello(); // Throws an error: "sayHello is not a function"
var sayHello = function() {
  console.log("Hello!");
};
// In this case, only the variable 'sayHello' is hoisted, but its value (the function) is not assigned until the original declaration is encountered during runtime.
```

Hoisting can sometimes lead to confusion and bugs, especially if you're not aware of this behavior. It's recommended to follow best practices to avoid issues related to hoisting:

- Declare variables at the beginning of their scope to make code behavior clearer.
- Always declare variables before using them to avoid relying on hoisting behavior.
- Be aware of the differences between function declarations and function expressions.


---
---

## 11. Git

---
---


### 11.1 What are the advantages of using a version control system?

Version Control Systems (VCS) offer numerous advantages for individuals and teams involved in software development and collaborative projects.

- History and Version Tracking:
  * VCS allows you to track changes to your code over time. Each commit represents a snapshot of the codebase at a specific point, along with the changes made. This history helps in understanding the evolution of the project and can be used to troubleshoot issues.

- Collaboration:
  * VCS enables multiple developers to work on the same project simultaneously. It provides mechanisms to merge and manage changes made by different team members, preventing conflicts and ensuring that everyone is working on the latest version of the code.

- Conflict Resolution:
  * When multiple people are making changes to the same file or codebase, conflicts can arise. VCS tools provide methods for detecting and resolving these conflicts, ensuring that changes are combined in a controlled and organized manner.

- Branching and Merging:
  * VCS allows you to create branches, which are separate lines of development that can be used for feature development, bug fixes, or experimentation. These branches can be merged back into the main codebase once the changes are complete.

- Code Review and Collaboration Workflow:
  * VCS supports code review workflows, where changes are reviewed before being merged into the main codebase. This improves code quality and ensures that best practices are followed.

- Revert to Previous States:
  * If a bug is introduced or a mistake is made, VCS enables you to revert the codebase to a previous state. This is especially useful in situations where you need to roll back changes quickly.

- Backup and Disaster Recovery:
  * Version control systems act as a form of backup, storing multiple copies of your code. This provides a level of protection against data loss, whether due to accidental deletion, hardware failure, or other unforeseen events.

- Traceability and Accountability:
  * VCS records who made each change and when. This traceability can be valuable for auditing purposes, identifying contributors to specific features or issues, and understanding the context behind changes.

- Experimentation and Prototyping:
  * With branches, developers can experiment with new features, fixes, or ideas without affecting the main codebase. This allows for rapid prototyping and testing.

- Efficient Release Management:
  * VCS plays a role in managing different versions of your software. By tagging releases, you can easily create and maintain different versions of your project, making it easier to support multiple versions in production.

- Standardization and Consistency:
  * VCS encourages standardized practices by providing a central repository for code. Developers can follow a consistent workflow and share coding standards and guidelines.



---

### 11.2 What’s the difference between Git and GitHub?

Git and GitHub are related but distinct concepts in the world of version control and software development.

- Git:
  * Git is a distributed version control system (DVCS) that was created by Linus Torvalds, the same person who created the Linux operating system.
  * It is a tool used to manage and track changes to source code over time.
  * Git allows developers to work collaboratively on the same codebase, manage different versions of the code, and merge changes made by multiple developers.
  * Git operates locally on your computer and doesn't require a constant connection to a server. Each developer has a complete copy of the entire codebase, which provides flexibility and offline capabilities.

- GitHub:
  * GitHub is a web-based platform that provides hosting for Git repositories. It's a service built around Git that enhances collaboration and offers additional features.
  * GitHub allows developers to store, manage, and collaborate on their Git repositories in a centralized and user-friendly way.
  * It provides a visual interface for working with Git repositories, making tasks such as creating branches, reviewing changes, and managing pull requests more intuitive.
  * GitHub also offers features like issue tracking, project management tools, continuous integration, and more, which contribute to a streamlined development workflow.
  * GitHub is not the only platform that hosts Git repositories; other alternatives include GitLab and Bitbucket.

In summary, Git is the version control system that handles tracking changes and managing versions of source code, while GitHub is a web-based platform that provides hosting for Git repositories and offers collaboration tools to enhance the development process.


---

### 11.3 What are remote repositories in Git?

Remote repositories in Git are versions of your project that are hosted on a server or online platform, separate from your local repository. They serve as a way to collaborate with others, share code, and keep a centralized backup of your project. Remote repositories are crucial for team collaboration and for sharing your work with others.

Key points about remote repositories:

- Hosted Remotely: Remote repositories are hosted on remote servers, often provided by services like GitHub, GitLab, Bitbucket, or your own server.
- Collaboration: Remote repositories allow multiple developers to work together on the same codebase. They can clone the repository, make changes, and push their changes back to the remote repository.
- Backup and Redundancy: Remote repositories act as a secure backup of your project. If something happens to your local copy, you can always retrieve your code from the remote repository.
- Branches and Pull Requests: Remote repositories enable you to create and manage branches. Developers can work on separate branches, make changes, and later merge their branches back into the main branch (usually called "master" or "main"). Pull requests or merge requests facilitate the process of reviewing and merging changes.
- Fetching and Pulling: Fetching allows you to retrieve changes from a remote repository to your local repository without automatically merging them. Pulling is the process of fetching and merging the changes into your local branch.
- Pushing: Pushing is the process of sending your local changes to the remote repository. Other team members can then fetch or pull your changes to stay up-to-date.
- Forks: Many online platforms allow you to fork a repository, creating a copy that you can modify independently. You can then submit pull requests to propose changes to the original repository.
- Private and Public Repositories: Remote repositories can be either private (accessible only to collaborators) or public (accessible to anyone). This flexibility enables both open-source and proprietary projects.


---

### 11.4 Why does a merge conflict occur?

A merge conflict occurs in version control systems like Git when there are conflicting changes made to the same part of a file or codebase by different contributors. Merge conflicts typically arise during the process of combining changes from different branches, such as when merging a feature branch into the main branch or pulling changes from a remote repository.

#### Parallel Development:
  - Imagine two or more developers are working on the same codebase but on different branches. They make changes to the same part of a file or code during their work.

#### Attempted Merge:
  - When one developer attempts to merge their branch back into the main branch (or pull changes from a remote repository), the version control system tries to automatically combine the changes.

#### Conflicting Changes:
  - If the changes made by the different developers affect the same lines of code, the version control system cannot determine which changes should take precedence. This creates a conflict situation.


The version control system identifies the conflicting lines and marks them as a "conflict." It will not automatically resolve the conflict to avoid unintentional data loss.
When a merge conflict occurs, it's up to the developer to resolve it manually. This involves reviewing the conflicting changes, deciding which version to keep, and making the necessary modifications to the code to achieve a coherent and correct result.

Merge conflicts are a natural part of collaborative development, especially in projects with multiple contributors. They highlight the need for clear communication, careful code review, and the ability to resolve disagreements over code changes effectively.


---
---

## 12. Terminal

---
---

### 12.1 How do you run a JavaScript file in the terminal?

To run a JavaScript file in the terminal, you can use the `Node.js` runtime environment. `Node.js` allows you to execute JavaScript code outside of a web browser, making it suitable for running JavaScript files on the command line or in a server environment.

- Install `Node.js` (If Not Installed):
  * If you don't have `Node.js` installed on your system, you'll need to download and install it. You can get the latest version from the official `Node.js` website: https://nodejs.org/
- Create a JavaScript File:
  * Create a .js file containing your JavaScript code.
    e.g. 'app.js' file:
    ```javascript
    console.log("Hello World");
    ```
- Open Terminal:
  * Open your terminal or command prompt.
- Navigate to the Directory:
  * Use the cd command to navigate to the directory where your JavaScript file is located.
    e.g.
    ```javascript
    cd /path/to/your/project/directory
    ```
- Run the JavaScript File:
  * Use the `node` command followed by the name of your JavaScript file to execute it.
    ```javascript
    node app.js
    // This will run the app.js file using the Node.js interpreter, and the output (if any) will be displayed in the terminal.
    // Output: Hello World
    ```

Running JavaScript files in the terminal using Node.js is especially useful for scripts, automation tasks, server-side applications, and other scenarios where you don't need a web browser to execute your code.

---

### 12.2 How do you stop a running a command in the terminal?

On most operating systems (Windows, macOS, Linux), pressing `Ctrl+C` sends an interrupt signal (SIGINT) to the currently running command in the terminal.
This signal typically causes the command to terminate, and you'll be returned to the terminal prompt.


---

### 12.3 How go you get the previous command in the terminal?

Pressing the up arrow key (↑) in the Windows Command Prompt will cycle through your command history.
Pressing the down arrow key (↓) will move backward through your command history.
Using these keyboard shortcuts, you can easily navigate through your command history to retrieve and reuse previous commands in the terminal. If you need to access even older commands beyond the immediate history, you can use the arrow keys to cycle through the history.

---

### 12.4 How do you got to the current directory's parent directory in the terminal?

To navigate to the parent directory of the current directory in the terminal, we can use the command `cd ..` This command allows us to move up one level in the directory hierarchy.



---
---
