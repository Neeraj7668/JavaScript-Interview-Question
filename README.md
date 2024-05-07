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


## React Interview questions 
1. Context API vs Redux.:
2. Class vs function component:
3. Prop drilling:
4. Bubble event:
5. Event propagation:
6. Interceptor:
7. Debouncing:
8. Virtual DOM:
9. Wildcard routing.:
10. Ref and forward ref:
11. Use Callback:
12. UseMemo:
13. usestate():
14. Unidirectional data flow:
15. Userfriendly URL:
16. synthetic events in React:
17. Memory management:
18. PWA:
19. SSR:

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

greet("Aman", displayMessage); // Outputs: "Hello, Aman!"
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


# React Question Answers

1. **Context API vs Redux?** </br>
Context API is a part of React that allows you to manage global state without third-party libraries, but it's less powerful than Redux, which offers more features like middleware and time-travel debugging. Use Context API for simpler state management needs and Redux for complex applications with more advanced requirements.

2. **Class vs function component?** </br>
Function components are simpler and more concise, using hooks like `useState` and `useEffect` for managing state and side effects. They are the preferred way to write components in modern React.

Class components are more verbose, using a combination of a constructor, `this.state`, and lifecycle methods like `componentDidMount` for side effects. They are still used in some cases, especially when working with older codebases or libraries that haven't been updated to use hooks.

1. **constructor(props)**: Initializes state and binds event handlers.
2. **render()**: Returns the JSX to be rendered.
3. **componentDidMount()**: Runs after the component is mounted to the DOM.
4. **componentDidUpdate(prevProps, prevState)**: Runs after the component updates.
5. **shouldComponentUpdate(nextProps, nextState)**: Controls if the component should re-render.
6. **componentWillUnmount()**: Runs before the component is removed from the DOM.

3. **Prop drilling** </br>
Prop drilling is the process of passing props down through multiple levels of nested components, even if intermediate components do not directly use the props, which can make the code harder to maintain.

4. **Bubble event?** </br>
Event bubbling is the process where an event triggered on the innermost (target) element propagates up through its ancestors in the DOM tree, allowing parent elements to also respond to the event.
or we can say:
Event bubbling is the propagation of an event from its target element up through its parent elements in the DOM hierarchy, enabling each ancestor to potentially handle the event.

5. **Event propagation?** </br>
Event propagation refers to the process by which events are handled in the DOM, where an event occurring on a specific element can propagate or travel through different phases (capturing and bubbling) and potentially trigger event handlers on ancestor or descendant elements.

6. **Interceptor?** </br>
An interceptor is a middleware function or component that intercepts an operation or process, allowing you to modify or augment its behavior. In web development, interceptors are often used to intercept HTTP requests or responses to add headers, log information, or modify data before it is sent or received.

7. **Debouncing?** </br>
Debouncing is a technique used to limit the rate at which a function is called. It ensures that the function is only executed after a certain amount of time has passed since the last invocation. This is commonly used in scenarios like handling user input, where you want to wait for the user to finish typing before performing an action.

8. **Real DOM v/s Virtual DOM** </br>
The real DOM is the actual representation of the HTML elements rendered on the web page, and any updates to it directly affect what the user sees. The virtual DOM is a lightweight copy of the real DOM maintained by libraries like React, which allows for faster updates by comparing its state with the real DOM and only applying the necessary changes, minimizing re-renders and improving performance.

9. **Wildcard routing?** </br>
Wildcard routing is a routing technique that allows a single route to match multiple URLs. This is often used in web applications to handle dynamic or variable parts of a URL, such as IDs or slugs, where the specific value is not known ahead of time. Wildcard routing is typically denoted by a special character like "*" or ":id" in the route definition.

In `react-router-dom`, you can use wildcard routing with the `Route` component by specifying a path with a wildcard parameter. For example, to create a route that matches any URL starting with "/user/", you can use the `:username` wildcard like this:

```jsx
import { BrowserRouter as Router, Route, Switch } from 'react-router-dom';

function App() {
  return (
    <Router>
      <Switch>
        <Route path="/user/:username" component={UserComponent} />
      </Switch>
    </Router>
  );
}
```

In this example, `:username` acts as a wildcard that matches any value in the URL segment after "/user/". You can then access the wildcard value (`username`) in your `UserComponent` using the `useParams` hook or `withRouter` HOC.

10. **Ref and forward ref?** </br>
`ref` is a special attribute in React that can be used to get a reference to a DOM element or a class component instance created by React. It allows you to interact with the underlying DOM or component directly.

`forwardRef` is a higher-order component (HOC) or a function component that allows you to pass `ref` through to a child component. This is useful when you need to access the underlying DOM element of a child component from a parent component.

Here's a basic example of using `forwardRef`:

```jsx
const FancyButton = React.forwardRef((props, ref) => (
  <button ref={ref} className="FancyButton">
    {props.children}
  </button>
));

const App = () => {
  const ref = React.createRef();
  return <FancyButton ref={ref}>Click me!</FancyButton>;
};
```

In this example, the `ref` is forwarded from `FancyButton` to the underlying `button` element, allowing you to access the `button` element using the `ref` created in the parent component (`App`).

11. **useMemo()?** </br>
`useMemo` is a hook in React that is used for memoization. It memoizes the result of a function so that the function is only called when one of its dependencies has changed. This can help improve performance by avoiding unnecessary recalculations.

12. **useCallback()?** </br>
`useCallback` is a hook in React that is used to memoize functions. It returns a memoized version of the callback function that only changes if one of the dependencies has changed. This is useful for optimizing performance in scenarios where functions are passed as props to child components, preventing unnecessary re-renders of those components.

Here's a basic example of using `useCallback`:

```jsx
import React, { useState, useCallback } from 'react';

function App() {
  const [count, setCount] = useState(0);

  const handleClick = useCallback(() => {
    setCount(count + 1);
  }, [count]);

  return (
    <div>
      <button onClick={handleClick}>Increment</button>
      <p>Count: {count}</p>
    </div>
  );
}

export default App;
```

In this example, `handleClick` is a callback function that increments the `count` state. By using `useCallback`, we ensure that `handleClick` is only recreated when the `count` state changes, optimizing the performance of the component.


13. **useState()** </br>
`useState` is a React hook used to add state variables to functional components.

14. **Unidirectional data flow?** </br>
Unidirectional data flow is a design pattern in which data flows only in one direction, typically from parent components to child components. Changes to the data are managed centrally and passed down to child components through props, ensuring predictable and maintainable code.

15. **Userfriendly URL?** </br>
A user-friendly URL is a web address that is easy for users to read and understand. It typically includes descriptive words that convey the content of the page, making it more intuitive and easier to remember. This can improve the user experience and make the website more accessible.

16. **synthetic events in React?** </br>
Synthetic events in React are objects that wrap native browser events, providing a consistent interface and additional features like event pooling and cross-browser compatibility. They are used for handling events in React components.

Event pooling in React reuses synthetic event objects to reduce memory allocation and improve performance.

17. **Memory management in React?** </br>
Memory management in React is handled by JavaScript's garbage collector, which automatically deallocates memory for objects that are no longer needed, but developers can optimize memory usage by minimizing unnecessary object creation and ensuring proper cleanup of resources, such as event listeners and timers, to prevent memory leaks.

One example of memory management in React is to use `useEffect` hook with a cleanup function to remove event listeners or clear intervals when a component unmounts, preventing memory leaks:

```jsx
import React, { useEffect } from 'react';

function Timer() {
  useEffect(() => {
    const intervalId = setInterval(() => {
      console.log('Tick');
    }, 1000);

    return () => {
      clearInterval(intervalId); // Cleanup function
    };
  }, []); // Empty dependency array means the effect runs only once

  return <div>Timer Component</div>;
}

export default Timer;
```

18. **PWA in React?** </br>
Progressive Web Apps (PWAs) in React are web applications that use modern web capabilities to provide a user experience similar to that of mobile apps. They are built using web technologies like HTML, CSS, and JavaScript, and can be installed on a user's device and accessed offline. React provides tools and libraries, such as service workers and the `react-pwa` package, to help developers create PWAs with features like offline support, push notifications, and home screen installation prompts.

19. **SSR in React?** </br>
Server-Side Rendering (SSR) is a technique used in web development where the server generates the initial HTML for a webpage, which is then sent to the client's browser, allowing the page to be rendered faster and improving SEO.

## MySQL Interview questions

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