# Lesson 5: Objects and Arrays

## Creating and Accessing Objects and Arrays

In JavaScript, objects and arrays are fundamental data structures used to store and organize data. Understanding how to create and manipulate them is essential for effective programming.

### 1. Creating Objects

An object is a collection of key-value pairs, where each key is a string (or Symbol) and each value can be of any data type. You can create an object using either object literal notation or the `new Object()` constructor.

#### Object Literal Notation

**Example:**
```javascript
let person = {
    name: "Alice",
    age: 30,
    isStudent: false
};
```

#### Accessing Object Properties

You can access object properties using dot notation or bracket notation.

**Dot Notation:**
```javascript
console.log(person.name); // Outputs: Alice
console.log(person.age);  // Outputs: 30
```

**Bracket Notation:**
```javascript
console.log(person["isStudent"]); // Outputs: false
```

### 2. Creating Arrays

An array is an ordered list of values, which can be of any data type. You can create an array using array literal notation or the `new Array()` constructor.

#### Array Literal Notation

**Example:**
```javascript
let fruits = ["Apple", "Banana", "Cherry"];
```

#### Accessing Array Elements

You can access elements in an array using their index, starting from 0.

**Example:**
```javascript
console.log(fruits[0]); // Outputs: Apple
console.log(fruits[1]); // Outputs: Banana
```

## Understanding Properties, Methods, and Common Array Methods

### 1. Object Properties and Methods

- **Properties**: Properties are the key-value pairs in an object. You can add, modify, or delete properties.

**Example:**
```javascript
person.height = 170; // Adding a new property
console.log(person.height); // Outputs: 170

person.age = 31; // Modifying an existing property
console.log(person.age); // Outputs: 31

delete person.isStudent; // Deleting a property
console.log(person.isStudent); // Outputs: undefined
```

- **Methods**: Methods are functions that are associated with an object. They can perform actions using the object's properties.

**Example:**
```javascript
let car = {
    make: "Toyota",
    model: "Camry",
    year: 2020,
    getCarInfo: function() {
        return `${this.year} ${this.make} ${this.model}`;
    }
};

console.log(car.getCarInfo()); // Outputs: 2020 Toyota Camry
```

### 2. Common Array Methods

JavaScript provides several built-in methods to manipulate arrays. Here are some commonly used array methods:

- **`push()`**: Adds one or more elements to the end of an array and returns the new length of the array.

**Example:**
```javascript
fruits.push("Orange");
console.log(fruits); // Outputs: ["Apple", "Banana", "Cherry", "Orange"]
```

- **`pop()`**: Removes the last element from an array and returns that element.

**Example:**
```javascript
let lastFruit = fruits.pop();
console.log(lastFruit); // Outputs: Orange
console.log(fruits); // Outputs: ["Apple", "Banana", "Cherry"]
```

- **`shift()`**: Removes the first element from an array and returns that element.

**Example:**
```javascript
let firstFruit = fruits.shift();
console.log(firstFruit); // Outputs: Apple
console.log(fruits); // Outputs: ["Banana", "Cherry"]
```

- **`unshift()`**: Adds one or more elements to the beginning of an array and returns the new length of the array.

**Example:**
```javascript
fruits.unshift("Mango");
console.log(fruits); // Outputs: ["Mango", "Banana", "Cherry"]
```

- **`map()`**: Creates a new array populated with the results of calling a provided function on every element in the calling array.

**Example:**
```javascript
let lengths = fruits.map(fruit => fruit.length);
console.log(lengths); // Outputs: [5, 6, 6] (lengths of "Mango", "Banana", "Cherry")
```

- **`filter()`**: Creates a new array with all elements that pass the test implemented by the provided function.

**Example:**
```javascript
let longFruits = fruits.filter(fruit => fruit.length > 5);
console.log(longFruits); // Outputs: ["Banana", "Cherry"]
```

## Conclusion

In this lesson, you learned how to create and access objects and arrays in JavaScript. You also explored properties and methods of objects, as well as common array methods that allow you to manipulate and work with data effectively. Mastering these concepts is crucial for organizing and managing data in your applications. In the next lesson, we will dive into basic operators used in JavaScript!