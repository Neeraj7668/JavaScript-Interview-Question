# JavaScript Interview questions

𝟭-𝟭𝟬: 𝗕𝗮𝘀𝗶𝗰𝘀 𝗝𝗮𝘃𝗮𝗦𝗰𝗿𝗶𝗽𝘁

1. What is JavaScript?
2. Explain the difference between let, const, and var.
3. How does hoisting work in JavaScript?
4. Describe the concept of closures.
5. Explain the event loop in JavaScript.
6. What is the difference between == and ===?
7. How do you check the type of a variable in JavaScript?
8. What is the use of the this keyword in JavaScript?
9. Explain the difference between function declaration and function expression.
10. How does the setTimeout function work?

𝟭𝟭-𝟮𝟬: 𝗙𝘂𝗻𝗰𝘁𝗶𝗼𝗻𝘀 𝗮𝗻𝗱 𝗦𝗰𝗼𝗽𝗲

11. What is a callback function?
12. Explain the concept of a pure function.
13. Describe the differences between function.call, function.apply, and function.bind.
14. What is the purpose of the arguments object in a function?
15. How do you create a closure in JavaScript?
16. What is the use of the bind method?
17. What is the difference between a shallow copy and a deep copy?
18. How does the call stack work in JavaScript?
19. Explain the concept of function currying.
20. How can you avoid callback hell in JavaScript?

𝟮𝟭-𝟯𝟬: 𝗢𝗯𝗷𝗲𝗰𝘁𝘀 𝗮𝗻𝗱 𝗣𝗿𝗼𝘁𝗼𝘁𝘆𝗽𝗲𝘀

21. What is prototypal inheritance?
22. How do you create an object in JavaScript?
23. What is the purpose of the prototype property in JavaScript?
24. Explain the difference between Object.create and the constructor pattern.
25. How do you add a property to an object in JavaScript?
26. What is the hasOwnProperty method used for?
27. How can you prevent modification of object properties in JavaScript?
28. Describe the use of the new keyword.
29. Explain the concept of Object Destructuring in JavaScript.
30. What is the difference between null and undefined?

𝟯𝟭-𝟰𝟬: 𝗗𝗢𝗠 𝗠𝗮𝗻𝗶𝗽𝘂𝗹𝗮𝘁𝗶𝗼𝗻 𝗮𝗻𝗱 𝗘𝘃𝗲𝗻𝘁𝘀

31. What is the DOM?
32. How do you select elements with Vanilla JavaScript?
33. Explain event delegation in JavaScript.
34. What is the purpose of the addEventListener method?
35. How do you create and remove elements in the DOM?
36. Explain the concept of event propagation.
37. How can you prevent the default behaviour of an event?
38. What is the purpose of the data- attribute in HTML?
39. Describe the difference between innerHTML and textContent.
40. How do you handle asynchronous code in JavaScript?

## JavaScript Practical Questions Answer 1-10

1. **Write program to find the nth largest number in the array without using in-built functions? <br>**
   let arr=[66,44,55,88,7,9,3,22,322]
   Ans: Here's a JavaScript program to find the nth largest number in an array without using any in-built functions:

```javascript
function findNthLargest(arr, n) {
  let sortedArr = arr.slice().sort((a, b) => b - a);
  return sortedArr[n - 1];
}

let arr = [66, 44, 55, 88, 7, 9, 3, 22, 322];
let n = 3;
let nthLargest = findNthLargest(arr, n);
console.log(`The ${n}th largest number in the array is: ${nthLargest}`);

This program first creates a sorted copy of the array in descending order using the `sort()` method. Then, it returns the nth element (n - 1 index) from the sorted array, which corresponds to the nth largest number in the original array.

function findNthLargestWithoutSort(arr, n) {
    let max = Math.max(...arr);
    for (let i = 1; i < n; i++) {
        let index = arr.indexOf(max);
        arr.splice(index, 1);
        max = Math.max(...arr);
    }
    return max;
}

let arr = [66, 44, 55, 88, 7, 9, 3, 22, 322];
let n = 3;
let nthLargest = findNthLargestWithoutSort(arr, n);
console.log(`The ${n}th largest number in the array is: ${nthLargest}`);
```
This program iteratively finds the maximum element in the array n times, removing each maximum element found before finding the next largest element. This way, it avoids using the sort method or any other built-in functions.

<!--  -->

## Basic JavaScript Question Answer 1-10

1. **What is JavaScript?** <br>
   Ans: JavaScript is a high level programming language used to create interactive and dynamic websites, web applications and desktop applications.It is also commonly used for server-side development using Node.js.

2. **Explain the difference between let, const, and var?** <br>
   Ans: `var` is function-scoped (or global scope) and can be redeclared and reassigned. `let` is block-scoped, can be reassigned but not redeclared in the same scope. `const` is also block-scoped and cannot be reassigned or redeclared.

```javascript
var x = 1;
let y = 2;
const z = 3;

// Redeclaration and reassignment
var x = 4; // No error
let y = 5; // Error: Identifier 'y' has already been declared
const z = 6; // Error: Identifier 'z' has already been declared

// Reassignment
x = 7; // No error
y = 8; // No error
z = 9; // Error: Assignment to constant variable
```

3. **How does hoisting work in JavaScript?** <br>
   Ans: In JavaScript, variable and function declarations are hoisted to the top of their containing scope during the compile phase, which means they are processed before the code is executed. However, only the declarations are hoisted, not the initializations. Here's how it works:

```javascript
console.log(x); // undefined
var x = 5;
```

In this example, even though `x` is logged before it's assigned a value, it doesn't throw an error. This is because the declaration `var x;` is hoisted to the top, making `x` accessible throughout the function (or global scope), but its value is `undefined` until the assignment `x = 5;` is reached.

4. **Describe the concept of closures?** <br>
   Ans: A closure is the combination of a function bundled(enclosed) together with its lexical environment within which that function was declared. i.e, It is an inner function that has access to the outer or enclosing function’s variables, functions and other data even after the outer function has finished its execution.

The closure has three scope chains.

1. Own scope where variables defined between its curly brackets
2. Outer function's variables
3. Global variables

```javascript
function outerFunction() {
  let outerVariable = "I am from outerFunction";

  function innerFunction() {
    console.log(outerVariable); // Accessing outerVariable from the outer scope
  }

  return innerFunction;
}

const closureFunction = outerFunction();
closureFunction(); // Outputs: "I am from outerFunction"
```

In this example, `innerFunction` is a closure because it retains access to the `outerVariable` even after `outerFunction` has finished executing. This is possible because closures in JavaScript maintain a reference to their outer lexical environment.

5. **Explain the event loop in JavaScript?** <br>
   Ans: The event loop in JavaScript manages the execution of multiple asynchronous tasks, ensuring that they are executed in the correct order. It continuously checks the call stack and the callback queue, moving tasks from the queue to the stack when the stack is empty.

Example:

```javascript
console.log("Hello");

setTimeout(function () {
  console.log("World");
}, 1000);

console.log("JavaScript");
```

Output:

```
Hello
JavaScript
World
```

6. **What is the difference between == and ===? <br>**
   Ans:
   The `==` operator checks if two values are equal without type conversion, while `===` checks if they are equal with their respective types as well.

Example:

```javascript
0 == "0"; // true, because '0' is converted to number 0
0 === "0"; // false, because they are of different types
```

7. **How do you check the type of a variable in JavaScript? <br>**
   Ans: We can check the type of a variable in JavaScript using the `typeof` operator.

Example:

```javascript
typeof 42; // "number"
```

8. **What is the use of the this keyword in JavaScript?** <br>
   Ans:
   The `this` keyword in JavaScript refers to the object that is currently executing the function where `this` is used.

Example:

```javascript
const person = {
  name: "Neeraj Maurya",
  email: "neerajmourya001@gmail.com",
  introduce: function () {
    return "Hello, my name is " + this.name + "and my email is " + this.email;
  },
};
console.log(person.introduce()); // Outputs: "Hello, my name is Alice"
```

9. **Explain the difference between function declaration and function expression? <br>**
   Ans:
   Function declarations are hoisted and can be called before they are defined, while function expressions are not hoisted and cannot be called before they are defined.

Example:

```javascript
// Function Declaration
functionDeclaration(); // "Function Declaration is hoisted"
function functionDeclaration() {
  console.log("Function Declaration is hoisted");
}

// Function Expression
// functionExpression(); // This would throw an error
var functionExpression = function () {
  console.log("Function Expression is not hoisted");
};
```

10. **How does the setTimeout function work?<br>**
    Ans:
    The `setTimeout` function in JavaScript schedules a function to run after a specified delay in milliseconds.

Example:

```javascript
setTimeout(function () {
  console.log("Delayed message");
}, 2000); // Outputs 'Delayed message' after 2 seconds
```

## JavaScript:- Functions and Scope Question Answer 11-20

11. **What is a callback function?<br>**
    Ans:
    A callback function is a function that is passed as an argument to another function and is called ("invoked") inside that function.

Example:

```javascript
function greet(name, callback) {
  const message = "Hello, " + name + "!";
  callback(message);
}

function displayMessage(message) {
  console.log(message);
}

greet("Aman", displayMessage); // Outputs: "Hello, Alice!"
```

12. **Explain the concept of a pure function?<br>**
    Ans:
    A pure function is a function that always returns the same result given the same input and has no side effects.

Example:

```javascript
function add(a, b) {
  return a + b;
}
```

13. **Describe the differences between function.call, function.apply, and function.bind?<br>**
    Ans:
    `function.call` and `function.apply` are used to call a function with a specific context (the value of `this`) and arguments, where `apply` takes arguments as an array. `function.bind` creates a new function with the specified context.

Example:

```javascript
const person = {
  name: "John",
  greet: function () {
    return "Hello, " + this.name;
  },
};

const newContext = { name: "Bob" };

console.log(person.greet.call(newContext)); // Outputs: "Hello, Bob"
console.log(person.greet.apply(newContext)); // Outputs: "Hello, Bob"

const boundGreet = person.greet.bind(newContext);
console.log(boundGreet()); // Outputs: "Hello, Bob"
```

14. **What is the purpose of the arguments object in a function?<br>**
    Ans:
    The `arguments` object in a function provides access to all the arguments passed to the function, even if they were not declared as formal parameters.

Example:

```javascript
function sum() {
  let total = 0;
  for (let i = 0; i < arguments.length; i++) {
    total += arguments[i];
  }
  return total;
}

console.log(sum(1, 2, 3, 4, 5)); // Outputs: 15
```

15. **How do you create a closure in JavaScript?<br>**
    Ans:
    You create a closure in JavaScript by defining a function within another function and accessing variables from the outer function's scope.

Example:

```javascript
function outerFunction() {
  let outerVariable = "I am from outerFunction";

  function innerFunction() {
    console.log(outerVariable); // Accessing outerVariable from the outer scope
  }

  return innerFunction;
}

const closureFunction = outerFunction();
closureFunction(); // Outputs: "I am from outerFunction"
```

16. **What is the use of the bind method?<br>**
    Ans:
    The `bind` method is used to create a new function with a specified `this` value and initial arguments, without calling the function immediately.

Example:

```javascript
const person = {
  name: "John",
  greet: function () {
    return "Hello, " + this.name;
  },
};

const boundGreet = person.greet.bind(person);
console.log(boundGreet()); // Outputs: "Hello, Alice"
```

17. **What is the difference between a shallow copy and a deep copy?<br>**
    Ans:
    A shallow copy creates a new object but does not duplicate nested objects, while a deep copy creates a new object and duplicates all nested objects as well.

```javascript
// Shallow copy
const originalArray = [1, 2, [3, 4]];
const shallowCopyArray = [...originalArray];
originalArray[2][0] = 5;
console.log(shallowCopyArray[2][0]); // Outputs: 5 (both originalArray and shallowCopyArray share the same reference to the nested array)

// Deep copy
function deepCopyArray(arr) {
  return JSON.parse(JSON.stringify(arr));
}

const deepCopyArray = deepCopyArray(originalArray);
originalArray[2][0] = 6;
console.log(deepCopyArray[2][0]); // Outputs: 5 (deepCopyArray retains the original value)
```

In this example, the shallow copy using the spread operator `[...originalArray]` does not create a new nested array, so both the original array and the shallow copy share the same reference to the nested array. However, the deep copy function creates a new array with a new nested array, so changes to the original array do not affect the deep copy.

18. **How does the call stack work in JavaScript?<br>**
    Ans:
    The call stack in JavaScript is a data structure that records function calls, managing the execution order and context.

Example:

```javascript
function greet() {
  console.log("Hello");
}

function welcome() {
  greet();
  console.log("Welcome");
}

welcome();
```

In this example, the call stack records the function calls in the order they are invoked, managing the execution flow.

19. **Explain the concept of function currying?<br>**
    Ans:
    Function currying is the process of converting a function with multiple arguments into a sequence of nested functions, each taking a single argument.

Example:

```javascript
function add(a) {
  return function (b) {
    return a + b;
  };
}

const addTwo = add(2);
console.log(addTwo(3)); // Outputs: 5
```

20. **How can you avoid callback hell in JavaScript?<br>**
    Ans:
    We can avoid callback hell in JavaScript by using promises or async/await for asynchronous operations.

Example:

```javascript
function asyncOperation() {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      resolve("Operation completed");
    }, 2000);
  });
}

async function fun() {
  try {
    const result = await asyncOperation();
    console.log(result);
  } catch (error) {
    console.error(error);
  }
}

fun();
```

## 1. What is MySQL?
MySQL is a relational database management system based on SQL (Structured Query Language). It is an open source software owned by Oracle and can run on various platforms. Most websites or web applications are developed using MySQL.

## JOIN SQL
JOIN in MySQL is used to combine rows from two or more tables based on a related column between them.

## Explain the concept of a foreign key.

A foreign key in MySQL establishes a relationship between two tables by linking a column or group of columns in one table to the primary key column(s) in another table. It enforces referential integrity, ensuring that values in the foreign key column(s) match values in the referenced primary key column(s) of the related table.

## What does the JOIN statement do in MySQL? Explain the different types of joins.
The JOIN statement in MySQL is used to retrieve data from multiple tables based on a related column between them. 

## 38. What is a primary key in MySQL?
A primary key in MySQL is a unique identifier for each row in a table. 

## 31. What types of relationships are used in MySQL?
Three types of relationships are used in MySQL:

One-to-one – items with one-to-one relation can be included as columns in the same table
One-to-many – or many-to-one relationships are seen when one row in a table is related to multiple rows in another table
Many-to-many – many rows in a table are linked to many rows in another table

## 33. What is Scaling?
Scaling capacity in MySQL is the ability to handle the load in terms of:

Data quantity
Number of users
User activity
Size of related datasets

## 34. What is Sharding?
The process of breaking up large tables into smaller chunks or shards spread across many servers is called sharding. It makes querying, maintenance, and other tasks faster. 

## 36. How does MySQL differ from PostgreSQL?
MySQL and PostgreSQL are both popular relational database management systems (RDBMS) but have differences in features, performance, and syntax. MySQL is known for its speed and ease of use, while PostgreSQL is praised for its advanced features, including sup

## 38. What is a primary key in MySQL?
A primary key in MySQL is a unique identifier for each row in a table.

## 39. Explain the concept of a foreign key.
A foreign key in MySQL establishes a relationship between two tables by linking a column or group of columns in one table to the primary key column(s) in another table. 

## 49. How do you perform a full-text search in MySQL?
Full-text search in MySQL is performed using the MATCH() AGAINST() syntax, where MATCH() specifies the columns to search and AGAINST() specifies the search query. It is applicable only on columns indexed as FULLTEXT.

## 50. Explain the LIKE clause in MySQL.
The LIKE clause in MySQL is used to search for patterns in strings. It allows the use of wildcard characters such as '%' (matches zero or more characters) and '_' (matches any single character) to perform flexible pattern matching.

## 51. Describe the use of GROUP BY and ORDER BY in MySQL.
GROUP BY in MySQL is used to group rows that have the same values into summary rows, typically in conjunction with aggregate functions like SUM or COUNT. ORDER BY is used to sort

## 54. Explain the difference between INNER JOIN and OUTER JOIN.
INNER JOIN returns only the rows that have matching values in both tables based on the join condition specified, while OUTER JOIN returns all rows from one or both tables, with unmatched rows filled with NULL values where the join condition is not met.