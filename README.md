# JS Technical Blog

This is a technical blog to revise the all the covered conepts [uptil now](https://github.com/mountblue/javascript-full-stack-path/blob/master/2.%20javascript/4.%20js-debugging-and-review.md) in mountblue JS bootcamp

## Loops

### for:
Inside the for loop there are three expressiosn:

- step initilization `let step = 0`: this is where the loop iteration start is defined (it is run once).
- step limit `step < 10`: This is the condition until the step will increase or decrease.
- step size: this is where you defince the jumps you want to take between each iteration. `step++`

```javascript
for(let step = 0; step < 10; step++){
    console.log(i);
}
```

### forEach:
`forEach` is used to iterate over an array and access its elements:

```javascript
let arr = [1, 2, 3, 4, 5, 6]

arr.forEach((element) => {
    console.log(element);
})
```

### for ... in:
`for ... in` loop is used to iterate over an object and access its keys.

```javascript
let student = {name: "Kishore", class: "12th", stream: "science"}

for(let key in student){
    console.log(key, student[key]);
}
```

### for ... of:
`for ... of` loop is used to iterate over an array and access its element directly.

```javascript
let names = ["John", "Oliver", "Kingston", "Harry"]

for(let name of names){
    console.log(name);
}
```

### while:
`while` is also a loop that iterates until the condition is met. But this is different from `for` as the step function is executed within the loop. But while using `while` loop you have to manually do the step function.

```javascript
let count = 0

while (count < 10){
    console.log(count);
    count++
}
```


## Pass by Reference and Pass by Value

### Pass by value:

When a primitive data type is passed as an argument to a function, it create a copy of it and then passes it to function. This is called pass by value.

```javascript
function changeValue(x) {
  x = 10;
  console.log(x); // Output: 10
}
let a = 5;
changeValue(a);
console.log(a); // Output: 5 (unchanged)
```

### Pass by reference:

When a non-primitive data type (like array or an object) is passed as an arguemnet to the function, it doesn't create a copy, and it refernce in memory is passed to the function(original object). So any change inside the function to the array/object will affect it outside the function as well.

```javascript
function changeArray(arr) {
  arr.push(4);
  console.log(arr); // Output: [1, 2, 3, 4]
}
let numbers = [1, 2, 3];
changeArray(numbers);
console.log(numbers); // Output: [1, 2, 3, 4] (modified)
```

## Array methods

### Basics:

**1. Array.pop():**

`Array.pop()` removes the last element from the element the array and returns it.

Mutates the original array.

```javascript
const fruits = ['apple', 'banana', 'orange'];
const lastFruit = fruits.pop();

console.log(lastFruit); // Output: 'orange'
console.log(fruits); // Output: ['apple', 'banana']
```

**2. Array.push():**

`Array.push()` appends the arguements of `push()` to the array and returns its new length.

Mutates the original array.

```javascript
const numbers = [1, 2, 3];
const newLength = numbers.push(4, 5);

console.log(newLength); // Output: 5
console.log(numbers); // Output: [1, 2, 3, 4, 5]
```

**3. Array.concat():**

`Array.concat()` merges the new array passed as arguement to `concat()` with the array and return the merged array.

Does not mutate the original array.

```javascript
const arr1 = [1, 2];
const arr2 = [3, 4];

const concatenated = arr1.concat(arr2);
console.log(concatenated); // Output: [1, 2, 3, 4]
```

**4. Array.slice():**

`Array.slice()` is used to return an array thats portion of the main array

Does not mutate the original array.

```javascript
const names = ['Alice', 'Bob', 'Charlie', 'David'];

const slicedNames = names.slice(1, 3);
console.log(slicedNames); // Output: ['Bob', 'Charlie']
```

**4. Array.splice():**

`Array.splice()` is used to add or remove elements from an array at a specific index.

Mutates the original array

```javascript
const colors = ['red', 'green', 'blue'];

colors.splice(1, 0, 'yellow');
console.log(colors); // Output: ['red', 'yellow', 'green', 'blue']

```

**6. Array.join():**

`Array.join()` creates and returns a new string by concatenating all of the elements in an array, separated by a specified separator string.

Does not mutate the original array.

```javascript
const words = ['Hello', 'world', 'from', 'JavaScript'];

const sentence = words.join(' ');
console.log(sentence); // Output: 'Hello world from JavaScript'
```

**7. Array.flat():**

`Array.flat()` creates a new array with all sub-array elements concatenated into it recursively up to the specified depth.

Does not mutate the original array.

### Finding:

**1. Array.find():**

`Array.find()` returns the first element in the array that satisfies the provided test function. If no elements satisfy the test function, undefined is returned.

Does not mutate the original array.

```javascript
const numbers = [1, 2, 3, 4, 5];

const evenNumber = numbers.find(num => {
    return num % 2 === 0
});
console.log(evenNumber); // Output: 2
```

**2. Array.indexOf():**

`Array.indexOf()` returns the first index at which a given element can be found in the array, or -1 if it is not present.

Does not mutate the original array.

```javascript
const fruits = ['apple', 'banana', 'orange'];
const index = fruits.indexOf('banana');

console.log(index); // Output: 1
```

**3. Array.includes():**

`Array.includes()` determines whether an array includes a certain value among its entries, returning true or false as appropriate.

Does not mutate the original array.

```javascript
const numbers = [1, 2, 3, 4, 5];
const includesThree = numbers.includes(3);
console.log(includesThree); // Output: true
```

**4. Array.findIndex():**

`Array.findIndex()` returns the index of the first element in the array that satisfies the provided testing function. If no elements satisfy the testing function, -1 is returned.

Does not mutate the original array.

```javascript
const numbers = [1, 2, 3, 4, 5];
const indexOfEvenNumber = numbers.findIndex(num => {
    return num % 2 === 0;
});
console.log(indexOfEvenNumber); // Output: 1
```

###

**1. Array.forEach():**

`Array.forEach()` executes a provided function once for each array element.

Does not mutate the original array.

```javascript
const numbers = [1, 2, 3, 4, 5];
numbers.forEach(num => {
    console.log(num);
});
// Output:
// 1
// 2
// 3
// 4
// 5
```

**2. Array.filter():**

`Array.filter()` creates a new array with all elements that pass the test implemented by the provided function.

Does not mutate the original array.

```javascript
const numbers = [1, 2, 3, 4, 5];
const evenNumbers = numbers.filter(num => {
    return num % 2 === 0;
});
console.log(evenNumbers); // Output: [2, 4]
```

**3. Array.map():**

`Array.map()` creates a new array populated with the results of calling a provided function on every element in the calling array.

Does not mutate the original array.

```javascript
const numbers = [1, 2, 3, 4, 5];
const doubledNumbers = numbers.map(num => {
    return num * 2;
});
console.log(doubledNumbers); // Output: [2, 4, 6, 8, 10]
```

**4. Array.reduce():**

`Array.reduce()` executes a reducer function (that you provide) on each element of the array, resulting in a single output value.

Does not mutate the original array.

```javascript
const numbers = [1, 2, 3, 4, 5];
const sum = numbers.reduce((acc, num) => {
    acc = acc + num;
    return acc;
}, 0);
console.log(sum); // Output: 15
```

**5. Array.sort():**

`Array.sort()` sorts the elements of an array in place and returns the sorted array. The default sort order is ascending, built upon converting the elements into strings, then comparing their sequences of UTF-16 code units values.

Mutates the original array.

```javascript
const fruits = ['banana', 'apple', 'orange'];
fruits.sort();
console.log(fruits); // Output: ['apple', 'banana', 'orange']
```

### Advanced:

**1. Array methods chaining:**

Array methods can be chained together to perform multiple operations on an array in a single statement.

Does not mutate the original array unless a mutating method is used in the chain.

```javascript
const numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
const result = numbers.filter(num => {
    return num % 2 === 0;
}).map(num => {
    return num * 2;
}).reduce((acc, num) => {
    acc = acc + num;
    return acc;
}, 0);

console.log(result); // Output: 60
```

## String methods

**1. String.toUpperCase() and String.toLowerCase():**

`String.toUpperCase()` converts a string to uppercase letters, while String.
`toLowerCase()` converts a string to lowercase letters.

Does not mutate the original string.

```javascript
const str = 'Hello, World!';

const upperStr = str.toUpperCase();
const lowerStr = str.toLowerCase();

console.log(upperStr); // Output: 'HELLO, WORLD!'
console.log(lowerStr); // Output: 'hello, world!'
```

**2. String.trim():**

`String.trim()` removes whitespace from both ends of a string.

Does not mutate the original string.

```javascript
const str = '  Hello, World!  ';
const trimmedStr = str.trim();

console.log(trimmedStr); // Output: 'Hello, World!'
```

**3. String.split():**

`String.split()` splits a string into an array of substrings based on a specified separator.

Does not mutate the original string.

```javascript
const str = 'Hello, World!';
const words = str.split(', ');

console.log(words); // Output: ['Hello', 'World!']
```

**4. String.replace():**

`String.replace()` replaces a specified value with another value in a string.

Does not mutate the original string.

```javascript
const str = 'Hello, World!';
const newStr = str.replace('World', 'Universe');
console.log(newStr); // Output: 'Hello, Universe!'
```

**5. String.substring() and String.slice():**

String.substring() and String.slice() extract a part of a string and return the extracted part in a new string.

Do not mutate the original string

```javascript
const str = 'Hello, World!';
const substr = str.substring(0, 5);
const slicedStr = str.slice(7);

console.log(substr);    // Output: 'Hello'
console.log(slicedStr); // Output: 'World!'
```

## Object methods and operations

### 1. Object.assign():

`Object.assign()` is used to copy the values of all enumerable properties from one or more source objects to a target object.

Mutates the target object.

```javascript
const target = { a: 1, b: 2 };
const source = { b: 4, c: 5 };

Object.assign(target, source);
console.log(target); // Output: { a: 1, b: 4, c: 5 }
```

### 2. Object.keys()

Object.keys() returns an array of a given object's own key property names.

Do not mutate the original object.

```javascript
const obj = { a: 1, b: 2, c: 3 };

const keys = Object.keys(obj);
console.log(keys);    // Output: ['a', 'b', 'c']
```

### 3. Object.values():
Object.values() returns an array of a given object's own key property values.

Do not mutate the original object.

```javascript
const obj = { a: 1, b: 2, c: 3 };

const values = Object.values(obj);
console.log(values);  // Output: [1, 2, 3]
```

### 4. Object.entries():
Object.entries() returns an array of a given object's own enumerable string-keyed property [key, value] pairs.

Do not mutate the original object.

```javascript
const obj = { a: 1, b: 2, c: 3 };

const entries = Object.entries(obj);
console.log(entries); // Output: [['a', 1], ['b', 2], ['c', 3]]
```

## Hoisting

Hoisting is a JavaScript mechanism where variables and function declarations are moved to the top of their scope before code execution. This means that regardless of where variables and functions are declared, they are treated as if they are at the top of their scope.

**Variable hoisting:**
- Variables declared with `var` are hoisted to the top of their scope and initialized with a value of `undefined`.
- Variables declared with `let` and `const` are also hoisted but are not initialized with a value. Accessing them before the declaration results in a `ReferenceError`.

```javascript
console.log(x); // Output: undefined
var x = 5;

console.log(y); // ReferenceError: Cannot access 'y' before initialization
let y = 10;
```
**Function hoisting:**
- Function declarations are hoisted completely, including the function body.
- Function expressions are not hoisted.

```javascript
foo(); // Output: "Hello"
function foo() {
  console.log("Hello");
}

bar(); // TypeError: bar is not a function
var bar = function() {
  console.log("World");
};
```

## Scopes

Scope determines the accessibility of variables and functions in JavaScript. There are three types of scope in JavaScript:

**1. Global scope:**

Variables declared outside of any function or block have global scope.
They can be accessed from anywhere in the code.


**2. Function scope:**

Variables declared inside a function are only accessible within that function.
Each function creates a new scope.


**3. Block scope:**

Variables declared inside a block `{}` using `let` or `const` are only accessible within that block.
Blocks include `if` statements, `for` loops, and more.

```javascript
// Global scope
var globalVar = "I am global";

function myFunction() {
  // Function scope
  var functionVar = "I am in function scope";
  console.log(globalVar); // Accessible here
}

if (true) {
  // Block scope
  let blockVar = "I am in block scope";
  console.log(globalVar);   // Accessible here
  console.log(functionVar); // Not accessible here
}

console.log(globalVar);   // Accessible here
console.log(functionVar); // Not accessible here
console.log(blockVar);    // Not accessible here
```

## Closures
A closure is a function that has access to variables in its outer (enclosing) lexical scope, even after the outer function has returned. Closures allow a function to access variables from an enclosing scope even when invoked in a different scope.

```javascript
function outerFunction(x) {
  var y = 10;
  
  function innerFunction() {
    console.log(x + y);
  }
  
  return innerFunction;
}

var closure = outerFunction(5);
closure(); // Output: 15
```

## Higher Order Functions
Higher-order functions are functions that can take other functions as arguments and/or return functions as results.

```javascript
// Higher-order function that takes a function as an argument
function applyOperation(numbers, operation) {
  return numbers.map(operation);
}

const numbers = [1, 2, 3, 4, 5];
const doubledNumbers = applyOperation(numbers, (x) => {
    return x * 2;
});
console.log(doubledNumbers); // Output: [2, 4, 6, 8, 10]
```

## Best Practices
- Use meaningful and descriptive names for variables and functions.
- Prefer const and let over var for variable declarations.
- Handle errors and exceptions properly.
- Use strict equality (===) for comparisons.
- Comment your code to improve readability and maintainability.
- Use version control (e.g., Git) to track changes and collaborate with others.
- Write unit tests to ensure code correctness and prevent regressions.
- Optimize code for performance when necessary.

## Debugging
Debugging is the process of identifying and fixing errors or bugs in code. JavaScript provides several tools and techniques for effective debugging:

**1. Console logging:**
- Use `console.log()` & `console.table()` statements to output values and messages to the console for inspection.

**2. Debugging tools:**

- Browsers provide built-in debugging tools, such as Chrome DevTools or Firefox Developer Tools.


**3. Error handling:**

- Implement proper error handling using try/catch blocks to catch and handle exceptions gracefully.

---