# JavaScript Workshop Cheat Sheet

## Table of Contents

1. **[Beginner Fundamentals](#beginner-fundamentals)**
   - JavaScript Statements  
   - JavaScript Variables  
   - JavaScript Var vs Let vs Const  
   - JavaScript Data Types  
   - JavaScript Type Conversion  
   - JavaScript Operators  
   - JavaScript Arithmetic  
   - JavaScript Assignment  
   - JavaScript Comparison & Logical Operators  
   - JavaScript Operator Precedence  
   - JavaScript Booleans  

2. **[Control Flow](#control-flow)**
   - JavaScript `if`, `else`, `else if`  
   - JavaScript Switch Statement  
   - JavaScript `for` Loop  
   - JavaScript `while` Loop  
   - JavaScript Break & Continue  

3. **[Functions & Scope](#functions--scope)**
   - JavaScript Functions  
   - JavaScript Function Definitions  
   - JavaScript Function Parameters  
   - JavaScript Function Invocation  
   - JavaScript `call()`  
   - JavaScript `apply()`  
   - JavaScript `bind()`  
   - JavaScript Nested Functions  
   - JavaScript Scope  
   - JavaScript Hoisting  
   - The JavaScript `this` Keyword  

4. **[Strings & Numbers](#strings--numbers)**
   - JavaScript Strings  
   - JavaScript String Methods  
   - JavaScript String Search  
   - JavaScript String Reference  
   - JavaScript Numbers  
   - JavaScript Number Methods  
   - JavaScript Number Properties  
   - JavaScript Number Reference  

5. **[Arrays & Objects](#arrays--objects)**
   - JavaScript Arrays  
   - JavaScript Array Methods  
   - JavaScript Array Search  
   - JavaScript Array Sort  
   - JavaScript Array Iterations  
   - JavaScript Objects  
   - JavaScript Object Definition  
   - JavaScript Object Properties  
   - JavaScript Object Methods  
   - JavaScript Object Constructors  
   - JavaScript Object Accessors  
   - JavaScript Object Prototypes  

6. **[DOM & Events](#dom--events)**
   - JavaScript Events  
   - JavaScript Forms  
   - JavaScript Display Objects  
   - JavaScript HTML DOM Methods  
   - JavaScript HTML DOM Document  
   - JavaScript HTML DOM Elements  
   - JavaScript HTML DOM Elements (Nodes)  
   - JavaScript HTML DOM Collections  
   - JavaScript HTML DOM Node Lists  
   - JavaScript HTML DOM – Changing HTML  
   - JavaScript HTML DOM – Changing CSS  
   - JavaScript HTML DOM Animation  
   - JavaScript HTML DOM Events  
   - JavaScript HTML DOM EventListener  
   - JavaScript HTML DOM Navigation  

7. **[Browser & Timing](#browser--timing)**
   - JavaScript Window – The Browser Object Model  
   - JavaScript Window Screen  
   - JavaScript Window Location  
   - JavaScript Window History  
   - JavaScript Window Navigator  
   - JavaScript Popup Boxes  
   - JavaScript Timing Events  
   - JavaScript Cookies  

8. **[Advanced Data & Error Handling](#advanced-data--error-handling)**
   - JavaScript Math Object  
   - JavaScript Random  
   - JavaScript Bitwise Operations  
   - JavaScript Errors  
   - JavaScript Date Objects  
   - JavaScript Date Formats  
   - JavaScript Get Date Methods  
   - JavaScript Set Date Methods  

9. **[Working With JSON](#working-with-json)**
   - JavaScript JSON  
   - JSON Syntax  
   - JSON Data Types  
   - JSON Object Literals  
   - JSON Array Literals  
   - `JSON.parse()`  
   - `JSON.stringify()`  
   - JSON HTML  

10. **[Final Workshop Summary](#final-workshop-summary)**


## BEGINNER FUNDAMENTALS

🟢 **JavaScript Statements**
* 🔹 **Explanation**
  * Instructions that tell the computer what to do
  * End with semicolons (;) for clarity and best practice
* 🔹 **Code Example**
```js
console.log("Hello World");
let name = "John";
document.getElementById("demo").innerHTML = "Welcome!";
```
* 🔹 **Real-world Use Case**
  * Display messages to users
  * Store user input
  * Update webpage content
* 🔹 **Best Practice**
  * Always use semicolons to avoid unexpected behavior

🟢 **JavaScript Variables**
* 🔹 **Explanation**
  * Containers that store data values
  * Can be declared using var, let, or const
* 🔹 **Code Example**
```js
let userName = "Alice";
const PI = 3.14159;
var age = 25;
```
* 🔹 **Real-world Use Case**
  * Store user preferences
  * Keep track of shopping cart items
  * Hold API response data
* 🔹 **Best Practice**
  * Use descriptive names like `userName` instead of `x`

🟢 **JavaScript Var vs Let vs Const**
* 🔹 **Explanation**
  * `var`: function-scoped, can be redeclared and updated
  * `let`: block-scoped, can be updated but not redeclared
  * `const`: block-scoped, cannot be updated or redeclared
* 🔹 **Code Example**
```js
var oldWay = "function scoped";
let modernWay = "block scoped";
const FIXED_VALUE = "cannot change";

// const for objects/arrays - contents can change
const user = { name: "John" };
user.name = "Jane"; // This works!
```
* 🔹 **Real-world Use Case**
  * `const` for configuration values, API URLs
  * `let` for loop counters, temporary variables
  * Avoid `var` in modern JavaScript
* 🔹 **Best Practice**
  * Use `const` by default, `let` when you need to reassign, avoid `var`

🟢 **JavaScript Data Types**
* 🔹 **Explanation**
  * Primitive types: string, number, boolean, undefined, null, symbol, bigint
  * Non-primitive: object (includes arrays, functions, dates)
* 🔹 **Code Example**
```js
let text = "Hello World";        // string
let number = 42;                 // number
let isActive = true;             // boolean
let empty;                       // undefined
let nothing = null;              // null
let person = { name: "John" };   // object
let colors = ["red", "blue"];    // array (object)
```
* 🔹 **Real-world Use Case**
  * Strings for names, messages, HTML content
  * Numbers for prices, quantities, calculations
  * Booleans for toggles, validation states
* 🔹 **Shorthand**
  * Use `typeof` operator to check data type
* 🔹 **Best Practice**
  * Always initialize variables to avoid undefined values

🟢 **JavaScript Type Conversion**
* 🔹 **Explanation**
  * Automatic conversion (coercion) happens implicitly
  * Manual conversion using Number(), String(), Boolean()
* 🔹 **Code Example**
```js
// Automatic conversion
let result = "5" + 3;           // "53" (string)
let math = "5" - 3;             // 2 (number)

// Manual conversion
let str = String(123);          // "123"
let num = Number("456");        // 456
let bool = Boolean("hello");    // true
```
* 🔹 **Real-world Use Case**
  * Converting user input from forms (always strings)
  * API responses that need type conversion
  * Displaying numbers as formatted text
* 🔹 **Best Practice**
  * Always explicitly convert types to avoid bugs

🟢 **JavaScript Operators**
* 🔹 **Explanation**
  * Symbols that perform operations on variables and values
  * Include arithmetic, assignment, comparison, logical operators
* 🔹 **Code Example**
```js
let a = 10;
let b = 3;

// Arithmetic
let sum = a + b;        // 13
let remainder = a % b;  // 1

// Assignment
a += 5;                 // a = a + 5 = 15

// Comparison
let isEqual = a === 15; // true
let isGreater = a > b;  // true
```
* 🔹 **Real-world Use Case**
  * Calculate totals in shopping carts
  * Compare user permissions
  * Update counters and scores
* 🔹 **Best Practice**
  * Use `===` instead of `==` for strict equality

🟢 **JavaScript Arithmetic**
* 🔹 **Explanation**
  * Basic math operations: +, -, *, /, % (modulus), ** (exponentiation)
  * Follow standard mathematical order of operations
* 🔹 **Code Example**
```js
let a = 10;
let b = 3;

let addition = a + b;       // 13
let subtraction = a - b;    // 7
let multiplication = a * b; // 30
let division = a / b;       // 3.333...
let modulus = a % b;        // 1
let power = a ** 2;         // 100
```
* 🔹 **Real-world Use Case**
  * Calculate prices with tax
  * Determine page numbers (modulus)
  * Calculate compound interest
* 🔹 **Best Practice**
  * Use parentheses to make complex calculations clear

🟢 **JavaScript Assignment**
* 🔹 **Explanation**
  * Basic assignment (=) assigns values to variables
  * Compound assignment operators combine operation with assignment
* 🔹 **Code Example**
```js
let score = 100;        // Basic assignment

score += 10;            // score = score + 10 = 110
score -= 5;             // score = score - 5 = 105
score *= 2;             // score = score * 2 = 210
score /= 3;             // score = score / 3 = 70
score %= 8;             // score = score % 8 = 6
```
* 🔹 **Real-world Use Case**
  * Update user scores in games
  * Increment counters
  * Apply discounts to prices
* 🔹 **Shorthand**
  * `x += 1` is shorter than `x = x + 1`
* 🔹 **Best Practice**
  * Use compound operators for cleaner, more readable code

🟢 **JavaScript Comparison and Logical Operators**
* 🔹 **Explanation**
  * Comparison: ===, !==, >, <, >=, <= return true/false
  * Logical: && (and), || (or), ! (not) combine boolean values
* 🔹 **Code Example**
```js
let age = 25;
let hasLicense = true;

// Comparison
let isAdult = age >= 18;        // true
let isExact = age === 25;       // true

// Logical
let canDrive = isAdult && hasLicense;    // true
let needsHelp = !hasLicense || age < 16; // false
```
* 🔹 **Real-world Use Case**
  * Form validation (check required fields)
  * User permission checks
  * Filter search results
* 🔹 **Best Practice**
  * Use `===` and `!==` to avoid type coercion issues

🟢 **JavaScript Operator Precedence**
* 🔹 **Explanation**
  * Order in which operators are evaluated in expressions
  * Multiplication and division before addition and subtraction
* 🔹 **Code Example**
```js
let result1 = 2 + 3 * 4;        // 14 (not 20)
let result2 = (2 + 3) * 4;      // 20

let bool1 = true || false && false;  // true
let bool2 = (true || false) && false; // false
```
* 🔹 **Real-world Use Case**
  * Complex pricing calculations
  * Boolean logic for user permissions
  * Mathematical formulas
* 🔹 **Best Practice**
  * Use parentheses to make intentions clear, even when not required

🟢 **JavaScript Booleans**
* 🔹 **Explanation**
  * Represent true or false values
  * Used in conditions, flags, and toggle states
* 🔹 **Code Example**
```js
let isLoggedIn = true;
let hasPermission = false;

// Falsy values become false
let falsy1 = Boolean(0);        // false
let falsy2 = Boolean("");       // false
let falsy3 = Boolean(null);     // false

// Truthy values become true
let truthy = Boolean("hello");  // true
```
* 🔹 **Real-world Use Case**
  * Toggle switches (dark mode on/off)
  * Form validation states
  * Feature flags in applications
* 🔹 **Best Practice**
  * Use descriptive names like `isVisible` instead of just `visible`

### ✅ **Beginner Integration Tasks**
1. **Variable Practice**: Create variables for a user profile (name, age, isActive) and display them using string concatenation and template literals.
2. **Type Conversion Challenge**: Take a string input "25" and a number 5, convert appropriately, and perform arithmetic operations showing the results.
3. **Boolean Logic**: Create a simple login validator that checks if username length > 3 AND password length > 6, displaying appropriate messages.

---

## CONTROL FLOW

🟢 **JavaScript if, else, and else if**
* 🔹 **Explanation**
  * Execute different code blocks based on conditions
  * `if` runs when condition is true, `else` runs when false, `else if` provides additional conditions
* 🔹 **Code Example**
```js
let score = 85;

if (score >= 90) {
    console.log("Grade: A");
} else if (score >= 80) {
    console.log("Grade: B");
} else if (score >= 70) {
    console.log("Grade: C");
} else {
    console.log("Grade: F");
}
```
* 🔹 **Real-world Use Case**
  * User authentication checks
  * Form validation messages
  * Different content based on user roles
* 🔹 **Shorthand**
  * Ternary operator: `let grade = score >= 90 ? "A" : "B";`
* 🔹 **Best Practice**
  * Always use braces {} even for single statements

🟢 **JavaScript Switch Statement**
* 🔹 **Explanation**
  * Alternative to multiple if/else statements for exact value matching
  * More readable when checking one variable against many values
* 🔹 **Code Example**
```js
let day = "Monday";

switch (day) {
    case "Monday":
        console.log("Start of work week");
        break;
    case "Friday":
        console.log("TGIF!");
        break;
    case "Saturday":
    case "Sunday":
        console.log("Weekend!");
        break;
    default:
        console.log("Regular day");
}
```
* 🔹 **Real-world Use Case**
  * Menu navigation handling
  * Different API endpoints based on user role
  * Game state management
* 🔹 **Best Practice**
  * Always include `break` statements and a `default` case

🟢 **JavaScript For Loop**
* 🔹 **Explanation**
  * Repeats code a specific number of times
  * Three parts: initialization, condition, increment
* 🔹 **Code Example**
```js
// Basic for loop
for (let i = 0; i < 5; i++) {
    console.log("Count: " + i);
}

// Loop through array
let fruits = ["apple", "banana", "orange"];
for (let i = 0; i < fruits.length; i++) {
    console.log(fruits[i]);
}

// For...of loop (modern)
for (let fruit of fruits) {
    console.log(fruit);
}
```
* 🔹 **Real-world Use Case**
  * Display lists of products
  * Process form inputs
  * Generate HTML elements dynamically
* 🔹 **Shorthand**
  * `for...of` for arrays, `for...in` for objects
* 🔹 **Best Practice**
  * Use `for...of` for arrays when you don't need the index

🟢 **JavaScript While Loop**
* 🔹 **Explanation**
  * Repeats code while a condition remains true
  * `do...while` executes at least once before checking condition
* 🔹 **Code Example**
```js
// While loop
let count = 0;
while (count < 3) {
    console.log("Count: " + count);
    count++;
}

// Do...while loop
let userInput;
do {
    userInput = prompt("Enter 'quit' to exit:");
} while (userInput !== "quit");
```
* 🔹 **Real-world Use Case**
  * Keep asking for input until valid
  * Process data until end condition met
  * Game loops that run until game over
* 🔹 **Best Practice**
  * Always ensure the condition will eventually become false to avoid infinite loops

🟢 **JavaScript Break and Continue**
* 🔹 **Explanation**
  * `break` exits the entire loop immediately
  * `continue` skips current iteration and moves to next
* 🔹 **Code Example**
```js
// Break example
for (let i = 0; i < 10; i++) {
    if (i === 5) {
        break;  // Exit loop when i equals 5
    }
    console.log(i);  // Prints 0, 1, 2, 3, 4
}

// Continue example
for (let i = 0; i < 5; i++) {
    if (i === 2) {
        continue;  // Skip when i equals 2
    }
    console.log(i);  // Prints 0, 1, 3, 4
}
```
* 🔹 **Real-world Use Case**
  * Exit search when item found
  * Skip invalid data in processing
  * Handle special cases in loops
* 🔹 **Best Practice**
  * Use sparingly; often better to restructure logic

### ✅ **Control Flow Integration Tasks**
1. **Grade Calculator**: Create a program that takes an array of scores, uses loops to calculate average, and uses if/else to assign letter grades.
2. **Menu System**: Build a switch-based menu system that continues to prompt user for choices until they select "quit".
3. **Number Processor**: Use while loop to keep asking for numbers, skip negative numbers with continue, and break when user enters 0, then display sum.

---

## FUNCTIONS & SCOPE

🟢 **JavaScript Functions**
* 🔹 **Explanation**
  * Reusable blocks of code that perform specific tasks
  * Can accept inputs (parameters) and return outputs
* 🔹 **Code Example**
```js
// Function declaration
function greetUser(name) {
    return "Hello, " + name + "!";
}

// Function expression
const calculateArea = function(width, height) {
    return width * height;
};

// Arrow function
const multiply = (a, b) => a * b;

// Usage
let message = greetUser("Alice");
console.log(message);  // "Hello, Alice!"
```
* 🔹 **Real-world Use Case**
  * Form validation functions
  * API call handlers
  * Data processing utilities
* 🔹 **Best Practice**
  * Use descriptive function names that explain what they do

🟢 **JavaScript Function Definitions**
* 🔹 **Explanation**
  * Function declarations are hoisted (can be called before definition)
  * Function expressions and arrow functions are not hoisted
* 🔹 **Code Example**
```js
// Function Declaration (hoisted)
function addNumbers(a, b) {
    return a + b;
}

// Function Expression (not hoisted)
const subtractNumbers = function(a, b) {
    return a - b;
};

// Arrow Function (not hoisted)
const divideNumbers = (a, b) => {
    return a / b;
};

// Short arrow function
const square = x => x * x;
```
* 🔹 **Real-world Use Case**
  * Event handlers for buttons
  * Utility functions for calculations
  * Data transformation functions
* 🔹 **Shorthand**
  * Arrow functions: `const add = (a, b) => a + b;`
* 🔹 **Best Practice**
  * Use arrow functions for short, simple operations

🟢 **JavaScript Function Parameters**
* 🔹 **Explanation**
  * Variables that accept values passed to functions
  * Can have default values and rest parameters
* 🔹 **Code Example**
```js
// Default parameters
function greet(name = "Guest", greeting = "Hello") {
    return `${greeting}, ${name}!`;
}

// Rest parameters
function sum(...numbers) {
    return numbers.reduce((total, num) => total + num, 0);
}

// Usage
console.log(greet());                    // "Hello, Guest!"
console.log(greet("Alice", "Welcome"));  // "Welcome, Alice!"
console.log(sum(1, 2, 3, 4, 5));        // 15
```
* 🔹 **Real-world Use Case**
  * Configuration functions with optional settings
  * Functions that handle variable number of inputs
  * API functions with default values
* 🔹 **Best Practice**
  * Always provide default values for optional parameters

🟢 **JavaScript Function Invocation**
* 🔹 **Explanation**
  * Different ways to call functions affect the `this` context
  * Functions can be called directly, as methods, or with call/apply
* 🔹 **Code Example**
```js
function sayHello() {
    console.log("Hello from " + this.name);
}

const person = {
    name: "Alice",
    greet: sayHello
};

// Direct invocation
sayHello();         // "Hello from undefined"

// Method invocation
person.greet();     // "Hello from Alice"

// Constructor invocation
function Person(name) {
    this.name = name;
}
const user = new Person("Bob");
```
* 🔹 **Real-world Use Case**
  * Object methods for user actions
  * Constructor functions for creating instances
  * Event handlers bound to elements
* 🔹 **Best Practice**
  * Use arrow functions to preserve `this` context

🟢 **JavaScript Function call()**
* 🔹 **Explanation**
  * Calls function with specific `this` value and individual arguments
  * First parameter sets `this`, remaining are function arguments
* 🔹 **Code Example**
```js
function introduce(age, city) {
    return `Hi, I'm ${this.name}, ${age} years old from ${city}`;
}

const person1 = { name: "Alice" };
const person2 = { name: "Bob" };

// Using call()
let intro1 = introduce.call(person1, 25, "New York");
let intro2 = introduce.call(person2, 30, "London");

console.log(intro1);  // "Hi, I'm Alice, 25 years old from New York"
console.log(intro2);  // "Hi, I'm Bob, 30 years old from London"
```
* 🔹 **Real-world Use Case**
  * Borrowing methods from other objects
  * Setting specific context for callback functions
  * Function composition and method sharing
* 🔹 **Best Practice**
  * Use when you need to explicitly set `this` context

🟢 **JavaScript Function apply()**
* 🔹 **Explanation**
  * Similar to call() but accepts arguments as an array
  * Useful when you have arguments in array format
* 🔹 **Code Example**
```js
function calculateTotal(price, tax, discount) {
    return `Total for ${this.item}: $${price + tax - discount}`;
}

const product = { item: "Laptop" };
const priceData = [1000, 100, 50];

// Using apply()
let total = calculateTotal.apply(product, priceData);
console.log(total);  // "Total for Laptop: $1050"

// Math.max with apply
let numbers = [5, 10, 2, 8];
let max = Math.max.apply(null, numbers);  // 10
```
* 🔹 **Real-world Use Case**
  * Working with arrays of arguments
  * Math operations on array values
  * Dynamic function calls with variable arguments
* 🔹 **Shorthand**
  * Use spread operator: `Math.max(...numbers)`
* 🔹 **Best Practice**
  * Prefer spread operator in modern JavaScript

🟢 **JavaScript Function bind()**
* 🔹 **Explanation**
  * Creates new function with fixed `this` value and optional preset arguments
  * Returns new function instead of calling immediately
* 🔹 **Code Example**
```js
const person = {
    name: "Alice",
    greet: function(greeting, punctuation) {
        return `${greeting}, I'm ${this.name}${punctuation}`;
    }
};

// Bind with this context
const boundGreet = person.greet.bind(person);
console.log(boundGreet("Hello", "!"));  // "Hello, I'm Alice!"

// Bind with preset arguments
const casualGreet = person.greet.bind(person, "Hey");
console.log(casualGreet("?"));  // "Hey, I'm Alice?"
```
* 🔹 **Real-world Use Case**
  * Event handlers that need specific context
  * Creating specialized versions of functions
  * Callback functions with fixed parameters
* 🔹 **Best Practice**
  * Use bind() for event handlers to maintain object context

🟢 **JavaScript Nested Functions**
* 🔹 **Explanation**
  * Functions defined inside other functions
  * Inner functions have access to outer function's variables (closure)
* 🔹 **Code Example**
```js
function outerFunction(x) {
    // Outer function variable
    let outerVar = x;
    
    // Nested function
    function innerFunction(y) {
        return outerVar + y;  // Access outer variable
    }
    
    return innerFunction;
}

const addToFive = outerFunction(5);
console.log(addToFive(3));  // 8

// Practical example
function createCounter() {
    let count = 0;
    
    return function() {
        count++;
        return count;
    };
}

const counter = createCounter();
console.log(counter());  // 1
console.log(counter());  // 2
```
* 🔹 **Real-world Use Case**
  * Private variables and methods
  * Function factories
  * Module patterns
* 🔹 **Best Practice**
  * Use for creating private scope and data encapsulation

🟢 **JavaScript Scope**
* 🔹 **Explanation**
  * Global scope: accessible everywhere in program
  * Function scope: accessible only within function
  * Block scope: accessible only within block (let/const)
* 🔹 **Code Example**
```js
let globalVar = "I'm global";      // Global scope

function myFunction() {
    let functionVar = "I'm in function";  // Function scope
    
    if (true) {
        let blockVar = "I'm in block";    // Block scope
        const alsoBlock = "Me too";       // Block scope
        var functionScoped = "I'm function scoped"; // Function scope
    }
    
    console.log(globalVar);        // ✓ Works
    console.log(functionVar);      // ✓ Works
    console.log(functionScoped);   // ✓ Works
    // console.log(blockVar);      // ✗ Error
}
```
* 🔹 **Real-world Use Case**
  * Preventing variable name conflicts
  * Creating private variables
  * Managing application state
* 🔹 **Best Practice**
  * Use `let` and `const` for proper block scoping

🟢 **JavaScript Hoisting**
* 🔹 **Explanation**
  * Variable and function declarations are moved to top of scope
  * `var` variables are hoisted with `undefined` value
  * `let` and `const` are hoisted but not initialized (temporal dead zone)
* 🔹 **Code Example**
```js
// This works due to function hoisting
console.log(sayHello("World"));  // "Hello, World!"

function sayHello(name) {
    return "Hello, " + name + "!";
}

// Variable hoisting with var
console.log(myVar);  // undefined (not error)
var myVar = "Hello";

// let/const hoisting - temporal dead zone
// console.log(myLet);  // ReferenceError
let myLet = "World";
```
* 🔹 **Real-world Use Case**
  * Understanding why code works in unexpected orders
  * Debugging variable access issues
  * Writing more predictable code
* 🔹 **Best Practice**
  * Declare variables at the top of their scope for clarity

🟢 **JavaScript this Keyword**
* 🔹 **Explanation**
  * Refers to object that owns the currently executing code
  * Value depends on how function is called
* 🔹 **Code Example**
```js
const person = {
    name: "Alice",
    regularFunction: function() {
        console.log("Regular:", this.name);  // "Alice"
    },
    arrowFunction: () => {
        console.log("Arrow:", this.name);    // undefined
    },
    nestedExample: function() {
        const inner = () => {
            console.log("Nested arrow:", this.name);  // "Alice"
        };
        inner();
    }
};

person.regularFunction();  // Regular: Alice
person.arrowFunction();    // Arrow: undefined
person.nestedExample();    // Nested arrow: Alice
```
* 🔹 **Real-world Use Case**
  * Object methods accessing object properties
  * Event handlers needing element context
  * Class methods and constructors
* 🔹 **Best Practice**
  * Use arrow functions to preserve `this` context from enclosing scope

### ✅ **Functions & Scope Integration Tasks**
1. **Calculator Factory**: Create a function that returns an object with calculator methods (add, subtract, multiply, divide) that maintain their own running total using closure.
2. **Event Handler Manager**: Build a system using bind() to create event handlers that maintain context, with nested functions for validation.
3. **Scope Detective**: Create examples demonstrating hoisting behavior with var, let, and const, showing how `this` context changes in different scenarios.

---

## STRINGS & NUMBERS

🟢 **JavaScript Strings**
* 🔹 **Explanation**
  * Text data enclosed in quotes (single, double, or backticks)
  * Immutable - string methods return new strings
* 🔹 **Code Example**
```js
let singleQuote = 'Hello World';
let doubleQuote = "Hello World";
let templateLiteral = `Hello ${name}`;  // Template literal

// String properties and basic methods
let text = "JavaScript";
console.log(text.length);        // 10
console.log(text[0]);            // "J"
console.log(text.charAt(4));     // "S"

// Template literals with expressions
let price = 19.99;
let message = `The price is $${price.toFixed(2)}`;
```
* 🔹 **Real-world Use Case**
  * Display user names and messages
  * Format prices and dates
  * Generate HTML content dynamically
* 🔹 **Shorthand**
  * Template literals: `Hello ${variable}` instead of `"Hello " + variable`
* 🔹 **Best Practice**
  * Use template literals for string interpolation

🟢 **JavaScript String Methods**
* 🔹 **Explanation**
  * Built-in functions to manipulate and analyze strings
  * Return new strings without modifying original
* 🔹 **Code Example**
```js
let text = "  Hello World  ";

// Case methods
console.log(text.toLowerCase());     // "  hello world  "
console.log(text.toUpperCase());     // "  HELLO WORLD  "

// Whitespace methods
console.log(text.trim());            // "Hello World"
console.log(text.trimStart());       // "Hello World  "

// Manipulation methods
console.log(text.replace("World", "JS"));  // "  Hello JS  "
console.log(text.slice(2, 7));            // "Hello"
console.log(text.substring(2, 7));        // "Hello"
console.log(text.split(" "));             // ["", "", "Hello", "World", "", ""]
```
* 🔹 **Real-world Use Case**
  * Clean user input (trim whitespace)
  * Format names (capitalize first letter)
  * Parse CSV data (split on commas)
* 🔹 **Best Practice**
  * Always trim user input from forms

🟢 **JavaScript String Search**
* 🔹 **Explanation**
  * Find and locate text within strings
  * Methods return positions or boolean values
* 🔹 **Code Example**
```js
let text = "The quick brown fox jumps over the lazy dog";

// Search methods
console.log(text.indexOf("fox"));           // 16
console.log(text.lastIndexOf("the"));       // 31
console.log(text.includes("brown"));        // true
console.log(text.startsWith("The"));        // true
console.log(text.endsWith("dog"));          // true

// Advanced search with regex
console.log(text.search(/fox/i));           // 16
console.log(text.match(/the/gi));           // ["The", "the"]
```
* 🔹 **Real-world Use Case**
  * Search functionality in applications
  * Validate email formats
  * Check if URL contains specific domain
* 🔹 **Best Practice**
  * Use `includes()` for simple existence checks

🟢 **JavaScript String Reference**
* 🔹 **Explanation**
  * Complete reference of string properties and methods
  * Includes length property and all manipulation methods
* 🔹 **Code Example**
```js
let str = "JavaScript Programming";

// Length and character access
console.log(str.length);                    // 21
console.log(str.charAt(4));                 // "S"
console.log(str.charCodeAt(0));             // 74 (Unicode)

// Extraction methods
console.log(str.slice(0, 10));              // "JavaScript"
console.log(str.substring(11));             // "Programming"
console.log(str.substr(11, 7));             // "Program" (deprecated)

// Conversion methods
console.log(str.split(" "));                // ["JavaScript", "Programming"]
console.log(str.repeat(2));                 // "JavaScript ProgrammingJavaScript Programming"
```
* 🔹 **Real-world Use Case**
  * Text processing applications
  * Data parsing and formatting
  * Input validation and sanitization
* 🔹 **Best Practice**
  * Learn the most commonly used methods: slice, includes, trim, split

🟢 **JavaScript Numbers**
* 🔹 **Explanation**
  * Numeric data type for integers and floating-point numbers
  * JavaScript has only one number type (64-bit floating point)
* 🔹 **Code Example**
```js
let integer = 42;
let decimal = 3.14159;
let negative = -25;
let scientific = 2.5e6;  // 2500000

// Special number values
let infinity = Infinity;
let negInfinity = -Infinity;
let notANumber = NaN;

// Number checks
console.log(isNaN("hello"));        // true
console.log(isFinite(100));         // true
console.log(Number.isInteger(42));  // true
```
* 🔹 **Real-world Use Case**
  * Prices, quantities, measurements
  * Calculations and mathematical operations
  * Counters and indices
* 🔹 **Best Practice**
  * Use `Number.isNaN()` instead of `isNaN()` for strict checking

🟢 **JavaScript Number Methods**
* 🔹 **Explanation**
  * Built-in methods to format and manipulate numbers
  * Include conversion, precision, and formatting methods
* 🔹 **Code Example**
```js
let num = 123.456789;

// Formatting methods
console.log(num.toFixed(2));        // "123.46"
console.log(num.toPrecision(5));    // "123.46"
console.log(num.toExponential(2));  // "1.23e+2"

// Conversion methods
console.log(num.toString());        // "123.456789"
console.log(num.toString(2));       // Binary: "1111011.01110101..."

// Parsing methods
console.log(parseInt("123.45"));    // 123
console.log(parseFloat("123.45"));  // 123.45
console.log(Number("123.45"));      // 123.45
```
* 🔹 **Real-world Use Case**
  * Format currency displays
  * Round user input to specific decimals
  * Convert strings to numbers from forms
* 🔹 **Best Practice**
  * Use `toFixed()` for currency formatting

🟢 **JavaScript Number Properties**
* 🔹 **Explanation**
  * Static properties that define number limits and special values
  * Include maximum/minimum values and epsilon for precision
* 🔹 **Code Example**
```js
// Number limits
console.log(Number.MAX_VALUE);          // 1.7976931348623157e+308
console.log(Number.MIN_VALUE);          // 5e-324
console.log(Number.MAX_SAFE_INTEGER);   // 9007199254740991
console.log(Number.MIN_SAFE_INTEGER);   // -9007199254740991

// Special values
console.log(Number.POSITIVE_INFINITY);  // Infinity
console.log(Number.NEGATIVE_INFINITY);  // -Infinity
console.log(Number.NaN);                // NaN
console.log(Number.EPSILON);            // 2.220446049250313e-16
```
* 🔹 **Real-world Use Case**
  * Validate number ranges in applications
  * Check for safe integer operations
  * Handle edge cases in calculations
* 🔹 **Best Practice**
  * Use `Number.isSafeInteger()` for large number operations

🟢 **JavaScript Number Reference**
* 🔹 **Explanation**
  * Complete reference of number methods and properties
  * Includes static methods for validation and conversion
* 🔹 **Code Example**
```js
// Static Number methods
console.log(Number.isInteger(42));      // true
console.log(Number.isInteger(42.0));    // true
console.log(Number.isInteger(42.1));    // false

console.log(Number.isSafeInteger(123)); // true
console.log(Number.isFinite(100));      // true
console.log(Number.isNaN(NaN));         // true

// Global functions (less preferred)
console.log(parseInt("42px"));          // 42
console.log(parseFloat("42.5rem"));     // 42.5
console.log(isNaN("hello"));            // true (converts to number first)
```
* 🔹 **Real-world Use Case**
  * Form validation for numeric inputs
  * Data type checking in APIs
  * Safe mathematical operations
* 🔹 **Best Practice**
  * Prefer `Number.` methods over global functions for strict checking

### ✅ **Strings & Numbers Integration Tasks**
1. **Text Formatter**: Create a function that takes a string, capitalizes first letter of each word, removes extra spaces, and returns character count.
2. **Price Calculator**: Build a system that takes string prices, converts to numbers, applies discounts, and formats as currency with proper decimal places.
3. **Data Validator**: Create validators for email format (using string methods), phone numbers (using number parsing), and clean/format the results.

---

## ARRAYS & OBJECTS

🟢 **JavaScript Arrays**
* 🔹 **Explanation**
  * Ordered collections of items stored in a single variable
  * Zero-indexed with dynamic size and mixed data types
* 🔹 **Code Example**
```js
// Creating arrays
let fruits = ["apple", "banana", "orange"];
let numbers = [1, 2, 3, 4, 5];
let mixed = ["hello", 42, true, null];

// Array properties and access
console.log(fruits.length);     // 3
console.log(fruits[0]);         // "apple"
console.log(fruits[fruits.length - 1]);  // "orange"

// Modifying arrays
fruits[1] = "grape";            // Change element
fruits.push("mango");           // Add to end
fruits.unshift("strawberry");   // Add to beginning
```
* 🔹 **Real-world Use Case**
  * Store shopping cart items
  * List of users or products
  * Navigation menu items
* 🔹 **Best Practice**
  * Use descriptive array names like `userNames` instead of `arr`

🟢 **JavaScript Array Methods**
* 🔹 **Explanation**
  * Built-in functions to manipulate arrays
  * Mutating methods change original array, non-mutating return new array
* 🔹 **Code Example**
```js
let fruits = ["apple", "banana", "orange"];

// Adding/removing elements
fruits.push("grape");           // ["apple", "banana", "orange", "grape"]
fruits.pop();                   // Removes "grape", returns it
fruits.unshift("strawberry");   // Adds to beginning
fruits.shift();                 // Removes from beginning

// Combining and slicing
let vegetables = ["carrot", "broccoli"];
let food = fruits.concat(vegetables);    // Combine arrays
let citrus = fruits.slice(1, 3);        // Extract portion

// Converting
let str = fruits.join(", ");            // "apple, banana, orange"
let reversed = fruits.reverse();         // Reverses original array
```
* 🔹 **Real-world Use Case**
  * Manage shopping cart additions/removals
  * Combine data from multiple sources
  * Create comma-separated lists for display
* 🔹 **Shorthand**
  * Spread operator: `[...arr1, ...arr2]` to combine arrays
* 🔹 **Best Practice**
  * Use `slice()` to copy arrays before modifying

🟢 **JavaScript Array Search**
* 🔹 **Explanation**
  * Methods to find elements, their positions, or check existence
  * Return indices, elements, or boolean values
* 🔹 **Code Example**
```js
let numbers = [10, 20, 30, 40, 50];
let users = [
    { name: "Alice", age: 25 },
    { name: "Bob", age: 30 },
    { name: "Carol", age: 35 }
];

// Basic search methods
console.log(numbers.indexOf(30));       // 2
console.log(numbers.lastIndexOf(30));   // 2
console.log(numbers.includes(25));      // false

// Advanced search methods
let found = users.find(user => user.age > 28);        // { name: "Bob", age: 30 }
let foundIndex = users.findIndex(user => user.age > 28);  // 1
let adults = users.filter(user => user.age >= 30);    // [Bob, Carol]
```
* 🔹 **Real-world Use Case**
  * Find user by ID in user list
  * Check if product exists in cart
  * Filter products by category or price
* 🔹 **Best Practice**
  * Use `find()` for single items, `filter()` for multiple matches

🟢 **JavaScript Array Sort**
* 🔹 **Explanation**
  * Sort array elements in place (modifies original array)
  * Default sort converts to strings; use compare function for numbers
* 🔹 **Code Example**
```js
let fruits = ["banana", "apple", "orange", "grape"];
let numbers = [10, 5, 40, 25, 1000, 1];

// String sorting (default)
fruits.sort();                          // ["apple", "banana", "grape", "orange"]
fruits.sort().reverse();                // ["orange", "grape", "banana", "apple"]

// Number sorting (requires compare function)
numbers.sort((a, b) => a - b);          // [1, 5, 10, 25, 40, 1000]
numbers.sort((a, b) => b - a);          // [1000, 40, 25, 10, 5, 1]

// Object sorting
let users = [
    { name: "Alice", age: 30 },
    { name: "Bob", age: 25 },
    { name: "Carol", age: 35 }
];
users.sort((a, b) => a.age - b.age);    // Sort by age ascending
```
* 🔹 **Real-world Use Case**
  * Sort products by price or rating
  * Alphabetize user lists
  * Order items by date or priority
* 🔹 **Best Practice**
  * Always use compare function for number sorting

🟢 **JavaScript Array Iterations**
* 🔹 **Explanation**
  * Methods to loop through arrays and transform data
  * Include forEach, map, filter, reduce for different use cases
* 🔹 **Code Example**
```js
let numbers = [1, 2, 3, 4, 5];

// forEach - execute function for each element
numbers.forEach(num => console.log(num * 2));

// map - transform each element, return new array
let doubled = numbers.map(num => num * 2);        // [2, 4, 6, 8, 10]

// filter - return elements that pass test
let evens = numbers.filter(num => num % 2 === 0); // [2, 4]

// reduce - reduce array to single value
let sum = numbers.reduce((total, num) => total + num, 0);  // 15

// Method chaining
let result = numbers
    .filter(num => num > 2)     // [3, 4, 5]
    .map(num => num * 2)        // [6, 8, 10]
    .reduce((sum, num) => sum + num, 0);  // 24
```
* 🔹 **Real-world Use Case**
  * Calculate shopping cart totals
  * Transform API data for display
  * Filter search results
* 🔹 **Best Practice**
  * Chain methods for readable data transformations

🟢 **JavaScript Objects**
* 🔹 **Explanation**
  * Collections of key-value pairs (properties and methods)
  * Created with object literals, constructors, or Object.create()
* 🔹 **Code Example**
```js
// Object literal
let person = {
    name: "Alice",
    age: 25,
    city: "New York",
    greet: function() {
        return `Hello, I'm ${this.name}`;
    }
};

// Accessing properties
console.log(person.name);           // "Alice"
console.log(person["age"]);         // 25
console.log(person.greet());        // "Hello, I'm Alice"

// Adding/modifying properties
person.email = "alice@email.com";   // Add property
person.age = 26;                    // Modify property
delete person.city;                 // Remove property
```
* 🔹 **Real-world Use Case**
  * Store user profiles and settings
  * Configuration objects for applications
  * Data structures for API responses
* 🔹 **Best Practice**
  * Use consistent naming conventions for properties

🟢 **JavaScript Object Definition**
* 🔹 **Explanation**
  * Various ways to create and define objects
  * Include literals, constructors, classes, and factory functions
* 🔹 **Code Example**
```js
// Object literal
let car1 = {
    brand: "Toyota",
    model: "Camry",
    year: 2022
};

// Constructor function
function Car(brand, model, year) {
    this.brand = brand;
    this.model = model;
    this.year = year;
}
let car2 = new Car("Honda", "Civic", 2021);

// Object.create()
let carPrototype = {
    start: function() { return `${this.brand} started`; }
};
let car3 = Object.create(carPrototype);
car3.brand = "Ford";

// Factory function
function createCar(brand, model, year) {
    return {
        brand,
        model,
        year,
        getInfo() { return `${brand} ${model} ${year}`; }
    };
}
let car4 = createCar("BMW", "X5", 2023);
```
* 🔹 **Real-world Use Case**
  * Create multiple similar objects (users, products)
  * Define object templates and blueprints
  * Build reusable object creation patterns
* 🔹 **Shorthand**
  * Property shorthand: `{ name, age }` instead of `{ name: name, age: age }`
* 🔹 **Best Practice**
  * Use object literals for single instances, constructors for multiple

🟢 **JavaScript Object Properties**
* 🔹 **Explanation**
  * Ways to access, modify, and work with object properties
  * Include dot notation, bracket notation, and property descriptors
* 🔹 **Code Example**
```js
let user = {
    firstName: "John",
    lastName: "Doe",
    age: 30
};

// Property access
console.log(user.firstName);        // "John"
console.log(user["lastName"]);      // "Doe"

// Dynamic property access
let prop = "age";
console.log(user[prop]);            // 30

// Property existence
console.log("age" in user);         // true
console.log(user.hasOwnProperty("age")); // true

// Get all properties
console.log(Object.keys(user));     // ["firstName", "lastName", "age"]
console.log(Object.values(user));   // ["John", "Doe", 30]
console.log(Object.entries(user));  // [["firstName", "John"], ...]
```
* 🔹 **Real-world Use Case**
  * Dynamic property access based on user input
  * Iterate over object properties
  * Check if required properties exist
* 🔹 **Best Practice**
  * Use dot notation when property name is known, brackets for dynamic access

🟢 **JavaScript Object Methods**
* 🔹 **Explanation**
  * Functions that belong to objects and operate on object data
  * Access object properties using `this` keyword
* 🔹 **Code Example**
```js
let calculator = {
    result: 0,
    
    add(num) {
        this.result += num;
        return this;  // Enable method chaining
    },
    
    subtract(num) {
        this.result -= num;
        return this;
    },
    
    multiply(num) {
        this.result *= num;
        return this;
    },
    
    getValue() {
        return this.result;
    },
    
    reset() {
        this.result = 0;
        return this;
    }
};

// Method chaining
let final = calculator
    .add(10)
    .multiply(2)
    .subtract(5)
    .getValue();    // 15
```
* 🔹 **Real-world Use Case**
  * User account methods (login, logout, updateProfile)
  * Shopping cart methods (addItem, removeItem, getTotal)
  * API service methods (get, post, put, delete)
* 🔹 **Best Practice**
  * Return `this` from methods to enable chaining

🟢 **JavaScript Object Constructors**
* 🔹 **Explanation**
  * Functions used with `new` keyword to create object instances
  * Define templates for creating multiple similar objects
* 🔹 **Code Example**
```js
// Constructor function
function Person(name, age, city) {
    this.name = name;
    this.age = age;
    this.city = city;
    
    this.introduce = function() {
        return `Hi, I'm ${this.name} from ${this.city}`;
    };
}

// Creating instances
let person1 = new Person("Alice", 25, "New York");
let person2 = new Person("Bob", 30, "London");

console.log(person1.introduce());  // "Hi, I'm Alice from New York"
console.log(person2.introduce());  // "Hi, I'm Bob from London"

// Check instance
console.log(person1 instanceof Person);  // true
```
* 🔹 **Real-world Use Case**
  * Create user accounts with similar structure
  * Generate product objects for e-commerce
  * Build game characters or entities
* 🔹 **Best Practice**
  * Use PascalCase for constructor function names

🟢 **JavaScript Object Accessors**
* 🔹 **Explanation**
  * Getter and setter methods that control property access
  * Allow computed properties and validation on assignment
* 🔹 **Code Example**
```js
let person = {
    firstName: "John",
    lastName: "Doe",
    
    // Getter
    get fullName() {
        return `${this.firstName} ${this.lastName}`;
    },
    
    // Setter
    set fullName(value) {
        let parts = value.split(" ");
        this.firstName = parts[0];
        this.lastName = parts[1];
    },
    
    get age() {
        return this._age;
    },
    
    set age(value) {
        if (value < 0 || value > 150) {
            throw new Error("Invalid age");
        }
        this._age = value;
    }
};

// Using accessors
console.log(person.fullName);       // "John Doe"
person.fullName = "Jane Smith";     // Uses setter
console.log(person.firstName);      // "Jane"

person.age = 25;                    // Uses setter with validation
console.log(person.age);            // 25
```
* 🔹 **Real-world Use Case**
  * Computed properties like fullName, totalPrice
  * Data validation on property assignment
  * Read-only or write-only properties
* 🔹 **Best Practice**
  * Use getters for computed properties, setters for validation

🟢 **JavaScript Object Prototypes**
* 🔹 **Explanation**
  * Mechanism for objects to inherit properties and methods
  * All objects have a prototype chain leading to Object.prototype
* 🔹 **Code Example**
```js
// Constructor function
function Animal(name) {
    this.name = name;
}

// Add method to prototype
Animal.prototype.speak = function() {
    return `${this.name} makes a sound`;
};

Animal.prototype.type = "Unknown";

// Create instances
let dog = new Animal("Buddy");
let cat = new Animal("Whiskers");

console.log(dog.speak());           // "Buddy makes a sound"
console.log(cat.speak());           // "Whiskers makes a sound"
console.log(dog.type);              // "Unknown"

// Prototype inheritance
function Dog(name, breed) {
    Animal.call(this, name);
    this.breed = breed;
}

Dog.prototype = Object.create(Animal.prototype);
Dog.prototype.constructor = Dog;

Dog.prototype.speak = function() {
    return `${this.name} barks`;
};

let myDog = new Dog("Rex", "Golden Retriever");
console.log(myDog.speak());         // "Rex barks"
```
* 🔹 **Real-world Use Case**
  * Share methods across all instances to save memory
  * Create inheritance hierarchies
  * Extend built-in objects (carefully)
* 🔹 **Best Practice**
  * Add methods to prototype, not in constructor for better performance

### ✅ **Arrays & Objects Integration Tasks**
1. **Contact Manager**: Create an array of contact objects with methods to add, remove, search by name, and sort by different properties using array methods.
2. **Shopping Cart System**: Build a cart object with items array, using array methods for calculations (total, tax, discounts) and object methods for cart operations.
3. **Data Processor**: Create a system that takes raw data arrays, uses array iteration methods to clean and transform data, then organizes into structured objects with accessors.

---

## DOM & EVENTS

🟢 **JavaScript Events**
* 🔹 **Explanation**
  * Actions that occur in the browser (clicks, key presses, page loads)
  * JavaScript can respond to events with event handlers
* 🔹 **Code Example**
```js
// Event handler methods
// Method 1: HTML attribute
// <button onclick="handleClick()">Click me</button>

// Method 2: DOM property
let button = document.getElementById("myButton");
button.onclick = function() {
    alert("Button clicked!");
};

// Method 3: addEventListener (preferred)
button.addEventListener("click", function() {
    console.log("Button was clicked!");
});

// Event object
button.addEventListener("click", function(event) {
    console.log("Event type:", event.type);
    console.log("Target:", event.target);
    event.preventDefault(); // Prevent default behavior
});
```
* 🔹 **Real-world Use Case**
  * Form submissions and validation
  * Interactive buttons and menus
  * Image galleries and carousens
* 🔹 **Best Practice**
  * Use `addEventListener()` for flexibility and multiple handlers

🟢 **JavaScript Forms**
* 🔹 **Explanation**
  * Handle form inputs, validation, and submission
  * Access form elements and their values
* 🔹 **Code Example**
```js
// Form access and validation
let form = document.getElementById("userForm");
let nameInput = document.getElementById("username");
let emailInput = document.getElementById("email");

form.addEventListener("submit", function(event) {
    event.preventDefault(); // Prevent form submission
    
    // Get form values
    let name = nameInput.value.trim();
    let email = emailInput.value.trim();
    
    // Validation
    if (name === "") {
        alert("Name is required");
        nameInput.focus();
        return;
    }
    
    if (!email.includes("@")) {
        alert("Valid email is required");
        emailInput.focus();
        return;
    }
    
    // Process form data
    console.log("Form submitted:", { name, email });
});

// Real-time validation
nameInput.addEventListener("input", function() {
    if (this.value.length < 3) {
        this.style.borderColor = "red";
    } else {
        this.style.borderColor = "green";
    }
});
```
* 🔹 **Real-world Use Case**
  * User registration and login forms
  * Contact forms and surveys
  * Search inputs with real-time results
* 🔹 **Best Practice**
  * Always validate on both client and server side

🟢 **JavaScript Display Objects**
* 🔹 **Explanation**
  * Methods to output and display content in the browser
  * Include console, alerts, and DOM manipulation
* 🔹 **Code Example**
```js
// Console output (for debugging)
console.log("Debug message");
console.error("Error message");
console.warn("Warning message");
console.table([{name: "Alice", age: 25}, {name: "Bob", age: 30}]);

// Alert dialogs
alert("Simple message");
let confirmed = confirm("Are you sure?");
let userInput = prompt("Enter your name:");

// DOM content display
document.getElementById("output").innerHTML = "<h2>Dynamic Content</h2>";
document.getElementById("text").textContent = "Safe text content";
document.getElementById("info").innerText = "Visible text only";

// Writing to document
document.write("Direct to document (avoid in modern apps)");
```
* 🔹 **Real-world Use Case**
  * Debug information during development
  * User confirmations and inputs
  * Dynamic content updates
* 🔹 **Best Practice**
  * Use `textContent` for plain text to prevent XSS attacks

🟢 **JavaScript HTML DOM Methods**
* 🔹 **Explanation**
  * Methods to find, access, and manipulate HTML elements
  * Include getElementById, querySelector, and element creation
* 🔹 **Code Example**
```js
// Finding elements
let elementById = document.getElementById("myId");
let elementsByClass = document.getElementsByClassName("myClass");
let elementsByTag = document.getElementsByTagName("p");

// Modern selectors (preferred)
let singleElement = document.querySelector(".myClass");
let multipleElements = document.querySelectorAll("p.highlight");

// Creating and modifying elements
let newDiv = document.createElement("div");
newDiv.textContent = "New content";
newDiv.className = "new-class";

// Adding to DOM
document.body.appendChild(newDiv);

// Removing elements
let oldElement = document.getElementById("remove-me");
if (oldElement) {
    oldElement.remove(); // Modern way
    // oldElement.parentNode.removeChild(oldElement); // Older way
}
```
* 🔹 **Real-world Use Case**
  * Dynamic content loading
  * Interactive user interfaces
  * Single-page application updates
* 🔹 **Best Practice**
  * Use `querySelector()` and `querySelectorAll()` for flexible element selection

🟢 **JavaScript HTML DOM Document**
* 🔹 **Explanation**
  * The document object represents the entire HTML page
  * Provides methods and properties to access page content
* 🔹 **Code Example**
```js
// Document properties
console.log(document.title);           // Page title
console.log(document.URL);             // Current URL
console.log(document.domain);          // Domain name
console.log(document.lastModified);    // Last modified date

// Document methods
document.write("Content"); // Avoid in modern apps
document.open();
document.close();

// Finding elements from document
let allImages = document.images;        // HTMLCollection of images
let allLinks = document.links;          // HTMLCollection of links
let allForms = document.forms;          // HTMLCollection of forms

// Document ready
document.addEventListener("DOMContentLoaded", function() {
    console.log("DOM is fully loaded");
    // Initialize your app here
});
```
* 🔹 **Real-world Use Case**
  * Initialize applications when page loads
  * Access meta information about the page
  * Global page-level operations
* 🔹 **Best Practice**
  * Use `DOMContentLoaded` event to ensure DOM is ready before manipulation

🟢 **JavaScript HTML DOM Elements**
* 🔹 **Explanation**
  * Individual HTML elements and their properties/methods
  * Access and modify element attributes, content, and styles
* 🔹 **Code Example**
```js
let element = document.getElementById("myDiv");

// Element properties
console.log(element.tagName);          // "DIV"
console.log(element.id);               // "myDiv"
console.log(element.className);        // CSS classes
console.log(element.innerHTML);        // HTML content
console.log(element.textContent);      // Text content only

// Modifying element
element.innerHTML = "<p>New HTML content</p>";
element.textContent = "New text content";
element.setAttribute("data-value", "123");
element.style.color = "blue";
element.style.fontSize = "16px";

// Element attributes
let src = element.getAttribute("src");
element.setAttribute("alt", "Description");
element.removeAttribute("title");

// CSS classes
element.classList.add("active");
element.classList.remove("inactive");
element.classList.toggle("highlight");
element.classList.contains("active"); // true/false
```
* 🔹 **Real-world Use Case**
  * Update content based on user actions
  * Toggle visibility and styles
  * Form field manipulation
* 🔹 **Best Practice**
  * Use `classList` methods instead of directly modifying `className`

🟢 **JavaScript HTML DOM Elements (Nodes)**
* 🔹 **Explanation**
  * DOM represents HTML as a tree of nodes (elements, text, attributes)
  * Navigate and manipulate the node tree structure
* 🔹 **Code Example**
```js
let element = document.getElementById("parent");

// Node properties
console.log(element.nodeType);         // 1 (Element node)
console.log(element.nodeName);         // Tag name
console.log(element.nodeValue);        // null for elements

// Node relationships
console.log(element.parentNode);       // Parent element
console.log(element.childNodes);       // All child nodes (includes text)
console.log(element.children);         // Only element children
console.log(element.firstChild);       // First child node
console.log(element.firstElementChild); // First element child
console.log(element.lastChild);        // Last child node
console.log(element.nextSibling);      // Next sibling node
console.log(element.previousSibling);  // Previous sibling node

// Node manipulation
let newNode = document.createElement("p");
element.appendChild(newNode);
element.insertBefore(newNode, element.firstChild);
element.removeChild(element.lastChild);
element.replaceChild(newNode, element.firstChild);
```
* 🔹 **Real-world Use Case**
  * Tree navigation for complex DOM structures
  * Dynamic content insertion at specific positions
  * Building DOM manipulation utilities
* 🔹 **Best Practice**
  * Use element-specific properties (`children`, `firstElementChild`) to avoid text nodes

🟢 **JavaScript HTML DOM Collections**
* 🔹 **Explanation**
  * Array-like objects containing multiple DOM elements
  * Live collections update automatically when DOM changes
* 🔹 **Code Example**
```js
// Getting collections
let divs = document.getElementsByTagName("div");        // HTMLCollection
let items = document.getElementsByClassName("item");    // HTMLCollection
let selected = document.querySelectorAll(".selected");  // NodeList

// Collection properties
console.log(divs.length);              // Number of elements

// Accessing elements
console.log(divs[0]);                  // First div
console.log(divs.item(1));             // Second div
console.log(items.namedItem("myId"));  // Element with id="myId"

// Iterating collections
// Convert to array for modern methods
let divsArray = Array.from(divs);
divsArray.forEach(div => {
    div.style.color = "blue";
});

// Or use traditional for loop
for (let i = 0; i < divs.length; i++) {
    divs[i].style.backgroundColor = "yellow";
}

// Modern iteration with for...of
for (let div of divs) {
    div.classList.add("processed");
}
```
* 🔹 **Real-world Use Case**
  * Apply styles to multiple elements
  * Process form inputs in bulk
  * Update navigation items
* 🔹 **Best Practice**
  * Convert HTMLCollections to arrays for modern array methods

🟢 **JavaScript HTML DOM Node Lists**
* 🔹 **Explanation**
  * Collections returned by `querySelectorAll()` and some other methods
  * Static collections that don't change when DOM changes
* 🔹 **Code Example**
```js
// Getting NodeLists
let paragraphs = document.querySelectorAll("p");
let buttons = document.querySelectorAll("button.active");

// NodeList methods
console.log(paragraphs.length);        // Number of nodes

// NodeList has forEach method
paragraphs.forEach((p, index) => {
    p.textContent = `Paragraph ${index + 1}`;
    p.style.marginBottom = "10px";
});

// Convert to array for more methods
let paragraphsArray = Array.from(paragraphs);
let textContents = paragraphsArray.map(p => p.textContent);

// Accessing individual nodes
console.log(paragraphs[0]);            // First paragraph
console.log(paragraphs.item(1));       // Second paragraph

// Check if NodeList is live or static
let liveList = document.getElementsByTagName("div");    // Live
let staticList = document.querySelectorAll("div");      // Static
```
* 🔹 **Real-world Use Case**
  * Batch processing of similar elements
  * Applying consistent styling or behavior
  * Form validation across multiple inputs
* 🔹 **Best Practice**
  * Use `querySelectorAll()` for static snapshots, `getElementsBy*` for live collections

🟢 **JavaScript HTML DOM - Changing HTML**
* 🔹 **Explanation**
  * Modify HTML content dynamically using JavaScript
  * Change inner HTML, text content, and attributes
* 🔹 **Code Example**
```js
let container = document.getElementById("content");

// Changing HTML content
container.innerHTML = "<h2>New Title</h2><p>New paragraph</p>";

// Changing text content (safer for user input)
let title = document.getElementById("title");
title.textContent = "Safe text content";

// Changing attributes
let image = document.getElementById("myImage");
image.src = "new-image.jpg";
image.alt = "New image description";
image.setAttribute("data-loaded", "true");

// Creating and inserting new elements
let newParagraph = document.createElement("p");
newParagraph.textContent = "This is a new paragraph";
newParagraph.className = "highlight";

// Different insertion methods
container.appendChild(newParagraph);                    // Add to end
container.insertBefore(newParagraph, container.firstChild); // Add to beginning
container.insertAdjacentHTML("beforeend", "<div>New div</div>");

// Modern insertion methods
container.prepend(newParagraph);                        // Add to beginning
container.append(newParagraph);                         // Add to end
```
* 🔹 **Real-world Use Case**
  * Dynamic content loading from APIs
  * Real-time updates without page refresh
  * Interactive user interfaces
* 🔹 **Best Practice**
  * Use `textContent` for plain text to prevent XSS attacks

🟢 **JavaScript HTML DOM - Changing CSS**
* 🔹 **Explanation**
  * Modify element styles dynamically using JavaScript
  * Change individual style properties or CSS classes
* 🔹 **Code Example**
```js
let element = document.getElementById("myDiv");

// Changing individual style properties
element.style.color = "blue";
element.style.backgroundColor = "yellow";
element.style.fontSize = "18px";
element.style.marginTop = "20px";

// CSS properties with hyphens use camelCase
element.style.borderRadius = "10px";
element.style.boxShadow = "2px 2px 5px rgba(0,0,0,0.3)";

// Getting computed styles
let computedStyle = window.getComputedStyle(element);
console.log(computedStyle.color);
console.log(computedStyle.fontSize);

// Working with CSS classes (preferred method)
element.classList.add("active");
element.classList.remove("inactive");
element.classList.toggle("highlight");
element.classList.replace("old-class", "new-class");

// Check if class exists
if (element.classList.contains("active")) {
    console.log("Element is active");
}

// Multiple class operations
element.className = "class1 class2 class3";  // Replace all classes
```
* 🔹 **Real-world Use Case**
  * Theme switching (dark/light mode)
  * Interactive animations and transitions
  * Form validation visual feedback
* 🔹 **Best Practice**
  * Use CSS classes instead of inline styles when possible

🟢 **JavaScript HTML DOM Animation**
* 🔹 **Explanation**
  * Create animations by changing element properties over time
  * Use timers, CSS transitions, or Web Animations API
* 🔹 **Code Example**
```js
let box = document.getElementById("animatedBox");

// Simple animation with setInterval
function slideRight() {
    let position = 0;
    let animation = setInterval(() => {
        position += 5;
        box.style.left = position + "px";
        
        if (position >= 200) {
            clearInterval(animation);
        }
    }, 20);
}

// Animation with CSS transitions (preferred)
function fadeOut() {
    box.style.transition = "opacity 1s ease-in-out";
    box.style.opacity = "0";
}

// Web Animations API (modern approach)
function bounceAnimation() {
    box.animate([
        { transform: "translateY(0px)" },
        { transform: "translateY(-50px)" },
        { transform: "translateY(0px)" }
    ], {
        duration: 1000,
        easing: "ease-in-out",
        iterations: 3
    });
}

// Request Animation Frame for smooth animations
function smoothMove() {
    let start = 0;
    let duration = 1000;
    let startTime = null;
    
    function animate(currentTime) {
        if (!startTime) startTime = currentTime;
        let progress = (currentTime - startTime) / duration;
        
        if (progress < 1) {
            box.style.left = (progress * 200) + "px";
            requestAnimationFrame(animate);
        }
    }
    
    requestAnimationFrame(animate);
}
```
* 🔹 **Real-world Use Case**
  * Loading spinners and progress bars
  * Smooth page transitions
  * Interactive hover effects
* 🔹 **Best Practice**
  * Use CSS transitions for simple animations, JavaScript for complex logic

🟢 **JavaScript HTML DOM Events**
* 🔹 **Explanation**
  * Handle various DOM events like clicks, mouse movements, keyboard input
  * Events bubble up through the DOM hierarchy
* 🔹 **Code Example**
```js
let button = document.getElementById("myButton");
let form = document.getElementById("myForm");

// Mouse events
button.addEventListener("click", function(e) {
    console.log("Button clicked");
});

button.addEventListener("mouseover", function(e) {
    this.style.backgroundColor = "lightblue";
});

button.addEventListener("mouseout", function(e) {
    this.style.backgroundColor = "";
});

// Keyboard events
document.addEventListener("keydown", function(e) {
    console.log("Key pressed:", e.key);
    if (e.key === "Enter") {
        console.log("Enter key pressed");
    }
});

// Form events
form.addEventListener("submit", function(e) {
    e.preventDefault(); // Prevent form submission
    console.log("Form submitted");
});

let input = document.getElementById("textInput");
input.addEventListener("input", function(e) {
    console.log("Input value:", e.target.value);
});

// Window events
window.addEventListener("load", function() {
    console.log("Page fully loaded");
});

window.addEventListener("resize", function() {
    console.log("Window resized to:", window.innerWidth, "x", window.innerHeight);
});
```
* 🔹 **Real-world Use Case**
  * Form validation and submission
  * Interactive user interfaces
  * Keyboard shortcuts and navigation
* 🔹 **Best Practice**
  * Use `preventDefault()` to control default browser behavior

🟢 **JavaScript HTML DOM EventListener**
* 🔹 **Explanation**
  * Modern way to handle events with more flexibility
  * Can add multiple listeners and control event behavior
* 🔹 **Code Example**
```js
let button = document.getElementById("eventButton");

// Adding event listeners
button.addEventListener("click", handleClick);
button.addEventListener("click", logClick);

function handleClick(event) {
    console.log("Handling click");
    event.preventDefault();
    event.stopPropagation(); // Stop event bubbling
}

function logClick(event) {
    console.log("Logging click at:", new Date());
}

// Removing event listeners
button.removeEventListener("click", handleClick);

// Event options
button.addEventListener("click", function(e) {
    console.log("This will only run once");
}, { once: true });

button.addEventListener("scroll", function(e) {
    console.log("Passive listener");
}, { passive: true });

// Event delegation (handling events on parent)
document.getElementById("container").addEventListener("click", function(e) {
    if (e.target.classList.contains("item")) {
        console.log("Item clicked:", e.target.textContent);
    }
});

// Custom events
let customEvent = new CustomEvent("myCustomEvent", {
    detail: { message: "Hello from custom event" }
});

button.addEventListener("myCustomEvent", function(e) {
    console.log(e.detail.message);
});

button.dispatchEvent(customEvent);
```
* 🔹 **Real-world Use Case**
  * Complex event handling with multiple functions
  * Event delegation for dynamic content
  * Custom events for component communication
* 🔹 **Best Practice**
  * Use event delegation for dynamically created elements

🟢 **JavaScript HTML DOM Navigation**
* 🔹 **Explanation**
  * Navigate through the DOM tree using element relationships
  * Move between parent, child, and sibling elements
* 🔹 **Code Example**
```js
let currentElement = document.getElementById("middle");

// Parent navigation
let parent = currentElement.parentElement;
let parentNode = currentElement.parentNode;

// Child navigation
let children = currentElement.children;           // HTMLCollection of elements
let childNodes = currentElement.childNodes;       // NodeList including text nodes
let firstChild = currentElement.firstElementChild;
let lastChild = currentElement.lastElementChild;

// Sibling navigation
let nextSibling = currentElement.nextElementSibling;
let previousSibling = currentElement.previousElementSibling;

// Practical navigation example
function highlightFamily(element) {
    // Highlight parent
    if (element.parentElement) {
        element.parentElement.style.border = "2px solid blue";
    }
    
    // Highlight children
    Array.from(element.children).forEach(child => {
        child.style.backgroundColor = "lightgreen";
    });
    
    // Highlight siblings
    let sibling = element.nextElementSibling;
    while (sibling) {
        sibling.style.color = "red";
        sibling = sibling.nextElementSibling;
    }
}

// Tree traversal
function walkDOM(node, callback) {
    callback(node);
    for (let child of node.children) {
        walkDOM(child, callback);
    }
}

// Usage
walkDOM(document.body, function(element) {
    console.log(element.tagName);
});
```
* 🔹 **Real-world Use Case**
  * Building tree views and navigation menus
  * Form validation that affects related fields
  * Creating DOM manipulation utilities
* 🔹 **Best Practice**
  * Use element-specific properties to avoid text nodes

### ✅ **DOM & Events Integration Tasks**
1. **Interactive Todo List**: Create a todo application with add/delete functionality, event delegation for dynamic items, and localStorage persistence.
2. **Form Validator**: Build a multi-step form with real-time validation, custom error messages, and smooth animations between steps.
3. **Image Gallery**: Create an interactive gallery with navigation, keyboard shortcuts, and smooth transitions using DOM manipulation and events.

---

## BROWSER & TIMING

🟢 **JavaScript Window - The Browser Object Model**
* 🔹 **Explanation**
  * The window object represents the browser window and global scope
  * Provides access to browser features and window properties
* 🔹 **Code Example**
```js
// Window properties
console.log(window.innerWidth);       // Viewport width
console.log(window.innerHeight);      // Viewport height
console.log(window.outerWidth);       // Browser window width
console.log(window.outerHeight);      // Browser window height

// Window methods
window.alert("Hello World");
let result = window.confirm("Are you sure?");
let input = window.prompt("Enter your name:");

// Opening new windows
let newWindow = window.open("https://example.com", "_blank", "width=400,height=300");
if (newWindow) {
    newWindow.focus();
    // newWindow.close(); // Close the window
}

// Global scope
var globalVar = "I'm global";
console.log(window.globalVar);        // "I'm global"

// Window events
window.addEventListener("resize", function() {
    console.log("Window resized:", window.innerWidth, "x", window.innerHeight);
});

window.addEventListener("beforeunload", function(e) {
    e.returnValue = "Are you sure you want to leave?";
});
```
* 🔹 **Real-world Use Case**
  * Responsive design based on window size
  * Popup windows for authentication
  * Warning users before leaving unsaved changes
* 🔹 **Best Practice**
  * Avoid excessive use of global variables on window object

🟢 **JavaScript Window Screen**
* 🔹 **Explanation**
  * Screen object provides information about user's screen
  * Includes screen resolution, available space, and color depth
* 🔹 **Code Example**
```js
// Screen properties
console.log(screen.width);            // Total screen width
console.log(screen.height);           // Total screen height
console.log(screen.availWidth);       // Available screen width
console.log(screen.availHeight);      // Available screen height (minus taskbar)

console.log(screen.colorDepth);       // Color depth in bits
console.log(screen.pixelDepth);       // Pixel depth in bits

// Screen orientation (if supported)
if (screen.orientation) {
    console.log(screen.orientation.type);    // "landscape-primary", etc.
    console.log(screen.orientation.angle);   // Rotation angle
}

// Practical usage
function getScreenInfo() {
    return {
        resolution: `${screen.width}x${screen.height}`,
        available: `${screen.availWidth}x${screen.availHeight}`,
        colorDepth: screen.colorDepth,
        devicePixelRatio: window.devicePixelRatio || 1
    };
}

// Responsive behavior based on screen size
if (screen.width < 768) {
    document.body.classList.add("mobile-screen");
} else if (screen.width < 1024) {
    document.body.classList.add("tablet-screen");
} else {
    document.body.classList.add("desktop-screen");
}
```
* 🔹 **Real-world Use Case**
  * Responsive design decisions
  * Analytics and user experience tracking
  * Optimizing content for different screen sizes
* 🔹 **Best Practice**
  * Use viewport dimensions (`window.inner*`) for layout, screen for analytics

🟢 **JavaScript Window Location**
* 🔹 **Explanation**
  * Location object contains information about current URL
  * Provides methods to navigate and manipulate the URL
* 🔹 **Code Example**
```js
// Location properties
console.log(location.href);           // Full URL
console.log(location.protocol);       // "https:" or "http:"
console.log(location.host);           // "example.com:8080"
console.log(location.hostname);       // "example.com"
console.log(location.port);           // "8080"
console.log(location.pathname);       // "/path/to/page"
console.log(location.search);         // "?param=value"
console.log(location.hash);           // "#section"

// URL manipulation
function getUrlParams() {
    let params = new URLSearchParams(location.search);
    let result = {};
    for (let [key, value] of params) {
        result[key] = value;
    }
    return result;
}

// Navigation methods
location.assign("https://example.com");     // Navigate (adds to history)
location.replace("https://example.com");    // Navigate (replaces in history)
location.reload();                          // Refresh page
location.reload(true);                      // Force refresh from server

// Practical examples
function redirectToLogin() {
    location.href = "/login?redirect=" + encodeURIComponent(location.pathname);
}

function updateUrlWithoutReload(newPath) {
    history.pushState(null, "", newPath);
}
```
* 🔹 **Real-world Use Case**
  * Single-page application routing
  * Reading URL parameters
  * Redirecting users based on conditions
* 🔹 **Best Practice**
  * Use `history.pushState()` for URL changes without page reload

🟢 **JavaScript Window History**
* 🔹 **Explanation**
  * History object manages browser's session history
  * Allows navigation through history and URL manipulation
* 🔹 **Code Example**
```js
// History navigation
history.back();                        // Go back one page
history.forward();                     // Go forward one page
history.go(-2);                        // Go back 2 pages
history.go(1);                         // Go forward 1 page

// History properties
console.log(history.length);           // Number of entries in history

// Modern history API
// Add new history entry
history.pushState({page: 1}, "Page 1", "/page1");

// Replace current history entry
history.replaceState({page: 2}, "Page 2", "/page2");

// Listen for history changes
window.addEventListener("popstate", function(event) {
    console.log("History changed:", event.state);
    
    // Handle the state change
    if (event.state && event.state.page) {
        loadPage(event.state.page);
    }
});

// Single Page Application example
function navigateTo(path, data) {
    history.pushState(data, null, path);
    handleRoute(path, data);
}

function handleRoute(path, data) {
    // Update page content based on path
    switch(path) {
        case "/home":
            showHomePage();
            break;
        case "/about":
            showAboutPage();
            break;
        default:
            show404Page();
    }
}
```
* 🔹 **Real-world Use Case**
  * Single-page application navigation
  * Back button support in web apps
  * URL synchronization with app state
* 🔹 **Best Practice**
  * Always handle `popstate` events when using `pushState()`

🟢 **JavaScript Window Navigator**
* 🔹 **Explanation**
  * Navigator object provides information about the browser
  * Includes browser name, version, platform, and capabilities
* 🔹 **Code Example**
```js
// Browser information
console.log(navigator.userAgent);      // Full user agent string
console.log(navigator.appName);        // Browser name
console.log(navigator.appVersion);     // Browser version
console.log(navigator.platform);       // Operating system
console.log(navigator.language);       // Preferred language
console.log(navigator.languages);      // Array of languages

// Browser capabilities
console.log(navigator.cookieEnabled);  // true/false
console.log(navigator.onLine);         // Online status
console.log(navigator.javaEnabled());  // Java support

// Modern APIs
if (navigator.geolocation) {
    navigator.geolocation.getCurrentPosition(
        function(position) {
            console.log("Latitude:", position.coords.latitude);
            console.log("Longitude:", position.coords.longitude);
        },
        function(error) {
            console.log("Geolocation error:", error.message);
        }
    );
}

// Service Worker support
if ('serviceWorker' in navigator) {
    navigator.serviceWorker.register('/sw.js');
}

// Clipboard API
if (navigator.clipboard) {
    navigator.clipboard.writeText("Hello World").then(() => {
        console.log("Text copied to clipboard");
    });
}

// Connection information
if (navigator.connection) {
    console.log("Connection type:", navigator.connection.effectiveType);
}
```
* 🔹 **Real-world Use Case**
  * Browser compatibility detection
  * Feature detection and progressive enhancement
  * User analytics and device information
* 🔹 **Best Practice**
  * Use feature detection instead of browser detection

🟢 **JavaScript Popup Boxes**
* 🔹 **Explanation**
  * Built-in dialog boxes for user interaction
  * Include alert, confirm, and prompt dialogs
* 🔹 **Code Example**
```js
// Alert box - display message
alert("Welcome to our website!");

// Confirm box - yes/no question
let userConfirmed = confirm("Do you want to delete this item?");
if (userConfirmed) {
    console.log("User confirmed");
    // Proceed with deletion
} else {
    console.log("User cancelled");
    // Cancel the operation
}

// Prompt box - get user input
let userName = prompt("Please enter your name:", "Default Name");
if (userName !== null && userName !== "") {
    console.log("Hello, " + userName);
} else {
    console.log("User cancelled or entered empty name");
}

// Advanced prompt with validation
function getValidEmail() {
    let email;
    do {
        email = prompt("Please enter a valid email address:");
        if (email === null) return null; // User cancelled
    } while (email && !email.includes("@"));
    
    return email;
}

// Modern alternatives (custom dialogs)
function showCustomAlert(message) {
    let modal = document.createElement("div");
    modal.innerHTML = `
        <div style="position: fixed; top: 50%; left: 50%; transform: translate(-50%, -50%); 
                    background: white; padding: 20px; border: 1px solid #ccc; z-index: 1000;">
            <p>${message}</p>
            <button onclick="this.parentElement.parentElement.remove()">OK</button>
        </div>
    `;
    document.body.appendChild(modal);
}
```
* 🔹 **Real-world Use Case**
  * Simple user confirmations
  * Quick user input collection
  * Development and debugging alerts
* 🔹 **Best Practice**
  * Use custom modals for better user experience in production apps

🟢 **JavaScript Timing Events**
* 🔹 **Explanation**
  * Execute code at specified time intervals
  * Include setTimeout for delays and setInterval for repeating actions
* 🔹 **Code Example**
```js
// setTimeout - execute once after delay
let timeoutId = setTimeout(function() {
    console.log("This runs after 2 seconds");
}, 2000);

// Clear timeout before it executes
clearTimeout(timeoutId);

// setInterval - execute repeatedly
let intervalId = setInterval(function() {
    console.log("This runs every 1 second");
}, 1000);

// Clear interval
setTimeout(() => {
    clearInterval(intervalId);
    console.log("Interval cleared after 5 seconds");
}, 5000);

// Practical examples
// Countdown timer
function startCountdown(seconds) {
    let remaining = seconds;
    let countdownDisplay = document.getElementById("countdown");
    
    let timer = setInterval(() => {
        countdownDisplay.textContent = remaining;
        remaining--;
        
        if (remaining < 0) {
            clearInterval(timer);
            countdownDisplay.textContent = "Time's up!";
        }
    }, 1000);
    
    return timer;
}

// Debounce function for search input
function debounce(func, delay) {
    let timeoutId;
    return function(...args) {
        clearTimeout(timeoutId);
        timeoutId = setTimeout(() => func.apply(this, args), delay);
    };
}

// Usage
let searchInput = document.getElementById("search");
let debouncedSearch = debounce(function(query) {
    console.log("Searching for:", query);
    // Perform search
}, 300);

searchInput.addEventListener("input", function() {
    debouncedSearch(this.value);
});

// Auto-save functionality
let autoSaveTimer;
function scheduleAutoSave() {
    clearTimeout(autoSaveTimer);
    autoSaveTimer = setTimeout(saveData, 5000); // Save after 5 seconds of inactivity
}

function saveData() {
    console.log("Auto-saving data...");
    // Save logic here
}
```
* 🔹 **Real-world Use Case**
  * Auto-save functionality
  * Debouncing user input
  * Countdown timers and notifications
* 🔹 **Best Practice**
  * Always clear timers when no longer needed to prevent memory leaks

🟢 **JavaScript Cookies**
* 🔹 **Explanation**
  * Small data stored in the browser for websites
  * Used for user preferences, session management, and tracking
* 🔹 **Code Example**
```js
// Setting cookies
document.cookie = "username=john";
document.cookie = "theme=dark; expires=Thu, 18 Dec 2024 12:00:00 GMT";
document.cookie = "sessionId=abc123; path=/; secure; httpOnly";

// Cookie utility functions
function setCookie(name, value, days) {
    let expires = "";
    if (days) {
        let date = new Date();
        date.setTime(date.getTime() + (days * 24 * 60 * 60 * 1000));
        expires = "; expires=" + date.toUTCString();
    }
    document.cookie = name + "=" + value + expires + "; path=/";
}

function getCookie(name) {
    let nameEQ = name + "=";
    let cookies = document.cookie.split(';');
    
    for (let cookie of cookies) {
        cookie = cookie.trim();
        if (cookie.indexOf(nameEQ) === 0) {
            return cookie.substring(nameEQ.length);
        }
    }
    return null;
}

function deleteCookie(name) {
    document.cookie = name + "=; expires=Thu, 01 Jan 1970 00:00:00 GMT; path=/";
}

// Practical usage
function saveUserPreferences(theme, language) {
    setCookie("theme", theme, 30);      // Save for 30 days
    setCookie("language", language, 30);
}

function loadUserPreferences() {
    let theme = getCookie("theme") || "light";
    let language = getCookie("language") || "en";
    
    applyTheme(theme);
    setLanguage(language);
}

// Cookie consent banner
function showCookieConsent() {
    if (!getCookie("cookieConsent")) {
        let banner = document.createElement("div");
        banner.innerHTML = `
            <div style="position: fixed; bottom: 0; width: 100%; background: #333; color: white; padding: 10px;">
                This site uses cookies. 
                <button onclick="acceptCookies()">Accept</button>
                <button onclick="this.parentElement.remove()">Dismiss</button>
            </div>
        `;
        document.body.appendChild(banner);
    }
}

function acceptCookies() {
    setCookie("cookieConsent", "true", 365);
    document.querySelector("[style*='position: fixed']").remove();
}

// Modern alternative: localStorage (not sent to server)
localStorage.setItem("userPreference", "darkMode");
let preference = localStorage.getItem("userPreference");
localStorage.removeItem("userPreference");
```
* 🔹 **Real-world Use Case**
  * User authentication sessions
  * Shopping cart persistence
  * User preferences and settings
* 🔹 **Best Practice**
  * Use localStorage for client-side data, cookies for server communication

### ✅ **Browser & Timing Integration Tasks**
1. **User Session Manager**: Create a system that tracks user activity, uses timing events for auto-logout warnings, and manages session cookies.
2. **Responsive Dashboard**: Build a dashboard that adapts to screen size, saves user preferences in cookies, and updates URL state without page reloads.
3. **Browser Compatibility Checker**: Create a tool that detects browser capabilities, displays appropriate messages, and provides fallbacks for unsupported features.

---

## ADVANCED DATA & ERROR HANDLING

🟢 **JavaScript Math Object**
* 🔹 **Explanation**
  * Built-in object with mathematical constants and functions
  * Provides methods for calculations, rounding, and trigonometry
* 🔹 **Code Example**
```js
// Math constants
console.log(Math.PI);          // 3.14159...
console.log(Math.E);           // 2.718...
console.log(Math.LN2);         // Natural log of 2
console.log(Math.SQRT2);       // Square root of 2

// Basic math methods
console.log(Math.abs(-5));     // 5 (absolute value)
console.log(Math.ceil(4.3));   // 5 (round up)
console.log(Math.floor(4.9));  // 4 (round down)
console.log(Math.round(4.6));  // 5 (round to nearest)
console.log(Math.trunc(4.9));  // 4 (remove decimal part)

// Min/Max
console.log(Math.min(2, 5, 1, 9));        // 1
console.log(Math.max(2, 5, 1, 9));        // 9
console.log(Math.min(...[2, 5, 1, 9]));   // Using spread operator

// Power and roots
console.log(Math.pow(2, 3));   // 8 (2^3)
console.log(Math.sqrt(16));    // 4 (square root)
console.log(Math.cbrt(27));    // 3 (cube root)

// Trigonometry (angles in radians)
console.log(Math.sin(Math.PI / 2));  // 1
console.log(Math.cos(0));            // 1
console.log(Math.tan(Math.PI / 4));  // 1

// Practical utility functions
function roundToDecimal(number, decimals) {
    return Math.round(number * Math.pow(10, decimals)) / Math.pow(10, decimals);
}

function clamp(value, min, max) {
    return Math.min(Math.max(value, min), max);
}

function lerp(start, end, factor) {
    return start + (end - start) * factor;
}
```
* 🔹 **Real-world Use Case**
  * Financial calculations and currency formatting
  * Game development physics and animations
  * Data visualization and chart calculations
* 🔹 **Best Practice**
  * Use `Math.round()` for display, but store precise values for calculations

🟢 **JavaScript Random**
* 🔹 **Explanation**
  * Generate random numbers for various applications
  * Math.random() returns decimal between 0 (inclusive) and 1 (exclusive)
* 🔹 **Code Example**
```js
// Basic random number (0 to 1)
console.log(Math.random());        // 0.something

// Random integer between min and max (inclusive)
function randomInt(min, max) {
    return Math.floor(Math.random() * (max - min + 1)) + min;
}

console.log(randomInt(1, 6));      // Dice roll (1-6)
console.log(randomInt(10, 20));    // Random number 10-20

// Random float between min and max
function randomFloat(min, max) {
    return Math.random() * (max - min) + min;
}

// Random array element
function randomChoice(array) {
    return array[Math.floor(Math.random() * array.length)];
}

let colors = ["red", "blue", "green", "yellow"];
console.log(randomChoice(colors));

// Shuffle array (Fisher-Yates algorithm)
function shuffleArray(array) {
    let shuffled = [...array];
    for (let i = shuffled.length - 1; i > 0; i--) {
        let j = Math.floor(Math.random() * (i + 1));
        [shuffled[i], shuffled[j]] = [shuffled[j], shuffled[i]];
    }
    return shuffled;
}

// Random string generator
function randomString(length) {
    let chars = 'ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789';
    let result = '';
    for (let i = 0; i < length; i++) {
        result += chars.charAt(Math.floor(Math.random() * chars.length));
    }
    return result;
}

// Random boolean with probability
function randomBoolean(probability = 0.5) {
    return Math.random() < probability;
}

// Random color generator
function randomColor() {
    return `#${Math.floor(Math.random() * 16777215).toString(16).padStart(6, '0')}`;
}

console.log(randomColor());        // #a3c5f7 (example)
```
* 🔹 **Real-world Use Case**
  * Games (dice rolls, card shuffling, random events)
  * UI elements (random colors, animations)
  * Testing with random data generation
* 🔹 **Best Practice**
  * Use crypto.getRandomValues() for cryptographically secure random numbers

🟢 **JavaScript Bitwise Operations**
* 🔹 **Explanation**
  * Operations that work directly on binary representations of numbers
  * Include AND, OR, XOR, NOT, and bit shifting operations
* 🔹 **Code Example**
```js
// Bitwise operators
let a = 5;  // 101 in binary
let b = 3;  // 011 in binary

console.log(a & b);    // 1 (AND: 101 & 011 = 001)
console.log(a | b);    // 7 (OR: 101 | 011 = 111)
console.log(a ^ b);    // 6 (XOR: 101 ^ 011 = 110)
console.log(~a);       // -6 (NOT: ~101 = ...11111010)

// Bit shifting
console.log(a << 1);   // 10 (left shift: 101 << 1 = 1010)
console.log(a >> 1);   // 2 (right shift: 101 >> 1 = 10)
console.log(-5 >>> 1); // Large positive number (unsigned right shift)

// Practical applications
// Check if number is even (faster than % 2)
function isEven(num) {
    return (num & 1) === 0;
}

// Toggle boolean using XOR
let flag = true;
flag = flag ^ true;    // false
flag = flag ^ true;    // true

// Set, clear, and check specific bits
function setBit(num, position) {
    return num | (1 << position);
}

function clearBit(num, position) {
    return num & ~(1 << position);
}

function checkBit(num, position) {
    return (num & (1 << position)) !== 0;
}

// RGB color manipulation
function createRGB(r, g, b) {
    return (r << 16) | (g << 8) | b;
}

function extractRGB(color) {
    return {
        r: (color >> 16) & 0xFF,
        g: (color >> 8) & 0xFF,
        b: color & 0xFF
    };
}

// Fast multiplication/division by powers of 2
let num = 16;
console.log(num << 2);  // 64 (multiply by 4)
console.log(num >> 2);  // 4 (divide by 4)

// Swap variables without temporary variable
let x = 10, y = 20;
x = x ^ y;
y = x ^ y;
x = x ^ y;
console.log(x, y);      // 20, 10
```
* 🔹 **Real-world Use Case**
  * Performance-critical applications
  * Working with binary data and flags
  * Graphics and color manipulation
* 🔹 **Best Practice**
  * Use sparingly and document well - prioritize readability over micro-optimizations

🟢 **JavaScript Errors**
* 🔹 **Explanation**
  * Handle runtime errors gracefully using try-catch blocks
  * Create custom errors and implement proper error handling strategies
* 🔹 **Code Example**
```js
// Basic try-catch
try {
    let result = riskyOperation();
    console.log(result);
} catch (error) {
    console.error("An error occurred:", error.message);
} finally {
    console.log("This always runs");
}

// Specific error types
try {
    JSON.parse("invalid json");
} catch (error) {
    if (error instanceof SyntaxError) {
        console.log("JSON syntax error");
    } else if (error instanceof ReferenceError) {
        console.log("Reference error");
    } else {
        console.log("Unknown error:", error);
    }
}

// Throwing custom errors
function divide(a, b) {
    if (b === 0) {
        throw new Error("Division by zero is not allowed");
    }
    return a / b;
}

function validateEmail(email) {
    if (!email.includes("@")) {
        throw new Error("Invalid email format");
    }
    return email;
}

// Custom error classes
class ValidationError extends Error {
    constructor(message, field) {
        super(message);
        this.name = "ValidationError";
        this.field = field;
    }
}

class NetworkError extends Error {
    constructor(message, statusCode) {
        super(message);
        this.name = "NetworkError";
        this.statusCode = statusCode;
    }
}

// Async error handling
async function fetchUserData(userId) {
    try {
        let response = await fetch(`/api/users/${userId}`);
        if (!response.ok) {
            throw new NetworkError("Failed to fetch user", response.status);
        }
        return await response.json();
    } catch (error) {
        if (error instanceof NetworkError) {
            console.log(`Network error (${error.statusCode}):`, error.message);
        } else {
            console.log("Unexpected error:", error);
        }
        throw error; // Re-throw for caller to handle
    }
}

// Error handling utility
function safeExecute(fn, fallback = null) {
    try {
        return fn();
    } catch (error) {
        console.error("Safe execution failed:", error);
        return fallback;
    }
}

// Global error handler
window.addEventListener("error", function(event) {
    console.error("Global error:", event.error);
    // Log to error reporting service
});

window.addEventListener("unhandledrejection", function(event) {
    console.error("Unhandled promise rejection:", event.reason);
    event.preventDefault(); // Prevent default browser behavior
});
```
* 🔹 **Real-world Use Case**
  * API error handling and user feedback
  * Form validation with specific error messages
  * Graceful degradation when features fail
* 🔹 **Best Practice**
  * Always handle errors gracefully, provide meaningful error messages to users

🟢 **JavaScript Date Objects**
* 🔹 **Explanation**
  * Work with dates and times in JavaScript
  * Create, manipulate, and format date objects
* 🔹 **Code Example**
```js
// Creating dates
let now = new Date();                           // Current date/time
let specificDate = new Date(2024, 0, 15);       // Jan 15, 2024 (month is 0-indexed)
let fromString = new Date("2024-01-15T10:30:00"); // ISO string
let fromTimestamp = new Date(1642248600000);     // Unix timestamp

// Date methods
console.log(now.getFullYear());     // 2024
console.log(now.getMonth());        // 0-11 (January = 0)
console.log(now.getDate());         // 1-31 (day of month)
console.log(now.getDay());          // 0-6 (Sunday = 0)
console.log(now.getHours());        // 0-23
console.log(now.getMinutes());      // 0-59
console.log(now.getSeconds());      // 0-59
console.log(now.getTime());         // Milliseconds since epoch

// Date calculations
let tomorrow = new Date();
tomorrow.setDate(tomorrow.getDate() + 1);

let nextWeek = new Date();
nextWeek.setDate(nextWeek.getDate() + 7);

let nextMonth = new Date();
nextMonth.setMonth(nextMonth.getMonth() + 1);

// Utility functions
function formatDate(date) {
    return `${date.getMonth() + 1}/${date.getDate()}/${date.getFullYear()}`;
}

function getDaysBetween(date1, date2) {
    let diffTime = Math.abs(date2 - date1);
    return Math.ceil(diffTime / (1000 * 60 * 60 * 24));
}

function isWeekend(date) {
    let day = date.getDay();
    return day === 0 || day === 6; // Sunday or Saturday
}

function addBusinessDays(date, days) {
    let result = new Date(date);
    let addedDays = 0;
    
    while (addedDays < days) {
        result.setDate(result.getDate() + 1);
        if (!isWeekend(result)) {
            addedDays++;
        }
    }
    
    return result;
}

// Age calculation
function calculateAge(birthDate) {
    let today = new Date();
    let age = today.getFullYear() - birthDate.getFullYear();
    let monthDiff = today.getMonth() - birthDate.getMonth();
    
    if (monthDiff < 0 || (monthDiff === 0 && today.getDate() < birthDate.getDate())) {
        age--;
    }
    
    return age;
}
```
* 🔹 **Real-world Use Case**
  * Event scheduling and calendar applications
  * Age verification and birthday tracking
  * Time-based content filtering
* 🔹 **Best Practice**
  * Use ISO 8601 format for date strings, consider timezone issues

🟢 **JavaScript Date Formats**
* 🔹 **Explanation**
  * Different ways to display and parse dates
  * Include various format methods and internationalization
* 🔹 **Code Example**
```js
let date = new Date(2024, 0, 15, 14, 30, 45);

// Built-in formatting methods
console.log(date.toString());        // "Mon Jan 15 2024 14:30:45 GMT-0800 (PST)"
console.log(date.toDateString());    // "Mon Jan 15 2024"
console.log(date.toTimeString());    // "14:30:45 GMT-0800 (PST)"
console.log(date.toISOString());     // "2024-01-15T22:30:45.000Z"
console.log(date.toJSON());          // "2024-01-15T22:30:45.000Z"

// Locale-specific formatting
console.log(date.toLocaleDateString());              // "1/15/2024"
console.log(date.toLocaleDateString("en-GB"));       // "15/01/2024"
console.log(date.toLocaleDateString("de-DE"));       // "15.1.2024"

console.log(date.toLocaleTimeString());              // "2:30:45 PM"
console.log(date.toLocaleTimeString("en-GB"));       // "14:30:45"

// Advanced formatting with options
let options = {
    year: 'numeric',
    month: 'long',
    day: 'numeric',
    weekday: 'long'
};
console.log(date.toLocaleDateString("en-US", options)); // "Monday, January 15, 2024"

// Custom formatting function
function formatDate(date, format) {
    let year = date.getFullYear();
    let month = String(date.getMonth() + 1).padStart(2, '0');
    let day = String(date.getDate()).padStart(2, '0');
    let hours = String(date.getHours()).padStart(2, '0');
    let minutes = String(date.getMinutes()).padStart(2, '0');
    let seconds = String(date.getSeconds()).padStart(2, '0');
    
    return format
        .replace('YYYY', year)
        .replace('MM', month)
        .replace('DD', day)
        .replace('HH', hours)
        .replace('mm', minutes)
        .replace('ss', seconds);
}

console.log(formatDate(date, "YYYY-MM-DD HH:mm:ss")); // "2024-01-15 14:30:45"

// Relative time formatting
function getRelativeTime(date) {
    let now = new Date();
    let diffMs = now - date;
    let diffDays = Math.floor(diffMs / (1000 * 60 * 60 * 24));
    
    if (diffDays === 0) return "Today";
    if (diffDays === 1) return "Yesterday";
    if (diffDays < 7) return `${diffDays} days ago`;
    if (diffDays < 30) return `${Math.floor(diffDays / 7)} weeks ago`;
    if (diffDays < 365) return `${Math.floor(diffDays / 30)} months ago`;
    return `${Math.floor(diffDays / 365)} years ago`;
}

// Modern Intl.DateTimeFormat
let formatter = new Intl.DateTimeFormat('en-US', {
    year: 'numeric',
    month: 'short',
    day: 'numeric',
    hour: '2-digit',
    minute: '2-digit'
});
console.log(formatter.format(date)); // "Jan 15, 2024, 02:30 PM"
```
* 🔹 **Real-world Use Case**
  * User-friendly date displays
  * Internationalized applications
  * Social media timestamp formatting
* 🔹 **Best Practice**
  * Use `Intl.DateTimeFormat` for consistent internationalization

🟢 **JavaScript Get Date Methods**
* 🔹 **Explanation**
  * Methods to extract specific parts of a date object
  * Include methods for year, month, day, time components
* 🔹 **Code Example**
```js
let date = new Date(2024, 0, 15, 14, 30, 45, 123);

// Date component getters
console.log(date.getFullYear());     // 2024
console.log(date.getYear());         // 124 (deprecated, use getFullYear)
console.log(date.getMonth());        // 0 (January, 0-indexed)
console.log(date.getDate());         // 15 (day of month, 1-31)
console.log(date.getDay());          // 1 (Monday, 0=Sunday, 6=Saturday)

// Time component getters
console.log(date.getHours());        // 14 (0-23)
console.log(date.getMinutes());      // 30 (0-59)
console.log(date.getSeconds());      // 45 (0-59)
console.log(date.getMilliseconds()); // 123 (0-999)

// Timestamp methods
console.log(date.getTime());         // 1705342245123 (milliseconds since epoch)
console.log(Date.now());             // Current timestamp

// UTC methods (for GMT time)
console.log(date.getUTCFullYear());  // 2024
console.log(date.getUTCMonth());     // 0
console.log(date.getUTCDate());      // 15
console.log(date.getUTCHours());     // 22 (if local timezone is GMT-8)

// Timezone offset
console.log(date.getTimezoneOffset()); // Minutes difference from UTC

// Practical utility functions
function getQuarter(date) {
    return Math.floor(date.getMonth() / 3) + 1;
}

function getWeekNumber(date) {
    let startOfYear = new Date(date.getFullYear(), 0, 1);
    let days = Math.floor((date - startOfYear) / (24 * 60 * 60 * 1000));
    return Math.ceil((days + startOfYear.getDay() + 1) / 7);
}

function isDST(date) {
    let jan = new Date(date.getFullYear(), 0, 1).getTimezoneOffset();
    let jul = new Date(date.getFullYear(), 6, 1).getTimezoneOffset();
    return Math.max(jan, jul) !== date.getTimezoneOffset();
}

function getMonthName(date, locale = 'en-US') {
    return date.toLocaleDateString(locale, { month: 'long' });
}

function getDayName(date, locale = 'en-US') {
    return date.toLocaleDateString(locale, { weekday: 'long' });
}

// Date comparison utilities
function isSameDay(date1, date2) {
    return date1.toDateString() === date2.toDateString();
}

function isToday(date) {
    return isSameDay(date, new Date());
}

function isThisWeek(date) {
    let now = new Date();
    let weekStart = new Date(now.setDate(now.getDate() - now.getDay()));
    let weekEnd = new Date(now.setDate(now.getDate() - now.getDay() + 6));
    return date >= weekStart && date <= weekEnd;
}
```
* 🔹 **Real-world Use Case**
  * Building calendar components
  * Filtering data by date ranges
  * Creating time-based analytics
* 🔹 **Best Practice**
  * Remember that `getMonth()` is zero-indexed (January = 0)

🟢 **JavaScript Set Date Methods**
* 🔹 **Explanation**
  * Methods to modify date objects by setting specific components
  * Allow precise date manipulation and calculations
* 🔹 **Code Example**
```js
let date = new Date(2024, 0, 15, 14, 30, 45);

// Setting date components
date.setFullYear(2025);              // Change year to 2025
date.setMonth(11);                   // Change to December (11)
date.setDate(25);                    // Change to 25th day
console.log(date);                   // Dec 25, 2025

// Setting time components
date.setHours(18);                   // Set hour to 6 PM
date.setMinutes(45);                 // Set minutes to 45
date.setSeconds(30);                 // Set seconds to 30
date.setMilliseconds(500);           // Set milliseconds

// Setting multiple components at once
date.setFullYear(2024, 5, 20);       // June 20, 2024
date.setHours(9, 30, 0, 0);          // 9:30:00.000 AM

// Using setTime for timestamp
date.setTime(1642248600000);         // Set to specific timestamp

// UTC setters
date.setUTCFullYear(2024);
date.setUTCMonth(0);
date.setUTCDate(1);

// Practical date manipulation
function addDays(date, days) {
    let result = new Date(date);
    result.setDate(result.getDate() + days);
    return result;
}

function addMonths(date, months) {
    let result = new Date(date);
    result.setMonth(result.getMonth() + months);
    return result;
}

function setToStartOfDay(date) {
    let result = new Date(date);
    result.setHours(0, 0, 0, 0);
    return result;
}

function setToEndOfDay(date) {
    let result = new Date(date);
    result.setHours(23, 59, 59, 999);
    return result;
}

function getFirstDayOfMonth(date) {
    let result = new Date(date);
    result.setDate(1);
    return result;
}

function getLastDayOfMonth(date) {
    let result = new Date(date);
    result.setMonth(result.getMonth() + 1, 0);
    return result;
}

// Date range utilities
function createDateRange(start, end) {
    let dates = [];
    let current = new Date(start);
    
    while (current <= end) {
        dates.push(new Date(current));
        current.setDate(current.getDate() + 1);
    }
    
    return dates;
}

function getNthWeekday(year, month, weekday, n) {
    let date = new Date(year, month, 1);
    let firstWeekday = date.getDay();
    let daysToAdd = (weekday - firstWeekday + 7) % 7 + (n - 1) * 7;
    date.setDate(1 + daysToAdd);
    return date;
}

// Example: Get the 2nd Tuesday of March 2024
let secondTuesdayMarch = getNthWeekday(2024, 2, 2, 2);

// Automatic overflow handling
let date2 = new Date(2024, 0, 31);    // Jan 31, 2024
date2.setMonth(1);                    // Becomes Feb 29, 2024 (leap year)
date2.setMonth(1);                    // Still Feb 29
date2.setDate(date2.getDate() + 1);   // Becomes Mar 1, 2024
```
* 🔹 **Real-world Use Case**
  * Schedule and appointment systems
  * Date picker components
  * Recurring event calculations
* 🔹 **Best Practice**
  * JavaScript automatically handles date overflow (Jan 32 becomes Feb 1)

### ✅ **Advanced Data & Error Handling Integration Tasks**
1. **Math Utilities Library**: Create a comprehensive math utility with random number generators, statistical functions, and error handling for invalid inputs.
2. **Date Management System**: Build a date utility library with formatting, calculation methods, timezone handling, and proper error handling for invalid dates.
3. **Data Processor with Error Recovery**: Create a system that processes arrays of data, handles various error types gracefully, and provides detailed error reporting with recovery strategies.

---

## WORKING WITH JSON

🟢 **JavaScript JSON**
* 🔹 **Explanation**
  * JavaScript Object Notation - lightweight data interchange format
  * Text-based format that's easy for humans to read and write
* 🔹 **Code Example**
```js
// JSON is a string format
let jsonString = '{"name": "Alice", "age": 25, "city": "New York"}';

// Convert JSON string to JavaScript object
let user = JSON.parse(jsonString);
console.log(user.name);              // "Alice"

// Convert JavaScript object to JSON string
let person = {
    name: "Bob",
    age: 30,
    hobbies: ["reading", "gaming"],
    isActive: true
};
let jsonOutput = JSON.stringify(person);
console.log(jsonOutput);             // '{"name":"Bob","age":30,"hobbies":["reading","gaming"],"isActive":true}'

// Working with nested objects
let complexData = {
    users: [
        { id: 1, name: "Alice", profile: { email: "alice@email.com", verified: true } },
        { id: 2, name: "Bob", profile: { email: "bob@email.com", verified: false } }
    ],
    metadata: {
        total: 2,
        lastUpdated: "2024-01-15T10:30:00Z"
    }
};

// Common use cases
function saveToLocalStorage(key, data) {
    localStorage.setItem(key, JSON.stringify(data));
}

function loadFromLocalStorage(key) {
    let data = localStorage.getItem(key);
    return data ? JSON.parse(data) : null;
}

// API communication
async function fetchUserData(userId) {
    let response = await fetch(`/api/users/${userId}`);
    let userData = await response.json(); // Automatically parses JSON
    return userData;
}

async function sendUserData(userData) {
    let response = await fetch('/api/users', {
        method: 'POST',
        headers: { 'Content-Type': 'application/json' },
        body: JSON.stringify(userData)
    });
    return response.json();
}
```
* 🔹 **Real-world Use Case**
  * API communication between client and server
  * Local storage and data persistence
  * Configuration files and data exchange
* 🔹 **Best Practice**
  * Always handle JSON parsing errors with try-catch blocks

🟢 **JSON Syntax**
* 🔹 **Explanation**
  * Strict syntax rules for valid JSON format
  * Must use double quotes, no trailing commas, specific data types only
* 🔹 **Code Example**
```js
// Valid JSON syntax
let validJSON = `{
    "name": "Alice",
    "age": 25,
    "isStudent": true,
    "grades": [95, 87, 92],
    "address": {
        "street": "123 Main St",
        "city": "New York",
        "zipCode": "10001"
    },
    "phone": null
}`;

// Invalid JSON examples (will cause parsing errors)
/*
{
    name: "Alice",           // ❌ Keys must have double quotes
    age: 25,                 // ❌ Trailing comma not allowed
    'city': "New York",      // ❌ Single quotes not allowed
    comment: undefined,      // ❌ undefined not supported
    date: new Date(),        // ❌ Objects not supported
    func: function() {}      // ❌ Functions not supported
}
*/

// JSON validation function
function isValidJSON(str) {
    try {
        JSON.parse(str);
        return true;
    } catch (e) {
        return false;
    }
}

// Safe JSON parsing with error handling
function safeJSONParse(str, fallback = null) {
    try {
        return JSON.parse(str);
    } catch (error) {
        console.error("JSON Parse Error:", error.message);
        return fallback;
    }
}

// JSON formatting for readability
let data = { name: "Alice", age: 25, city: "New York" };
let prettyJSON = JSON.stringify(data, null, 2);
console.log(prettyJSON);
/*
{
  "name": "Alice",
  "age": 25,
  "city": "New York"
}
*/

// Minified JSON (no extra spaces)
let minifiedJSON = JSON.stringify(data);
console.log(minifiedJSON);           // {"name":"Alice","age":25,"city":"New York"}
```
* 🔹 **Real-world Use Case**
  * Data validation before API requests
  * Configuration file parsing
  * Error handling for malformed data
* 🔹 **Best Practice**
  * Always validate JSON syntax before parsing in production

🟢 **JSON Data Types**
* 🔹 **Explanation**
  * JSON supports only specific data types: string, number, boolean, null, object, array
  * JavaScript-specific types like undefined, functions, and dates are not supported
* 🔹 **Code Example**
```js
// Supported JSON data types
let jsonDataTypes = {
    "stringValue": "Hello World",        // string
    "numberInteger": 42,                 // number (integer)
    "numberFloat": 3.14159,             // number (float)
    "numberScientific": 2.5e6,          // number (scientific notation)
    "booleanTrue": true,                 // boolean
    "booleanFalse": false,              // boolean
    "nullValue": null,                   // null
    "arrayValue": [1, 2, 3, "four"],    // array
    "objectValue": {                     // object
        "nested": "property"
    }
};

// Unsupported types and workarounds
let jsObject = {
    date: new Date(),                    // ❌ Not supported
    func: function() { return "hello"; }, // ❌ Not supported
    undef: undefined,                    // ❌ Not supported
    symbol: Symbol("test"),              // ❌ Not supported
    bigint: 123n                         // ❌ Not supported
};

// Workarounds for unsupported types
let objectForJSON = {
    dateString: new Date().toISOString(),           // Convert date to string
    functionName: "greetUser",                      // Store function name
    hasValue: jsObject.undef !== undefined,        // Convert undefined to boolean
    symbolDescription: jsObject.symbol.toString(), // Convert symbol to string
    bigintString: jsObject.bigint.toString()       // Convert bigint to string
};

// Custom serialization for complex objects
function serializeForJSON(obj) {
    return JSON.stringify(obj, function(key, value) {
        if (value instanceof Date) {
            return { __type: 'Date', value: value.toISOString() };
        }
        if (typeof value === 'function') {
            return { __type: 'Function', value: value.toString() };
        }
        if (typeof value === 'undefined') {
            return { __type: 'Undefined' };
        }
        if (typeof value === 'symbol') {
            return { __type: 'Symbol', value: value.toString() };
        }
        if (typeof value === 'bigint') {
            return { __type: 'BigInt', value: value.toString() };
        }
        return value;
    });
}

// Custom deserialization
function deserializeFromJSON(jsonString) {
    return JSON.parse(jsonString, function(key, value) {
        if (value && typeof value === 'object' && value.__type) {
            switch (value.__type) {
                case 'Date':
                    return new Date(value.value);
                case 'Function':
                    return new Function('return ' + value.value)();
                case 'Undefined':
                    return undefined;
                case 'Symbol':
                    return Symbol(value.value.replace('Symbol(', '').replace(')', ''));
                case 'BigInt':
                    return BigInt(value.value);
                default:
                    return value;
            }
        }
        return value;
    });
}

// Example usage
let complexObject = {
    name: "John",
    birthDate: new Date('1990-01-01'),
    greet: function() { return "Hello!"; },
    data: undefined,
    id: Symbol('userId'),
    largeNumber: 9007199254740991n
};

// Serialize complex object
let serialized = serializeForJSON(complexObject);
console.log('Serialized:', serialized);

// Deserialize back to original types
let deserialized = deserializeFromJSON(serialized);
console.log('Deserialized:', deserialized);

// Validation helper
function isValidJSON(str) {
    try {
        JSON.parse(str);
        return true;
    } catch (e) {
        return false;
    }
}

// Type checking for JSON compatibility
function isJSONCompatible(value) {
    const type = typeof value;
    
    if (value === null) return true;
    if (type === 'string' || type === 'number' || type === 'boolean') return true;
    if (Array.isArray(value)) {
        return value.every(item => isJSONCompatible(item));
    }
    if (type === 'object') {
        return Object.values(value).every(val => isJSONCompatible(val));
    }
    
    return false; // undefined, function, symbol, bigint not compatible
}

// Safe JSON stringify with error handling
function safeJSONStringify(obj, indent = 2) {
    try {
        return JSON.stringify(obj, null, indent);
    } catch (error) {
        console.error('JSON stringify error:', error.message);
        return null;
    }
}

// Safe JSON parse with error handling
function safeJSONParse(jsonString) {
    try {
        return JSON.parse(jsonString);
    } catch (error) {
        console.error('JSON parse error:', error.message);
        return null;
    }
}
```

* 🔹 **Key Points**
  * Always validate JSON strings before parsing to prevent errors
  * Use custom serialization/deserialization for complex JavaScript objects
  * Consider type compatibility when designing APIs that exchange JSON data
  * JSON numbers have limitations compared to JavaScript numbers (no Infinity, NaN)
  * Trailing commas and comments are not allowed in valid JSON

🟢 **JSON Object Literals**
* 🔹 **Explanation**
  * Objects in JSON are represented as key-value pairs enclosed in curly braces
  * Keys must be strings in double quotes, values can be any valid JSON data type
* 🔹 **Code Example**
```js
// JSON object literal
let userJSON = `{
    "id": 123,
    "name": "Alice Johnson",
    "email": "alice@example.com",
    "profile": {
        "age": 28,
        "location": "San Francisco",
        "preferences": {
            "theme": "dark",
            "notifications": true
        }
    },
    "lastLogin": "2024-01-15T10:30:00Z"
}`;

let user = JSON.parse(userJSON);
console.log(user.profile.preferences.theme);  // "dark"

// Creating JSON object literals
let productData = {
    "productId": "ABC123",
    "name": "Wireless Headphones",
    "price": 199.99,
    "inStock": true,
    "categories": ["electronics", "audio"],
    "specifications": {
        "battery": "30 hours",
        "weight": "250g",
        "wireless": true
    }
};

let jsonString = JSON.stringify(productData, null, 2);
```
* 🔹 **Real-world Use Case**
  * User profile data storage
  * Product catalog information
  * API response structures
* 🔹 **Best Practice**
  * Use consistent naming conventions for object keys

🟢 **JSON Array Literals**
* 🔹 **Explanation**
  * Arrays in JSON are ordered lists of values enclosed in square brackets
  * Can contain any valid JSON data types including nested objects and arrays
* 🔹 **Code Example**
```js
// JSON array literal
let usersJSON = `[
    {
        "id": 1,
        "name": "Alice",
        "skills": ["JavaScript", "Python", "React"]
    },
    {
        "id": 2,
        "name": "Bob",
        "skills": ["Java", "Spring", "MySQL"]
    }
]`;

let users = JSON.parse(usersJSON);
console.log(users[0].skills[0]);  // "JavaScript"

// Mixed data types in arrays
let mixedArray = [
    "string value",
    42,
    true,
    null,
    {"nested": "object"},
    [1, 2, 3]
];

// Array of objects (common pattern)
let todoList = [
    {
        "id": 1,
        "task": "Complete project",
        "completed": false,
        "priority": "high",
        "dueDate": "2024-01-20"
    },
    {
        "id": 2,
        "task": "Review code",
        "completed": true,
        "priority": "medium",
        "dueDate": "2024-01-18"
    }
];

// Processing JSON arrays
function filterCompletedTasks(tasks) {
    return tasks.filter(task => task.completed);
}

function getHighPriorityTasks(tasks) {
    return tasks.filter(task => task.priority === "high");
}
```
* 🔹 **Real-world Use Case**
  * Todo lists and task management
  * Shopping cart items
  * API response collections
* 🔹 **Best Practice**
  * Use arrays for ordered collections, objects for key-value relationships

🟢 **JSON.parse()**
* 🔹 **Explanation**
  * Converts JSON string into JavaScript object or array
  * Can accept optional reviver function for custom parsing logic
* 🔹 **Code Example**
```js
// Basic parsing
let jsonString = '{"name": "Alice", "age": 25, "city": "New York"}';
let user = JSON.parse(jsonString);
console.log(user.name);  // "Alice"

// Parsing with error handling
function safeJSONParse(str, fallback = null) {
    try {
        return JSON.parse(str);
    } catch (error) {
        console.error("JSON parsing failed:", error.message);
        return fallback;
    }
}

// Using reviver function for custom parsing
let dateJSON = '{"name": "Alice", "birthDate": "1999-05-15T00:00:00Z", "age": 25}';
let userWithDate = JSON.parse(dateJSON, function(key, value) {
    // Convert date strings back to Date objects
    if (key === "birthDate") {
        return new Date(value);
    }
    return value;
});

console.log(userWithDate.birthDate instanceof Date);  // true

// Advanced reviver for type restoration
function parseWithTypes(jsonStr) {
    return JSON.parse(jsonStr, function(key, value) {
        if (value && typeof value === 'object' && value.__type) {
            switch(value.__type) {
                case 'Date':
                    return new Date(value.value);
                case 'RegExp':
                    return new RegExp(value.source, value.flags);
                case 'Set':
                    return new Set(value.values);
                default:
                    return value;
            }
        }
        return value;
    });
}

// Parsing arrays
let numbersJSON = '[1, 2, 3, 4, 5]';
let numbers = JSON.parse(numbersJSON);
console.log(Array.isArray(numbers));  // true
```
* 🔹 **Real-world Use Case**
  * API response processing
  * localStorage data retrieval
  * Configuration file loading
* 🔹 **Shorthand**
  * `response.json()` in fetch API automatically parses JSON
* 🔹 **Best Practice**
  * Always wrap JSON.parse() in try-catch for error handling

🟢 **JSON.stringify()**
* 🔹 **Explanation**
  * Converts JavaScript object or array into JSON string
  * Accepts optional replacer function and space parameter for formatting
* 🔹 **Code Example**
```js
// Basic stringification
let user = {
    name: "Alice",
    age: 25,
    hobbies: ["reading", "gaming"],
    isActive: true
};

let jsonString = JSON.stringify(user);
console.log(jsonString);  // {"name":"Alice","age":25,"hobbies":["reading","gaming"],"isActive":true}

// Pretty printing with indentation
let prettyJSON = JSON.stringify(user, null, 2);
console.log(prettyJSON);
/*
{
  "name": "Alice",
  "age": 25,
  "hobbies": [
    "reading",
    "gaming"
  ],
  "isActive": true
}
*/

// Using replacer function to filter properties
let sensitiveData = {
    username: "alice123",
    password: "secret123",
    email: "alice@example.com",
    lastLogin: new Date()
};

let publicJSON = JSON.stringify(sensitiveData, function(key, value) {
    // Exclude password from JSON
    if (key === "password") {
        return undefined;
    }
    // Convert dates to ISO strings
    if (value instanceof Date) {
        return value.toISOString();
    }
    return value;
});

// Using replacer array to include only specific properties
let limitedJSON = JSON.stringify(user, ["name", "age"]);
console.log(limitedJSON);  // {"name":"Alice","age":25}

// Custom toJSON method
class Person {
    constructor(name, age, ssn) {
        this.name = name;
        this.age = age;
        this.ssn = ssn;
    }
    
    toJSON() {
        // Only include name and age in JSON, exclude sensitive SSN
        return {
            name: this.name,
            age: this.age
        };
    }
}

let person = new Person("Bob", 30, "123-45-6789");
console.log(JSON.stringify(person));  // {"name":"Bob","age":30}
```
* 🔹 **Real-world Use Case**
  * API request body preparation
  * localStorage data storage
  * Deep cloning objects (limited)
* 🔹 **Shorthand**
  * Deep clone: `JSON.parse(JSON.stringify(obj))` (has limitations)
* 🔹 **Best Practice**
  * Use replacer function to handle sensitive data and custom types

🟢 **JSON HTML**
* 🔹 **Explanation**
  * Display JSON data in HTML format for better readability
  * Convert JSON strings to formatted HTML elements
* 🔹 **Code Example**
```js
// Convert JSON to HTML table
function jsonToTable(jsonData) {
    if (!Array.isArray(jsonData)) return "";
    
    let html = "<table border='1'><thead><tr>";
    
    // Create headers from first object keys
    let headers = Object.keys(jsonData[0] || {});
    headers.forEach(header => {
        html += `<th>${header}</th>`;
    });
    html += "</tr></thead><tbody>";
    
    // Create rows
    jsonData.forEach(item => {
        html += "<tr>";
        headers.forEach(header => {
            let value = item[header];
            if (typeof value === 'object') {
                value = JSON.stringify(value);
            }
            html += `<td>${value}</td>`;
        });
        html += "</tr>";
    });
    
    html += "</tbody></table>";
    return html;
}

// Convert JSON to formatted HTML
function jsonToHTML(obj, indent = 0) {
    let html = "";
    let spacing = "&nbsp;".repeat(indent * 4);
    
    if (Array.isArray(obj)) {
        html += "[<br>";
        obj.forEach((item, index) => {
            html += spacing + "&nbsp;&nbsp;&nbsp;&nbsp;";
            html += jsonToHTML(item, indent + 1);
            if (index < obj.length - 1) html += ",";
            html += "<br>";
        });
        html += spacing + "]";
    } else if (typeof obj === 'object' && obj !== null) {
        html += "{<br>";
        let keys = Object.keys(obj);
        keys.forEach((key, index) => {
            html += spacing + `&nbsp;&nbsp;&nbsp;&nbsp;"${key}": `;
            html += jsonToHTML(obj[key], indent + 1);
            if (index < keys.length - 1) html += ",";
            html += "<br>";
        });
        html += spacing + "}";
    } else if (typeof obj === 'string') {
        html += `"${obj}"`;
    } else {
        html += String(obj);
    }
    
    return html;
}

// Display JSON data in webpage
function displayJSON(containerId, jsonData) {
    let container = document.getElementById(containerId);
    container.innerHTML = `<pre>${JSON.stringify(jsonData, null, 2)}</pre>`;
}

// Interactive JSON viewer
function createJSONViewer(jsonData) {
    let viewer = document.createElement('div');
    viewer.className = 'json-viewer';
    viewer.style.fontFamily = 'monospace';
    viewer.style.whiteSpace = 'pre-wrap';
    viewer.style.backgroundColor = '#f5f5f5';
    viewer.style.padding = '10px';
    viewer.style.border = '1px solid #ddd';
    viewer.textContent = JSON.stringify(jsonData, null, 2);
    return viewer;
}

// Syntax highlighting for JSON (basic)
function highlightJSON(json) {
    return json
        .replace(/("[\w]+"):/g, '<span style="color: blue;">$1</span>:')
        .replace(/(:\s*"[^"]*")/g, ':<span style="color: green;">$1</span>')
        .replace(/(:\s*\d+)/g, ':<span style="color: red;">$1</span>')
        .replace(/(:\s*(true|false|null))/g, ':<span style="color: purple;">$1</span>');
}
```
* 🔹 **Real-world Use Case**
  * Admin dashboards displaying API data
  * Debug tools and data visualization
  * Configuration editors
* 🔹 **Best Practice**
  * Use CSS for styling JSON displays, escape HTML characters in JSON values
---

## FINAL WORKSHOP SUMMARY

### 🎯 **Key Learning Objectives Achieved**
- **Beginner Fundamentals**: Variables, data types, operators, and basic JavaScript syntax
- **Control Flow**: Conditional statements, loops, and program flow control
- **Functions & Scope**: Function creation, invocation, and understanding JavaScript scope
- **Data Manipulation**: Working with strings, numbers, arrays, and objects
- **DOM Interaction**: Manipulating web pages and handling user events
- **Browser APIs**: Working with browser features, timing, and storage
- **Error Handling**: Managing errors and working with advanced data types
- **JSON Processing**: Data exchange and API communication

### 🚀 **Next Steps for Continued Learning**
1. **ES6+ Features**: Arrow functions, destructuring, modules, async/await
2. **Framework Integration**: React, Vue, or Angular with JavaScript fundamentals
3. **Node.js**: Server-side JavaScript development
4. **Testing**: Unit testing with Jest or similar frameworks
5. **Build Tools**: Webpack, Vite, and modern development workflows

### 💡 **Best Practices Recap**
- Always use `const` and `let` instead of `var`
- Handle errors gracefully with try-catch blocks
- Use descriptive variable and function names
- Prefer modern array methods over traditional loops
- Always validate and sanitize user input
- Use async/await for cleaner asynchronous code
- Comment complex logic and document functions
- Follow consistent code formatting and style guides
