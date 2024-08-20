# Lesson 8: Loops

Loops are essential programming constructs that allow you to execute a block of code repeatedly based on a specified condition. In this lesson, we will explore three types of loops in JavaScript: `for`, `while`, and `do...while` loops. We will also look at practical examples of how to iterate through arrays and objects.

## 1. Understanding `for` Loops

The `for` loop is used when you know in advance how many times you want to execute a block of code. It consists of three parts: initialization, condition, and increment/decrement.

### Syntax:
```javascript
for (initialization; condition; increment) {
    // Code to execute on each iteration
}
```

### Example:
```javascript
for (let i = 0; i < 5; i++) {
    console.log("Iteration number: " + i);
}
```
**Output:**
```
Iteration number: 0
Iteration number: 1
Iteration number: 2
Iteration number: 3
Iteration number: 4
```

### Practical Example: Iterating Through an Array
```javascript
let fruits = ["Apple", "Banana", "Cherry"];

for (let i = 0; i < fruits.length; i++) {
    console.log("Fruit: " + fruits[i]);
}
```
**Output:**
```
Fruit: Apple
Fruit: Banana
Fruit: Cherry
```

## 2. Understanding `while` Loops

The `while` loop executes a block of code as long as a specified condition is `true`. It is useful when you do not know in advance how many times you need to iterate.

### Syntax:
```javascript
while (condition) {
    // Code to execute as long as condition is true
}
```

### Example:
```javascript
let count = 0;

while (count < 5) {
    console.log("Count is: " + count);
    count++;
}
```
**Output:**
```
Count is: 0
Count is: 1
Count is: 2
Count is: 3
Count is: 4
```

### Practical Example: Iterating Through an Array
```javascript
let colors = ["Red", "Green", "Blue"];
let index = 0;

while (index < colors.length) {
    console.log("Color: " + colors[index]);
    index++;
}
```
**Output:**
```
Color: Red
Color: Green
Color: Blue
```

## 3. Understanding `do...while` Loops

The `do...while` loop is similar to the `while` loop, but it guarantees that the block of code will execute at least once before the condition is tested.

### Syntax:
```javascript
do {
    // Code to execute
} while (condition);
```

### Example:
```javascript
let num = 0;

do {
    console.log("Number: " + num);
    num++;
} while (num < 5);
```
**Output:**
```
Number: 0
Number: 1
Number: 2
Number: 3
Number: 4
```

### Practical Example: Iterating Through an Object
You can use loops to iterate over the properties of an object using `for...in`.

```javascript
let person = {
    name: "Alice",
    age: 30,
    city: "New York"
};

for (let key in person) {
    console.log(key + ": " + person[key]);
}
```
**Output:**
```
name: Alice
age: 30
city: New York
```

## Conclusion

In this lesson, you learned about the three main types of loops in JavaScript: `for`, `while`, and `do...while`. You also saw practical examples of how to iterate through arrays and objects using these loops. Understanding loops is crucial for automating repetitive tasks and processing collections of data efficiently. In the next lesson, we will explore functions in JavaScript, which allow you to encapsulate reusable blocks of code!