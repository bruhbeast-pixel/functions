Here's a **Full Guide to JavaScript**, covering all the essential learning skills and key concepts. Each section includes code examples to demonstrate how it works.

## 1. Variables and Data Types
JavaScript has three ways to declare variables: `var`, `let`, and `const`. Each has its own scope and usage.

- `var` is function-scoped (older, avoid using it in modern code).
- `let` and `const` are block-scoped.

### Example:
````javascript
// var
var name = 'John'; // globally or function-scoped
let age = 25; // block-scoped (preferred)
const country = 'USA'; // block-scoped and cannot be reassigned

age = 26; // OK
// country = 'Canada'; // Error, can't reassign a const
````

### Data Types:
- **Primitives**: `string`, `number`, `boolean`, `null`, `undefined`, `symbol`, `bigint`
- **Reference types**: `objects`, `arrays`, `functions`

### Example:
````javascript
let isStudent = true; // boolean
let score = 95.5; // number
let userName = "Alice"; // string
let person = null; // null
let data; // undefined
````

## 2. Control Flow
JavaScript provides standard control flow mechanisms: `if`-`else`, `switch`, and loops (`for`, `while`, `do-while`).

### Example:
````javascript
let number = 10;

// if-else
if (number > 10) {
    console.log("Greater than 10");
} else if (number === 10) {
    console.log("Equal to 10");
} else {
    console.log("Less than 10");
}

// switch
let grade = 'A';
switch (grade) {
    case 'A':
        console.log("Excellent");
        break;
    case 'B':
        console.log("Good");
        break;
    default:
        console.log("Try harder");
}
````

### Loops
````javascript
// for loop
for (let i = 0; i < 5; i++) {
    console.log(i);
}

// while loop
let count = 0;
while (count < 5) {
    console.log(count);
    count++;
}

// do-while loop
let num = 0;
do {
    console.log(num);
    num++;
} while (num < 3);
````

## 3. Functions
Functions are the building blocks of JavaScript. They can be declared, passed around as values, or even used as objects.

### Example:
````javascript
// Function declaration
function greet(name) {
    return `Hello, ${name}!`;
}
console.log(greet("Bob"));

// Arrow function
const add = (a, b) => a + b;
console.log(add(5, 3));
````

## 4. Objects and Prototypes
Objects in JavaScript are collections of key-value pairs. Each object can have methods and properties.

### Example:
````javascript
const person = {
    firstName: "John",
    lastName: "Doe",
    age: 30,
    greet() {
        return `Hello, my name is ${this.firstName} ${this.lastName}`;
    }
};
console.log(person.greet());
````

### Prototypes:
````javascript
function Person(name, age) {
    this.name = name;
    this.age = age;
}

Person.prototype.sayHello = function() {
    return `Hello, I'm ${this.name}`;
};

const john = new Person("John", 25);
console.log(john.sayHello());
````

## 5. Asynchronous Programming
JavaScript handles async code via callbacks, promises, and `async/await`.

### Callback Example:
````javascript
function fetchData(callback) {
    setTimeout(() => {
        callback("Data received");
    }, 1000);
}
fetchData(data => console.log(data));
````

### Promises:
````javascript
let promise = new Promise((resolve, reject) => {
    let success = true;
    if (success) resolve("Operation succeeded");
    else reject("Operation failed");
});

promise.then(result => console.log(result)).catch(error => console.log(error));
````

### Async/Await:
````javascript
async function fetchData() {
    let response = await new Promise(resolve => {
        setTimeout(() => resolve("Data fetched"), 1000);
    });
    console.log(response);
}
fetchData();
````

## 6. DOM Manipulation
The **Document Object Model** (DOM) allows JavaScript to interact with the HTML structure.

### Example:
````javascript
// Select an element
const button = document.querySelector('button');

// Add event listener
button.addEventListener('click', () => {
    console.log('Button clicked!');
});

// Modify DOM element
button.textContent = 'Clicked!';
````

## 7. Closures and Scope
Closures occur when a function is able to "remember" its lexical scope, even when executed outside of it.

### Example:
````javascript
function outer() {
    let count = 0;
    return function inner() {
        count++;
        console.log(count);
    };
}
const increment = outer();
increment(); // 1
increment(); // 2
````

## 8. Modules (ES6)
JavaScript allows splitting code into modules to improve maintainability. Use `import` and `export`.

### Example:
```javascript
// module.js
export const name = "Alice";
export function greet() {
    return `Hello, ${name}`;
}

// main.js
import { name, greet } from './module.js';
console.log(greet());
```

## 9. Error Handling
Errors can be handled using `try-catch` blocks.

### Example:
````javascript
try {
    let result = someUndefinedVariable;
} catch (error) {
    console.log("Error caught:", error.message);
} finally {
    console.log("This runs regardless of success or failure.");
}
````

## 10. APIs and Fetch
You can use the `fetch` API to make HTTP requests.

### Example:
````javascript
fetch('https://api.example.com/data')
    .then(response => response.json())
    .then(data => console.log(data))
    .catch(error => console.log('Error:', error));
````

## 11. Modern JavaScript Features
- **Arrow Functions**: More concise syntax for functions.
- **Destructuring**: Unpacking values from arrays or objects.
- **Template Literals**: Use backticks for string interpolation.
- **Spread/Rest**: Spread values into an array or function.

### Example:
````javascript
// Arrow Function
const add = (a, b) => a + b;

// Destructuring
let person = { name: "John", age: 30 };
let { name, age } = person;

// Template Literals
console.log(`Hello, my name is ${name} and I am ${age} years old`);

// Spread operator
let arr1 = [1, 2];
let arr2 = [...arr1, 3, 4]; // [1, 2, 3, 4]
````

## 12. Memory Management
JavaScript automatically manages memory, but you should avoid creating circular references, memory leaks, and unnecessary object allocations.

## 13. Performance Optimization
- **Minimize DOM manipulation**: Manipulate the DOM in batches to reduce reflows and repaints.
- **Avoid deep recursion**: Large recursive calls may lead to stack overflow errors.
- **Debounce or throttle events**: For frequent events like scrolling.

### Example:
````javascript
// Debounce function
function debounce(func, delay) {
    let timeout;
    return function(...args) {
        clearTimeout(timeout);
        timeout = setTimeout(() => func.apply(this, args), delay);
    };
}
````

## Conclusion
This guide covers the core topics and default learning skills to master JavaScript. By understanding these areas and practicing regularly, you'll be well-equipped to work with JavaScript for a wide range of applications.
