# Lesson 6: Basic Operators

In this lesson, we will explore the fundamental operators in JavaScript that allow you to perform various operations on values. We will cover arithmetic, comparison, and logical operators, as well as understand operator precedence and type coercion.

## 1. Arithmetic Operators

Arithmetic operators are used to perform mathematical calculations. Here are the most common arithmetic operators in JavaScript:

| Operator | Description             | Example         | Result |
|----------|-------------------------|------------------|--------|
| `+`      | Addition                | `5 + 3`          | `8`    |
| `-`      | Subtraction             | `5 - 3`          | `2`    |
| `*`      | Multiplication          | `5 * 3`          | `15`   |
| `/`      | Division                | `5 / 3`          | `1.6667` |
| `%`      | Modulus (Remainder)     | `5 % 3`          | `2`    |
| `**`     | Exponentiation          | `2 ** 3`         | `8`    |

### Example:
```javascript
let a = 10;
let b = 5;

console.log(a + b); // Outputs: 15
console.log(a - b); // Outputs: 5
console.log(a * b); // Outputs: 50
console.log(a / b); // Outputs: 2
console.log(a % b); // Outputs: 0
console.log(2 ** 3); // Outputs: 8
```

## 2. Comparison Operators

Comparison operators are used to compare two values and return a Boolean result (`true` or `false`). Here are the most common comparison operators:

| Operator | Description                        | Example         | Result |
|----------|------------------------------------|------------------|--------|
| `==`     | Equal to (type coercion allowed)  | `5 == '5'`       | `true` |
| `===`    | Strict equal to (no type coercion)| `5 === '5'`     | `false`|
| `!=`     | Not equal to (type coercion allowed)| `5 != '5'`     | `false`|
| `!==`    | Strict not equal to (no type coercion)| `5 !== '5'` | `true` |
| `>`      | Greater than                       | `5 > 3`          | `true` |
| `<`      | Less than                          | `5 < 3`          | `false`|
| `>=`     | Greater than or equal to          | `5 >= 5`         | `true` |
| `<=`     | Less than or equal to             | `5 <= 3`         | `false`|

### Example:
```javascript
let x = 10;
let y = '10';

console.log(x == y);  // Outputs: true (type coercion)
console.log(x === y); // Outputs: false (strict comparison)
console.log(x != y);  // Outputs: false (type coercion)
console.log(x !== y); // Outputs: true (strict comparison)
console.log(x > 5);   // Outputs: true
console.log(x < 5);   // Outputs: false
```

## 3. Logical Operators

Logical operators are used to combine multiple Boolean expressions. Here are the most common logical operators:

| Operator | Description               | Example               | Result |
|----------|---------------------------|-----------------------|--------|
| `&&`     | Logical AND               | `true && false`       | `false`|
| `||`     | Logical OR                | `true || false`       | `true` |
| `!`      | Logical NOT               | `!true`                | `false`|

### Example:
```javascript
let a = true;
let b = false;

console.log(a && b); // Outputs: false
console.log(a || b); // Outputs: true
console.log(!a);     // Outputs: false
```

## 4. Understanding Operator Precedence

Operator precedence determines the order in which operators are evaluated in an expression. Operators with higher precedence are evaluated before operators with lower precedence. Here’s a simplified order of precedence (from highest to lowest):

1. Parentheses `()`
2. Exponentiation `**`
3. Multiplication `*`, Division `/`, Modulus `%`
4. Addition `+`, Subtraction `-`
5. Comparison operators `==`, `!=`, `===`, `!==`, `>`, `<`, `>=`, `<=`
6. Logical NOT `!`
7. Logical AND `&&`
8. Logical OR `||`

### Example:
```javascript
let result = 5 + 3 * 2; // Multiplication has higher precedence
console.log(result); // Outputs: 11

let result2 = (5 + 3) * 2; // Parentheses change the order
console.log(result2); // Outputs: 16
```

## 5. Type Coercion

Type coercion is the automatic or implicit conversion of values from one data type to another. JavaScript performs type coercion in certain situations, especially when using comparison operators.

### Example:
```javascript
console.log(5 + '5'); // Outputs: "55" (number is coerced to string)
console.log(5 - '2'); // Outputs: 3 (string is coerced to number)
console.log(true + 1); // Outputs: 2 (true is coerced to 1)
console.log(false + 1); // Outputs: 1 (false is coerced to 0)
```

### Important Note:
While type coercion can be convenient, it can also lead to unexpected results. It's generally a good practice to use strict equality (`===`) to avoid unintentional type coercion.

## Conclusion

In this lesson, you learned about basic operators in JavaScript, including arithmetic, comparison, and logical operators. You also explored operator precedence and type coercion, which are essential concepts for writing effective JavaScript code. Understanding these operators will help you perform calculations, make comparisons, and control the flow of your programs. In the next lesson, we will dive into control structures, including conditional statements and loops!