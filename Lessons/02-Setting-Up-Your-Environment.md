# Lesson 2: Setting Up Your Environment

## Installing a Code Editor (e.g., Visual Studio Code)

A code editor is an essential tool for writing and managing your JavaScript code. Visual Studio Code (VS Code) is a popular, free, and powerful code editor that provides a great environment for JavaScript development. Follow these steps to install and set up Visual Studio Code:

### Step 1: Download Visual Studio Code
1. Visit the [Visual Studio Code website](https://code.visualstudio.com/).
2. Click on the **Download** button for your operating system (Windows, macOS, or Linux).

### Step 2: Install Visual Studio Code
1. Once the download is complete, open the installer.
2. Follow the installation prompts:
   - Accept the license agreement.
   - Choose the installation location.
   - Select additional tasks (you can check options for creating a desktop icon and adding to PATH).
3. Click **Install** and wait for the installation to complete.
4. Launch Visual Studio Code after installation.

### Step 3: Customize Your Editor
1. **Install Extensions**: Extensions enhance the functionality of VS Code. Some recommended extensions for JavaScript development include:
   - **ESLint**: Helps you maintain consistent coding styles by identifying and fixing problems in your JavaScript code.
   - **Prettier**: A code formatter that helps keep your code clean and organized.
   - **Live Server**: Allows you to launch a local development server with live reload capabilities for static and dynamic pages.
   
   To install extensions:
   - Click on the Extensions view icon in the Activity Bar on the side of the window.
   - Search for the desired extension and click **Install**.

2. **Customize Settings**: You can customize settings like font size, color theme, and editor layout by going to `File > Preferences > Settings` (or `Code > Preferences > Settings` on macOS).

## Setting Up a Local Development Environment and Browser Tools

To effectively develop and test your JavaScript applications, it’s important to set up a local development environment and familiarize yourself with browser tools.

### Step 1: Create a Project Folder
1. Create a new folder on your computer where you will store your JavaScript projects. You can name it something like `JavaScriptProjects`.
2. Open Visual Studio Code and navigate to `File > Open Folder...` to open your newly created folder.

### Step 2: Create Your First HTML File
1. Inside your project folder, create a new file named `index.html`.
2. Add the following basic HTML structure to the file:

   ```html
   <!DOCTYPE html>
   <html lang="en">
   <head>
       <meta charset="UTF-8">
       <meta name="viewport" content="width=device-width, initial-scale=1.0">
       <title>My First JavaScript Project</title>
   </head>
   <body>
       <h1>Hello, JavaScript!</h1>
       <script src="script.js"></script>
   </body>
   </html>
   ```

### Step 3: Create Your First JavaScript File
1. In the same project folder, create a new file named `script.js`.
2. Add the following simple JavaScript code to the file:

   ```javascript
   console.log("Welcome to JavaScript!");
   ```

### Step 4: Run Your Project
1. If you installed the **Live Server** extension, right-click on `index.html` in the Explorer sidebar and select **Open with Live Server**. This will launch your HTML file in your default web browser.
2. Open the browser's Developer Tools (usually by pressing `F12` or right-clicking on the page and selecting **Inspect**) to view the console.
3. You should see the message "Welcome to JavaScript!" in the console.

### Step 5: Familiarize Yourself with Browser Tools
- **Elements Tab**: Inspect and modify the HTML structure and CSS styles of your web page.
- **Console Tab**: View log messages, run JavaScript commands, and debug your code.
- **Network Tab**: Monitor network requests and responses, useful for debugging API calls.
- **Sources Tab**: View and debug your JavaScript files, set breakpoints, and step through code execution.

## Conclusion

In this lesson, you installed Visual Studio Code, created a basic project structure, and set up a local development environment to start coding in JavaScript. You also learned how to use browser tools to inspect and debug your code. In the next lesson, we will write your first JavaScript program and explore the console further!