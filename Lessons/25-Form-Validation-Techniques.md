# Lesson 25: Form Validation Techniques

Form validation is an essential part of web development that ensures user input is correct and meets specific criteria before it is submitted. In this lesson, we will explore how to add validation to user input forms using JavaScript and provide feedback to users on errors and successful submissions.

## 1. Setting Up the Project

First, let’s set up a simple HTML form for our project. Create an `index.html` file with the following structure:

### `index.html`

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Form Validation Example</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <h1>User Registration Form</h1>
    <form id="registrationForm">
        <label for="username">Username:</label>
        <input type="text" id="username" required>
        <span class="error" id="usernameError"></span>

        <label for="email">Email:</label>
        <input type="email" id="email" required>
        <span class="error" id="emailError"></span>

        <label for="password">Password:</label>
        <input type="password" id="password" required>
        <span class="error" id="passwordError"></span>

        <button type="submit">Register</button>
    </form>
    <div id="successMessage" class="success"></div>

    <script src="script.js"></script>
</body>
</html>
```

### `style.css`

Add some basic styles to make the form look better.

```css
body {
    font-family: Arial, sans-serif;
}

form {
    max-width: 400px;
    margin: auto;
}

label {
    display: block;
    margin: 10px 0 5px;
}

input {
    width: 100%;
    padding: 8px;
    margin-bottom: 10px;
}

.error {
    color: red;
    font-size: 0.9em;
}

.success {
    color: green;
    margin-top: 10px;
}
```

## 2. Adding Validation with JavaScript

Now, let’s write the JavaScript code to validate the form inputs and provide feedback to users.

### `script.js`

```javascript
document.addEventListener("DOMContentLoaded", function() {
    const form = document.getElementById("registrationForm");

    form.addEventListener("submit", function(event) {
        event.preventDefault(); // Prevent the default form submission

        // Clear previous error messages
        clearErrors();

        // Validate form fields
        const isValid = validateForm();

        if (isValid) {
            // Show success message
            document.getElementById("successMessage").textContent = "Registration successful!";
            form.reset(); // Reset the form
        }
    });

    function validateForm() {
        let isValid = true;

        // Validate username
        const username = document.getElementById("username").value;
        if (username.length < 3) {
            showError("usernameError", "Username must be at least 3 characters long.");
            isValid = false;
        }

        // Validate email
        const email = document.getElementById("email").value;
        const emailPattern = /^[^\s@]+@[^\s@]+\.[^\s@]+$/; // Simple email regex
        if (!emailPattern.test(email)) {
            showError("emailError", "Please enter a valid email address.");
            isValid = false;
        }

        // Validate password
        const password = document.getElementById("password").value;
        if (password.length < 6) {
            showError("passwordError", "Password must be at least 6 characters long.");
            isValid = false;
        }

        return isValid;
    }

    function showError(elementId, message) {
        const errorElement = document.getElementById(elementId);
        errorElement.textContent = message; // Set the error message
    }

    function clearErrors() {
        const errorElements = document.querySelectorAll(".error");
        errorElements.forEach(element => {
            element.textContent = ""; // Clear the error messages
        });
        document.getElementById("successMessage").textContent = ""; // Clear success message
    }
});
```

## 3. Explanation of the Code

### Form Submission Handling
- **Prevent Default Submission**: We use `event.preventDefault()` to prevent the form from submitting immediately, allowing us to validate the inputs first.
- **Clear Previous Errors**: The `clearErrors` function clears any previous error messages before validation.

### Validation Logic
- **Username Validation**: Checks if the username is at least 3 characters long.
- **Email Validation**: Uses a regular expression to check if the email is in a valid format.
- **Password Validation**: Checks if the password is at least 6 characters long.

### Error Handling
- **Show Error Messages**: The `showError` function displays error messages next to the respective input fields.
- **Success Message**: If the form is valid, a success message is displayed, and the form is reset.

## Conclusion

In this lesson, you learned how to implement form validation techniques using JavaScript. You created a user registration form that validates input fields, provides feedback on errors, and displays a success message upon successful submission. Proper form validation is crucial for enhancing user experience and ensuring data integrity in web applications. In the next lesson, we will explore more advanced topics in JavaScript, including working with APIs and asynchronous programming!