# Lesson 4: Variables and Data Types

## Understanding `var`, `let`, and `const`

In JavaScript, variables are used to store data values. There are three ways to declare variables: using `var`, `let`, and `const`. Each has its own scope and usage, which is important to understand as you write your code.

### 1. `var`
- **Scope**: `var` is function-scoped, meaning it is accessible within the function it is declared in. If declared outside of a function, it becomes a global variable.
- **Hoisting**: Variables declared with `var` are hoisted to the top of their scope, which means they can be referenced before their declaration (though they will be `undefined` until the line of code is executed).

**Example:**
```javascript
function example() {
    console.log(x); // Outputs: undefined (due to hoisting)
    var x = 5;
    console.log(x); // Outputs: 5
}
example();
```

### 2. `let`
- **Scope**: `let` is block-scoped, meaning it is only accessible within the block (enclosed by `{}`) in which it is declared. This prevents issues with variable collisions in loops and conditional statements.
- **Hoisting**: Variables declared with `let` are also hoisted, but they cannot be accessed until the line of code where they are declared is reached (this is known as the "temporal dead zone").

**Example:**
```javascript
if (true) {
    let y = 10;
    console.log(y); // Outputs: 10
}
console.log(y); // ReferenceError: y is not defined
```

### 3. `const`
- **Scope**: `const` is also block-scoped, similar to `let`. However, it is used to declare variables that are constant and cannot be reassigned.
- **Hoisting**: Like `let`, `const` variables are hoisted but cannot be accessed before their declaration.

**Example:**
```javascript
const z = 15;
console.log(z); // Outputs: 15
z = 20; // TypeError: Assignment to constant variable.
```

## Overview of Primitive Types

JavaScript has several built-in data types, known as primitive types. These types represent single values and are immutable (cannot be changed). Here are the main primitive types:

### 1. Strings
- Strings are used to represent text and are enclosed in single quotes (`'`), double quotes (`"`), or backticks (`` ` ``).
  
**Example:**
```javascript
let greeting = "Hello, World!";
let name = 'Alice';
let message = `Welcome, ${name}!`; // Template literal
console.log(message); // Outputs: Welcome, Alice!
```

### 2. Numbers
- Numbers in JavaScript can be integers or floating-point numbers. JavaScript does not differentiate between different types of numbers.

**Example:**
```javascript
let age = 25; // Integer
let price = 19.99; // Floating-point
console.log(age + price); // Outputs: 44.99
```

### 3. Booleans
- Booleans represent a logical entity and can have two values: `true` or `false`. They are often used in conditional statements.

**Example:**
```javascript
let isStudent = true;
let isGraduated = false;
console.log(isStudent); // Outputs: true
```

### 4. Null
- `null` is a special value that represents the intentional absence of any object value. It is explicitly assigned to indicate "no value."

**Example:**
```javascript
let selectedOption = null;
console.log(selectedOption); // Outputs: null
```

### 5. Undefined
- `undefined` is a type that indicates a variable has been declared but has not yet been assigned a value. It is also the default value for uninitialized variables.

**Example:**
```javascript
let notAssigned;
console.log(notAssigned); // Outputs: undefined
```

## Conclusion

In this lesson, you learned how to declare variables using `var`, `let`, and `const`, and understood their differences in scope and hoisting behavior. You also explored the five main primitive data types in JavaScript: strings, numbers, booleans, null, and undefined. These concepts are fundamental to writing effective JavaScript code. In the next lesson, we will dive into objects and arrays, which are essential for organizing and managing data!