# Lesson 3: Your First JavaScript Program

## Writing and Running a Simple "Hello, World!" Program

In this lesson, you will write and run your very first JavaScript program: a simple "Hello, World!" message. This classic program is often the first step in learning any programming language.

### Step 1: Open Your Project in Visual Studio Code
1. Launch Visual Studio Code.
2. Open the project folder you created in the previous lesson (e.g., `JavaScriptProjects`).

### Step 2: Create a New JavaScript File
1. In your project folder, create a new file named `hello.js`.
2. Open `hello.js` in the editor.

### Step 3: Write Your First JavaScript Code
1. In `hello.js`, type the following code:

   ```javascript
   console.log("Hello, World!");
   ```

   This line of code uses the `console.log()` function to print the message "Hello, World!" to the console.

### Step 4: Run Your JavaScript Program
You have a couple of options to run your JavaScript code:

#### Option 1: Using Live Server (for HTML)
1. If you want to run it in the context of an HTML file, you can modify your `index.html` file to include the `hello.js` script. Add the following line inside the `<body>` tag:

   ```html
   <script src="hello.js"></script>
   ```

2. Save the changes to `index.html`.
3. Right-click on `index.html` in the Explorer sidebar and select **Open with Live Server**.
4. Open the Developer Tools in your browser (usually by pressing `F12`), and navigate to the **Console** tab. You should see "Hello, World!" printed there.

#### Option 2: Using Node.js (for standalone JavaScript)
1. If you have Node.js installed, you can run your JavaScript file directly from the terminal.
2. Open a terminal in Visual Studio Code (you can do this by selecting `Terminal > New Terminal`).
3. In the terminal, type the following command and press Enter:

   ```bash
   node hello.js
   ```

4. You should see "Hello, World!" printed in the terminal.

## Understanding the Console for Debugging and Logging

The console is a powerful tool for debugging and logging information while developing JavaScript applications. Here are some key features and uses of the console:

### Console Methods
- **`console.log()`**: This method is used to print messages to the console. It's commonly used for debugging to check the values of variables or to track the flow of execution.
  
  ```javascript
  console.log("This is a log message.");
  ```

- **`console.error()`**: This method is used to display error messages in the console. It helps in identifying issues in your code.

  ```javascript
  console.error("This is an error message.");
  ```

- **`console.warn()`**: This method displays warning messages. Warnings can indicate potential issues that may not necessarily stop the program from running.

  ```javascript
  console.warn("This is a warning message.");
  ```

- **`console.table()`**: This method displays data in a table format, which is useful for visualizing arrays and objects.

  ```javascript
  const fruits = ["Apple", "Banana", "Cherry"];
  console.table(fruits);
  ```

### Using the Console for Debugging
1. **Inspect Variables**: You can log variable values to the console to check if they hold the expected values at different points in your code.

   ```javascript
   let x = 10;
   console.log("The value of x is:", x);
   ```

2. **Track Code Execution**: Use `console.log()` statements to track the flow of your program, especially in functions or loops.

   ```javascript
   function greet(name) {
       console.log("Entering greet function");
       console.log("Hello, " + name + "!");
   }
   greet("Alice");
   ```

3. **Identify Errors**: When an error occurs, the console will display error messages, including the line number where the error happened. This helps you quickly locate and fix issues in your code.

## Conclusion

In this lesson, you successfully wrote and ran your first JavaScript program, "Hello, World!" You also learned how to use the console for debugging and logging, which is an essential skill for any developer. In the next lesson, we will explore variables and data types in JavaScript!