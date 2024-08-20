# Lesson 11: Scope and Hoisting

Understanding scope and hoisting is crucial for writing effective JavaScript code. In this lesson, we will explore the concepts of local, global, and block scope, as well as what hoisting means and how it affects variable declarations.

## 1. Understanding Scope

Scope refers to the accessibility of variables and functions in different parts of your code. There are three main types of scope in JavaScript: global scope, local scope, and block scope.

### 1.1 Global Scope

A variable declared outside of any function or block has global scope. This means it is accessible from anywhere in your code, including inside functions.

**Example:**
```javascript
let globalVar = "I am a global variable";

function displayGlobalVar() {
    console.log(globalVar); // Accessible here
}

displayGlobalVar(); // Outputs: I am a global variable
console.log(globalVar); // Outputs: I am a global variable
```

### 1.2 Local Scope

A variable declared within a function has local scope. It is only accessible within that function and cannot be accessed from outside.

**Example:**
```javascript
function displayLocalVar() {
    let localVar = "I am a local variable";
    console.log(localVar); // Accessible here
}

displayLocalVar(); // Outputs: I am a local variable
console.log(localVar); // ReferenceError: localVar is not defined
```

### 1.3 Block Scope

Block scope is created by curly braces `{}` and is applicable to variables declared with `let` and `const`. Variables declared within a block are only accessible within that block.

**Example:**
```javascript
if (true) {
    let blockVar = "I am a block-scoped variable";
    console.log(blockVar); // Outputs: I am a block-scoped variable
}

console.log(blockVar); // ReferenceError: blockVar is not defined
```

### Summary of Scope
- **Global Scope**: Variables are accessible anywhere in the code.
- **Local Scope**: Variables are accessible only within the function where they are declared.
- **Block Scope**: Variables are accessible only within the block where they are declared (using `let` or `const`).

## 2. What Hoisting Means

Hoisting is a JavaScript mechanism where variable and function declarations are moved to the top of their containing scope during the compilation phase. This means that you can reference variables and functions before they are declared in the code.

### 2.1 Hoisting of Variables

Hoisting applies to variable declarations, but not to their initializations. Variables declared with `var` are hoisted to the top of their function scope, while `let` and `const` are hoisted to the top of their block scope but are not initialized.

**Example with `var`:**
```javascript
console.log(hoistedVar); // Outputs: undefined (declaration is hoisted)
var hoistedVar = "I am hoisted";
console.log(hoistedVar); // Outputs: I am hoisted
```

**Example with `let` and `const`:**
```javascript
console.log(hoistedLet); // ReferenceError: hoistedLet is not defined
let hoistedLet = "I am not hoisted";

console.log(hoistedConst); // ReferenceError: hoistedConst is not defined
const hoistedConst = "I am also not hoisted";
```

### 2.2 Hoisting of Functions

Function declarations are fully hoisted, meaning you can call them before they are defined in the code.

**Example:**
```javascript
greet(); // Outputs: Hello!

function greet() {
    console.log("Hello!");
}
```

However, function expressions (including arrow functions) are not hoisted in the same way as function declarations.

**Example of Function Expression:**
```javascript
sayHello(); // TypeError: sayHello is not a function

const sayHello = function() {
    console.log("Hello!");
};
```

## Conclusion

In this lesson, you learned about the different types of scope in JavaScript: global, local, and block scope. You also explored the concept of hoisting, which allows variable and function declarations to be accessed before they are defined in the code. Understanding scope and hoisting is essential for managing variable accessibility and avoiding common pitfalls in JavaScript. In the next lesson, we will dive into objects and arrays, which are key data structures in JavaScript!