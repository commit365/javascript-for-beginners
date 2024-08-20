# Lesson 16: Using Promises

Promises are a powerful way to handle asynchronous operations in JavaScript. They provide a cleaner and more manageable approach compared to traditional callback functions, especially when dealing with multiple asynchronous tasks. In this lesson, we will learn how to create and use promises, chain them, and handle errors effectively.

## 1. Creating and Using Promises

A promise is an object that represents the eventual completion (or failure) of an asynchronous operation and its resulting value. A promise can be in one of three states:

- **Pending**: The initial state, neither fulfilled nor rejected.
- **Fulfilled**: The operation completed successfully.
- **Rejected**: The operation failed.

### Creating a Promise

You can create a promise using the `Promise` constructor, which takes a function (the executor) as an argument. This function receives two parameters: `resolve` and `reject`.

**Syntax:**
```javascript
const myPromise = new Promise((resolve, reject) => {
    // Asynchronous operation
});
```

### Example: Creating a Promise

```javascript
const fetchData = () => {
    return new Promise((resolve, reject) => {
        setTimeout(() => {
            const success = true; // Simulate success or failure
            if (success) {
                resolve("Data received!");
            } else {
                reject("Error: Data not found.");
            }
        }, 2000);
    });
};

// Using the promise
fetchData()
    .then((data) => {
        console.log(data); // Outputs: Data received!
    })
    .catch((error) => {
        console.error(error); // Outputs: Error: Data not found.
    });
```

### Explanation:
- In this example, `fetchData` returns a promise that simulates a data fetching operation using `setTimeout`.
- If the operation is successful, it calls `resolve()` with the data; if it fails, it calls `reject()` with an error message.

## 2. Chaining Promises

One of the powerful features of promises is that you can chain them together. This allows you to perform a series of asynchronous operations in a clean and readable manner.

### Example: Chaining Promises

```javascript
const fetchData = () => {
    return new Promise((resolve) => {
        setTimeout(() => {
            resolve("Data received!");
        }, 2000);
    });
};

const processData = (data) => {
    return new Promise((resolve) => {
        setTimeout(() => {
            resolve(data + " - Processed");
        }, 1000);
    });
};

// Chaining promises
fetchData()
    .then((data) => {
        console.log(data); // Outputs: Data received!
        return processData(data); // Return the next promise
    })
    .then((processedData) => {
        console.log(processedData); // Outputs: Data received! - Processed
    })
    .catch((error) => {
        console.error(error); // Handle any errors
    });
```

### Explanation:
- In this example, `fetchData` returns a promise that resolves with data after 2 seconds.
- The first `.then()` receives the data, logs it, and returns another promise from `processData`.
- The second `.then()` waits for the processed data and logs it.
- If any promise in the chain is rejected, the error will be caught by the `.catch()` at the end.

## 3. Error Handling with `.catch()`

Error handling is an important aspect of working with promises. You can use the `.catch()` method to handle any errors that occur during the execution of the promise chain.

### Example: Error Handling

```javascript
const fetchData = () => {
    return new Promise((resolve, reject) => {
        setTimeout(() => {
            const success = false; // Simulate failure
            if (success) {
                resolve("Data received!");
            } else {
                reject("Error: Data not found.");
            }
        }, 2000);
    });
};

fetchData()
    .then((data) => {
        console.log(data);
    })
    .catch((error) => {
        console.error(error); // Outputs: Error: Data not found.
    });
```

### Explanation:
- In this example, if the `success` variable is set to `false`, the promise will be rejected, and the error message will be logged in the `.catch()` block.

## Conclusion

In this lesson, you learned how to create and use promises to handle asynchronous operations in JavaScript. You explored how to chain promises to perform multiple asynchronous tasks and how to handle errors effectively using the `.catch()` method. Promises provide a more manageable way to work with asynchronous code compared to callbacks, making your code cleaner and easier to understand. In the next lesson, we will dive into the `async` and `await` keywords, which allow for even more readable asynchronous code!