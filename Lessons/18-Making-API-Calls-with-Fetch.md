# Lesson 18: Making API Calls with Fetch

The `fetch` API is a modern JavaScript interface that allows you to make HTTP requests to servers and retrieve data. It is a powerful tool for interacting with APIs (Application Programming Interfaces) and is built into most modern browsers. In this lesson, we will learn how to use the `fetch` API to make API calls, handle JSON responses, and manage errors.

## 1. Using the Fetch API to Make HTTP Requests

The `fetch` function returns a promise that resolves to the response of the request. By default, it makes a GET request to the specified URL.

### Basic Syntax:
```javascript
fetch(url, options)
    .then(response => {
        // Handle the response
    })
    .catch(error => {
        // Handle any errors
    });
```

- **`url`**: The URL to which the request is sent.
- **`options`**: An optional object that contains any custom settings for the request (e.g., method, headers, body).

### Example: Making a GET Request
```javascript
fetch("https://jsonplaceholder.typicode.com/posts")
    .then(response => {
        return response.json(); // Parse the JSON from the response
    })
    .then(data => {
        console.log(data); // Outputs the array of posts
    })
    .catch(error => {
        console.error("Error fetching data:", error);
    });
```

### Explanation:
- In this example, we make a GET request to a placeholder API that returns a list of posts.
- The response is parsed as JSON using the `.json()` method, which also returns a promise.
- The parsed data is then logged to the console.

## 2. Handling JSON Responses

The `fetch` API makes it easy to work with JSON data. After making a request, you can use the `.json()` method to parse the response body as JSON.

### Example: Fetching and Displaying Data
```javascript
fetch("https://jsonplaceholder.typicode.com/posts")
    .then(response => {
        if (!response.ok) {
            throw new Error("Network response was not ok: " + response.statusText);
        }
        return response.json(); // Parse the JSON
    })
    .then(data => {
        data.forEach(post => {
            console.log(`Title: ${post.title}`);
            console.log(`Body: ${post.body}`);
            console.log("---");
        });
    })
    .catch(error => {
        console.error("Error fetching data:", error);
    });
```

### Explanation:
- The example checks if the response is OK (status code in the range 200-299) using the `response.ok` property.
- If the response is not OK, it throws an error with the status text.
- If successful, it parses the response as JSON and logs the title and body of each post.

## 3. Making POST Requests

You can also use the `fetch` API to make POST requests, which are commonly used to send data to a server.

### Example: Making a POST Request
```javascript
const postData = {
    title: "New Post",
    body: "This is the body of the new post.",
    userId: 1
};

fetch("https://jsonplaceholder.typicode.com/posts", {
    method: "POST", // Specify the request method
    headers: {
        "Content-Type": "application/json" // Set the content type
    },
    body: JSON.stringify(postData) // Convert the data to a JSON string
})
    .then(response => {
        if (!response.ok) {
            throw new Error("Network response was not ok: " + response.statusText);
        }
        return response.json(); // Parse the JSON response
    })
    .then(data => {
        console.log("Post created:", data); // Outputs the created post
    })
    .catch(error => {
        console.error("Error creating post:", error);
    });
```

### Explanation:
- In this example, we create a new post by sending a POST request to the API.
- We specify the method as "POST" and set the `Content-Type` header to "application/json".
- The `body` of the request is the stringified version of the `postData` object.
- After the request, we check the response and log the created post.

## 4. Error Handling

Error handling is crucial when making API calls. You should handle both network errors and response errors.

### Example of Handling Errors
```javascript
fetch("https://jsonplaceholder.typicode.com/posts/999") // Non-existent post
    .then(response => {
        if (!response.ok) {
            throw new Error("Network response was not ok: " + response.statusText);
        }
        return response.json();
    })
    .then(data => {
        console.log(data); // This will not run if there is an error
    })
    .catch(error => {
        console.error("Error fetching data:", error); // Outputs: Error fetching data: Network response was not ok: Not Found
    });
```

### Explanation:
- In this example, we attempt to fetch a non-existent post (ID 999).
- The error is caught in the `.catch()` block, allowing us to handle it gracefully.

## Conclusion

In this lesson, you learned how to use the `fetch` API to make HTTP requests, handle JSON responses, and manage errors effectively. The `fetch` API provides a modern way to interact with APIs and is essential for building dynamic web applications that communicate with servers. In the next lesson, we will explore how to work with local storage and session storage to manage data in the browser!