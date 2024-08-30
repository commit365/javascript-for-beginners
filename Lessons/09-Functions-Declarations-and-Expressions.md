# Lesson 9: Functions: Declarations and Expressions

Functions are fundamental building blocks in JavaScript that allow you to encapsulate reusable blocks of code. In this lesson, we will explore how to define functions, understand parameters and return values, and differentiate between function declarations and function expressions, including anonymous functions.

## 1. Defining Functions

### Function Declarations

A function declaration defines a named function that can be called later in the code. The syntax for declaring a function is as follows:

**Syntax:**
```javascript
function functionName(parameters) {
    // Code to execute
}
```

### Example:
```javascript
function greet(name) {
    console.log("Hello, " + name + "!");
}

// Calling the function
greet("Alice"); // Outputs: Hello, Alice!
```

### Parameters and Return Values

Functions can accept parameters (inputs) and return values (outputs). You can define parameters within the parentheses of the function declaration.

**Example:**
```javascript
function add(a, b) {
    return a + b; // Returns the sum of a and b
}

let result = add(5, 3);
console.log(result); // Outputs: 8
```

### Understanding Parameters
- **Parameters** are placeholders for the values you pass into the function when you call it. In the `add` function above, `a` and `b` are parameters.
- You can have multiple parameters, and they are separated by commas.

### Understanding Return Values
- The `return` statement is used to send a value back to the caller of the function. If no `return` statement is specified, the function returns `undefined` by default.

## 2. Function Expressions

A function expression defines a function that can be assigned to a variable. Unlike function declarations, function expressions can be anonymous (without a name).

### Syntax:
```javascript
const variableName = function(parameters) {
    // Code to execute
};
```

### Example: Function Expression
```javascript
const multiply = function(x, y) {
    return x * y; // Returns the product of x and y
};

let product = multiply(4, 5);
console.log(product); // Outputs: 20
```

### Anonymous Functions

An anonymous function is a function that does not have a name. It is often used in function expressions, callbacks, or immediately invoked function expressions (IIFE).

### Example: Anonymous Function in a Function Expression
```javascript
const divide = function(a, b) {
    return a / b; // Returns the quotient of a and b
};

let quotient = divide(10, 2);
console.log(quotient); // Outputs: 5
```

### Example: Using an Anonymous Function as a Callback
Anonymous functions are commonly used as callbacks in methods like `forEach`, `map`, and event listeners.

```javascript
let numbers = [1, 2, 3, 4, 5];

numbers.forEach(function(number) {
    console.log(number * 2); // Outputs: 2, 4, 6, 8, 10
});
```

## 3. Key Differences Between Function Declarations and Function Expressions

1. **Hoisting**:
   - Function declarations are hoisted, meaning you can call them before they are defined in the code.
   - Function expressions are not hoisted, so you must define them before calling them.

   **Example:**
   ```javascript
   greet("Bob"); // Works because greet is a function declaration

   function greet(name) {
       console.log("Hello, " + name + "!");
   }

   // multiply(2, 3); // Error: multiply is not defined

   const multiply = function(x, y) {
       return x * y;
   };
   ```

2. **Naming**:
   - Function declarations must have a name.
   - Function expressions can be anonymous or named.

## Conclusion

In this lesson, you learned how to define functions using function declarations and function expressions, as well as the concepts of parameters and return values. You also explored anonymous functions and their common usage in callbacks. Understanding functions is crucial for writing modular and reusable code in JavaScript. In the next lesson, we will dive into arrow functions, a more concise way to write functions in JavaScript!

[Next: 10-Arrow-Functions](./10-Arrow-Functions.md)