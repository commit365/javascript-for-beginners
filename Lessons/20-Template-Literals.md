# Lesson 20: Template Literals

Template literals are a powerful feature in JavaScript that allow for easier string manipulation and formatting. Introduced in ECMAScript 2015 (ES6), template literals provide a more flexible syntax for creating strings, enabling string interpolation, multi-line strings, and embedding expressions. In this lesson, we will explore how to use template literals effectively.

## 1. Using Template Literals for String Interpolation

Template literals are enclosed by backticks (`` ` ``) instead of single or double quotes. This allows you to embed variables and expressions directly within the string using the `${}` syntax.

### Syntax:
```javascript
let variable = "value";
let message = `This is a string with a variable: ${variable}`;
```

### Example of String Interpolation:
```javascript
let name = "Alice";
let age = 30;

let greeting = `Hello, my name is ${name} and I am ${age} years old.`;
console.log(greeting); // Outputs: Hello, my name is Alice and I am 30 years old.
```

### Explanation:
- In this example, the variables `name` and `age` are embedded directly within the string using `${}` syntax, making it easy to create dynamic strings.

## 2. Multi-line Strings

Template literals allow you to create multi-line strings without the need for concatenation or escape characters. You can simply press Enter to create a new line within the backticks.

### Example of Multi-line Strings:
```javascript
let multiLineString = `This is a string
that spans multiple
lines.`;
console.log(multiLineString);
```

**Output:**
```
This is a string
that spans multiple
lines.
```

### Explanation:
- In this example, the string is defined over multiple lines, and the line breaks are preserved in the output.

## 3. Embedding Expressions within Strings

You can embed not only variables but also any valid JavaScript expression within template literals. This includes arithmetic operations, function calls, and more.

### Example of Embedding Expressions:
```javascript
let a = 5;
let b = 10;

let result = `The sum of ${a} and ${b} is ${a + b}.`;
console.log(result); // Outputs: The sum of 5 and 10 is 15.
```

### Explanation:
- In this example, the expression `${a + b}` is evaluated, and its result is included in the string.

### Example with Function Calls:
```javascript
function getGreeting(name) {
    return `Hello, ${name}!`;
}

let greeting = getGreeting("Bob");
console.log(greeting); // Outputs: Hello, Bob!
```

### Explanation:
- Here, a function `getGreeting` returns a template literal that includes the `name` parameter, demonstrating how you can use template literals with function calls.

## Conclusion

In this lesson, you learned how to use template literals for string interpolation and creating multi-line strings in JavaScript. You also explored how to embed expressions within strings, making it easier to build dynamic and readable strings. Template literals enhance the flexibility and readability of your code, especially when working with complex strings. In the next lesson, we will explore more advanced JavaScript concepts, including modules and how to structure your code for better maintainability!

[Next: 21-Destructuring-Assignment](./21-Destructuring-Assignment.md)