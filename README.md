# JavaScript Interview questions

𝟭-𝟭𝟬: 𝗕𝗮𝘀𝗶𝗰𝘀 𝗼𝗳 𝗝𝗮𝘃𝗮𝗦𝗰𝗿𝗶𝗽𝘁

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

## JavaScript Question Answers:

1. **What is JavaScript?**
   Ans: JavaScript is a high level programming language used to create interactive and dynamic websites, web applications and desktop applications.It is also commonly used for server-side development using Node.js.

2. **Explain the difference between let, const, and var?**
   Ans: `var` is function-scoped and can be redeclared and reassigned. `let` is block-scoped, can be reassigned but not redeclared in the same scope. `const` is also block-scoped and cannot be reassigned or redeclared.

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
