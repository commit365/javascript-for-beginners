# Lesson 21: Destructuring Assignment

Destructuring assignment is a convenient way to extract values from arrays and properties from objects into distinct variables. This feature, introduced in ECMAScript 2015 (ES6), allows for cleaner and more readable code. In this lesson, we will explore how to destructure objects and arrays, as well as practical examples of destructuring in function parameters.

## 1. Destructuring Objects

Destructuring allows you to unpack properties from objects into variables. This can simplify your code and make it more readable.

### Syntax:
```javascript
const { property1, property2 } = object;
```

### Example of Object Destructuring:
```javascript
const person = {
    name: "Alice",
    age: 30,
    city: "New York"
};

// Destructuring the person object
const { name, age } = person;

console.log(name); // Outputs: Alice
console.log(age);  // Outputs: 30
```

### Explanation:
- In this example, the properties `name` and `age` are extracted from the `person` object and assigned to variables with the same names.

### Renaming Variables
You can also rename variables during destructuring using a colon (`:`).

**Example:**
```javascript
const { name: fullName, age: yearsOld } = person;

console.log(fullName); // Outputs: Alice
console.log(yearsOld); // Outputs: 30
```

## 2. Destructuring Arrays

Destructuring can also be applied to arrays, allowing you to extract elements based on their position.

### Syntax:
```javascript
const [element1, element2] = array;
```

### Example of Array Destructuring:
```javascript
const colors = ["red", "green", "blue"];

// Destructuring the colors array
const [firstColor, secondColor] = colors;

console.log(firstColor);  // Outputs: red
console.log(secondColor); // Outputs: green
```

### Explanation:
- In this example, the first and second elements of the `colors` array are extracted and assigned to `firstColor` and `secondColor`, respectively.

### Skipping Elements
You can skip elements in the array by leaving the corresponding variable empty.

**Example:**
```javascript
const numbers = [1, 2, 3, 4, 5];

// Skipping the first two elements
const [, , thirdNumber] = numbers;

console.log(thirdNumber); // Outputs: 3
```

## 3. Destructuring in Function Parameters

Destructuring can be particularly useful when working with function parameters. This allows you to extract values directly from the arguments passed to the function.

### Example of Destructuring in Function Parameters:
```javascript
const displayUserInfo = ({ name, age, city }) => {
    console.log(`Name: ${name}, Age: ${age}, City: ${city}`);
};

const user = {
    name: "Bob",
    age: 25,
    city: "Los Angeles"
};

// Calling the function with the user object
displayUserInfo(user); // Outputs: Name: Bob, Age: 25, City: Los Angeles
```

### Explanation:
- In this example, the `displayUserInfo` function takes an object as an argument and destructures it directly in the parameter list, allowing for clean and concise access to the properties.

### Example with Array Destructuring in Function Parameters:
```javascript
const calculateSum = ([a, b]) => {
    return a + b;
};

const numbers = [10, 20];

// Calling the function with the numbers array
const sum = calculateSum(numbers);
console.log(sum); // Outputs: 30
```

### Explanation:
- Here, the `calculateSum` function takes an array as an argument and destructures it directly in the parameter list to access the elements.

## Conclusion

In this lesson, you learned about destructuring assignment in JavaScript, including how to destructure objects and arrays for cleaner, more readable code. You also explored practical examples of using destructuring in function parameters, which can simplify your function definitions and improve code clarity. Destructuring is a powerful feature that enhances the way you work with complex data structures in JavaScript. In the next lesson, we will explore more advanced JavaScript topics, including modules and how to structure your code for better maintainability!