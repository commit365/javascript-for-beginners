# Lesson 7: Conditional Statements

Conditional statements allow you to execute different blocks of code based on certain conditions. In this lesson, we will explore how to use `if`, `else if`, and `else` statements, as well as the `switch` statement for handling multiple conditions.

## 1. Using `if`, `else if`, and `else`

### The `if` Statement

The `if` statement evaluates a condition and executes a block of code if the condition is `true`.

**Syntax:**
```javascript
if (condition) {
    // Code to execute if the condition is true
}
```

### Example:
```javascript
let temperature = 30;

if (temperature > 25) {
    console.log("It's a hot day!");
}
```

### The `else` Statement

The `else` statement can be used to execute a block of code if the `if` condition is `false`.

**Syntax:**
```javascript
if (condition) {
    // Code to execute if the condition is true
} else {
    // Code to execute if the condition is false
}
```

### Example:
```javascript
let temperature = 20;

if (temperature > 25) {
    console.log("It's a hot day!");
} else {
    console.log("It's not a hot day.");
}
```

### The `else if` Statement

You can use `else if` to check multiple conditions. If the first condition is `false`, it checks the next condition, and so on.

**Syntax:**
```javascript
if (condition1) {
    // Code to execute if condition1 is true
} else if (condition2) {
    // Code to execute if condition2 is true
} else {
    // Code to execute if all conditions are false
}
```

### Example:
```javascript
let temperature = 15;

if (temperature > 25) {
    console.log("It's a hot day!");
} else if (temperature > 15) {
    console.log("It's a warm day.");
} else {
    console.log("It's a cold day.");
}
```

## 2. Introduction to the `switch` Statement

The `switch` statement is another way to handle multiple conditions. It evaluates an expression and executes the corresponding case block that matches the expression's value. If no cases match, it can execute a default block.

**Syntax:**
```javascript
switch (expression) {
    case value1:
        // Code to execute if expression === value1
        break;
    case value2:
        // Code to execute if expression === value2
        break;
    // Add more cases as needed
    default:
        // Code to execute if no cases match
}
```

### Example:
```javascript
let day = 3;
let dayName;

switch (day) {
    case 1:
        dayName = "Monday";
        break;
    case 2:
        dayName = "Tuesday";
        break;
    case 3:
        dayName = "Wednesday";
        break;
    case 4:
        dayName = "Thursday";
        break;
    case 5:
        dayName = "Friday";
        break;
    case 6:
        dayName = "Saturday";
        break;
    case 7:
        dayName = "Sunday";
        break;
    default:
        dayName = "Invalid day";
}

console.log(dayName); // Outputs: Wednesday
```

### Important Notes:
- **Break Statement**: The `break` statement is used to exit the `switch` block. If you omit it, the program will continue executing the next case(s) (this is known as "fall-through").
- **Default Case**: The `default` case is optional and will execute if none of the specified cases match. It’s similar to the `else` statement in an `if` structure.

## Conclusion

In this lesson, you learned how to use conditional statements in JavaScript, including `if`, `else if`, and `else` statements for branching logic. You also explored the `switch` statement for handling multiple conditions in a more organized way. Mastering these conditional statements is essential for controlling the flow of your programs based on different conditions. In the next lesson, we will dive into loops, which allow you to execute code repeatedly!