# Lesson 17: Async/Await Syntax

Async/await is a modern syntax introduced in ECMAScript 2017 (ES8) that simplifies working with asynchronous code in JavaScript. It allows you to write asynchronous code that looks and behaves like synchronous code, making it easier to read and maintain. In this lesson, we will explore how to use async functions and the `await` keyword.

## 1. Introduction to Async Functions

An **async function** is a function that is declared with the `async` keyword. This keyword tells JavaScript that the function will contain asynchronous operations and will return a promise.

### Syntax:
```javascript
async function functionName() {
    // Asynchronous code
}
```

### Example of an Async Function:
```javascript
async function fetchData() {
    return "Data received!";
}

fetchData().then(data => {
    console.log(data); // Outputs: Data received!
});
```

In this example, `fetchData` is an async function that returns a string. When called, it returns a promise that resolves with the string.

## 2. The Await Keyword

The `await` keyword can only be used inside an async function. It pauses the execution of the async function and waits for the promise to resolve or reject. Once the promise is resolved, it returns the resolved value. If the promise is rejected, it throws an error.

### Syntax:
```javascript
let result = await promise;
```

### Example of Using Await:
```javascript
async function fetchData() {
    return new Promise((resolve) => {
        setTimeout(() => {
            resolve("Data received!");
        }, 2000);
    });
}

async function displayData() {
    const data = await fetchData(); // Wait for fetchData to resolve
    console.log(data); // Outputs: Data received!
}

displayData();
```

### Explanation:
- In this example, `fetchData` returns a promise that resolves after 2 seconds.
- The `displayData` function uses `await` to pause its execution until `fetchData` resolves, allowing it to log the received data.

## 3. Simplifying Asynchronous Code with Async/Await

Using async/await can make your asynchronous code cleaner and easier to follow, especially when dealing with multiple asynchronous operations.

### Example: Chaining Promises with Async/Await
Instead of chaining `.then()` calls, you can use async/await to handle multiple asynchronous operations sequentially.

```javascript
async function fetchData() {
    return new Promise((resolve) => {
        setTimeout(() => {
            resolve("Data received!");
        }, 2000);
    });
}

async function processData(data) {
    return new Promise((resolve) => {
        setTimeout(() => {
            resolve(data + " - Processed");
        }, 1000);
    });
}

async function displayData() {
    try {
        const data = await fetchData(); // Wait for fetchData to resolve
        console.log(data); // Outputs: Data received!

        const processedData = await processData(data); // Wait for processData to resolve
        console.log(processedData); // Outputs: Data received! - Processed
    } catch (error) {
        console.error("Error:", error); // Handle any errors
    }
}

displayData();
```

### Explanation:
- In this example, `displayData` uses `await` to wait for both `fetchData` and `processData` to complete.
- The `try...catch` block is used to handle any errors that may occur during the asynchronous operations, providing a clean way to manage errors.

## 4. Error Handling with Async/Await

You can handle errors in async functions using `try...catch` blocks, which is more intuitive than using `.catch()` with promises.

### Example of Error Handling:
```javascript
async function fetchData() {
    return new Promise((resolve, reject) => {
        setTimeout(() => {
            reject("Error: Data not found."); // Simulate an error
        }, 2000);
    });
}

async function displayData() {
    try {
        const data = await fetchData(); // Wait for fetchData to resolve
        console.log(data);
    } catch (error) {
        console.error(error); // Outputs: Error: Data not found.
    }
}

displayData();
```

### Explanation:
- In this example, `fetchData` simulates an error by rejecting the promise.
- The `displayData` function catches the error using a `try...catch` block, allowing you to handle it gracefully.

## Conclusion

In this lesson, you learned about async functions and the `await` keyword, which simplify working with asynchronous code in JavaScript. By using async/await, you can write cleaner and more readable code, making it easier to manage multiple asynchronous operations and handle errors. Understanding async/await is essential for building responsive web applications that rely on asynchronous data fetching and processing. In the next lesson, we will explore working with APIs and fetching data from external sources!