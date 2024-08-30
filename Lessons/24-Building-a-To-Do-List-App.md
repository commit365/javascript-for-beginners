# Lesson 24: Building a To-Do List App

In this lesson, we will create a simple To-Do List application using JavaScript. We will implement basic CRUD (Create, Read, Update, Delete) operations and use local storage to persist the data. This project will help you understand how to apply the concepts learned in previous lessons to build a functional web application.

## 1. Setting Up the Project

First, let's set up our project structure:

```plaintext
todo-list-app/
index.html
script.js
style.css
```

### `index.html`

This file will contain the HTML structure for our To-Do List app.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>To-Do List App</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <h1>To-Do List App</h1>
    <input type="text" id="taskInput" placeholder="Enter a task">
    <button id="addTaskButton">Add Task</button>
    <ul id="taskList"></ul>

    <script src="script.js"></script>
</body>
</html>
```

### `style.css`

This file will contain basic CSS styles to make our app look better.

```css
body {
    font-family: Arial, sans-serif;
}

#taskList {
    list-style-type: none;
    padding: 0;
}

#taskList li {
    margin-bottom: 10px;
}

#taskList li span {
    cursor: pointer;
}

#taskList li span:hover {
    text-decoration: underline;
}
```

## 2. Creating the JavaScript Logic

Now let's write the JavaScript code to handle CRUD operations and interact with local storage.

### `script.js`

```javascript
document.addEventListener("DOMContentLoaded", function() {
    const taskInput = document.getElementById("taskInput");
    const addTaskButton = document.getElementById("addTaskButton");
    const taskList = document.getElementById("taskList");

    // Load tasks from local storage on page load
    loadTasks();

    // Add event listener for adding new tasks
    addTaskButton.addEventListener("click", function() {
        const task = taskInput.value.trim();
        if (task) {
            addTask(task);
            taskInput.value = ""; // Clear input field after adding task
        }
    });

    // Function to load tasks from local storage
    function loadTasks() {
        const storedTasks = localStorage.getItem("tasks");
        if (storedTasks) {
            const tasks = JSON.parse(storedTasks);
            tasks.forEach(task => {
                addTaskToList(task);
            });
        }
    }

    // Function to add a new task to the list and save it to local storage
    function addTask(task) {
        const tasks = getTasksFromLocalStorage();
        tasks.push(task);
        saveTasksToLocalStorage(tasks);
        addTaskToList(task);
    }

    // Function to get tasks from local storage or return an empty array if none exist
    function getTasksFromLocalStorage() {
        const storedTasks = localStorage.getItem("tasks");
        return storedTasks ? JSON.parse(storedTasks) : [];
    }

    // Function to save tasks to local storage
    function saveTasksToLocalStorage(tasks) {
        localStorage.setItem("tasks", JSON.stringify(tasks));
    }

    // Function to add a task to the HTML list
    function addTaskToList(task) {
        const liElement = document.createElement("li");
        liElement.textContent = task;

        // Add delete button functionality
        const deleteButton = document.createElement("button");
        deleteButton.textContent = "Delete";
        deleteButton.onclick = function() {
            deleteTask(task);
            liElement.remove();
        };
        liElement.appendChild(deleteButton);

        taskList.appendChild(liElement);
    }

    // Function to delete a task from the list and update local storage
    function deleteTask(task) {
        const tasks = getTasksFromLocalStorage();
        const index = tasks.indexOf(task);
        if (index !== -1) {
            tasks.splice(index, 1);
            saveTasksToLocalStorage(tasks);
        }
    }
});
```

## Conclusion

In this lesson, you built a simple To-Do List application using JavaScript that includes basic CRUD operations and uses local storage for persistence. This project demonstrates how to apply various concepts learned throughout these lessons into practical use cases. By organizing your code into logical parts and using appropriate data structures like arrays for storing tasks, you can create functional web applications efficiently. In the next lesson, we will explore more advanced topics in JavaScript.

[Next: 25-Form-Validation-Techniques](./25-Form-Validation-Techniques.md)