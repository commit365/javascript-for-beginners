# Lesson 14: Event Handling

Event handling is a crucial aspect of JavaScript that allows you to create interactive web applications. By responding to user interactions, such as clicks, keystrokes, and form submissions, you can enhance the user experience. In this lesson, we will explore how to add event listeners and handle various types of events.

## 1. Adding Event Listeners for User Interactions

An event listener is a function that waits for a specific event to occur on a particular element. You can add an event listener to an element using the `addEventListener()` method.

### Syntax:
```javascript
element.addEventListener(event, function);
```

- **`event`**: A string representing the event type (e.g., `"click"`, `"input"`).
- **`function`**: The function to be executed when the event occurs.

### Example: Adding a Click Event Listener
```html
<button id="myButton">Click Me!</button>
<script>
    let button = document.getElementById("myButton");
    button.addEventListener("click", function() {
        alert("Button was clicked!");
    });
</script>
```

In this example, when the button is clicked, an alert will pop up displaying the message.

## 2. Handling Various Events

### 2.1 Click Events

Click events are triggered when a user clicks on an element, such as a button or a link. You can handle click events to perform actions like showing alerts, changing content, or navigating to a different page.

**Example: Changing Text on Button Click**
```html
<button id="changeTextButton">Change Text</button>
<p id="text">Original Text</p>
<script>
    let changeTextButton = document.getElementById("changeTextButton");
    changeTextButton.addEventListener("click", function() {
        let textParagraph = document.getElementById("text");
        textParagraph.textContent = "Text has been changed!";
    });
</script>
```

### 2.2 Input Events

Input events are triggered when the value of an input field changes. This can be useful for validating user input in real-time or updating other elements based on the input.

**Example: Real-Time Input Handling**
```html
<input type="text" id="nameInput" placeholder="Enter your name">
<p id="greeting"></p>
<script>
    let nameInput = document.getElementById("nameInput");
    let greeting = document.getElementById("greeting");

    nameInput.addEventListener("input", function() {
        greeting.textContent = "Hello, " + nameInput.value + "!";
    });
</script>
```

In this example, as the user types in the input field, the greeting message updates in real-time.

### 2.3 Form Events

Form events are triggered when a user interacts with a form, such as submitting it. You can handle form submissions to validate input, prevent default behavior, or send data to a server.

**Example: Handling Form Submission**
```html
<form id="myForm">
    <input type="text" id="username" placeholder="Enter your username" required>
    <button type="submit">Submit</button>
</form>
<p id="formMessage"></p>
<script>
    let myForm = document.getElementById("myForm");
    let formMessage = document.getElementById("formMessage");

    myForm.addEventListener("submit", function(event) {
        event.preventDefault(); // Prevents the default form submission
        let username = document.getElementById("username").value;
        formMessage.textContent = "Form submitted! Welcome, " + username + "!";
    });
</script>
```

In this example, when the form is submitted, the default action (which would normally refresh the page) is prevented, and a message is displayed instead.

## Conclusion

In this lesson, you learned about event handling in JavaScript, including how to add event listeners for user interactions. You explored various events such as click events, input events, and form events, and saw practical examples of how to handle these events to create dynamic and interactive web applications. Understanding event handling is essential for enhancing user experience on your web pages. In the next lesson, we will explore more advanced topics in JavaScript, including working with asynchronous code!

[Next: 15-Asynchronous-JavaScript](./15-Asynchronous-JavaScript.md)