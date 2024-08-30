# Lesson 13: Selecting and Modifying DOM Elements

In this lesson, we will focus on how to select and modify DOM elements using JavaScript. Understanding how to manipulate the DOM is essential for creating interactive web applications. We will cover methods for selecting elements and techniques for changing their styles, attributes, and content dynamically.

## 1. Selecting DOM Elements

JavaScript provides several methods to select elements from the DOM. Here are the most commonly used methods:

### 1.1 `getElementById()`

The `getElementById()` method selects an element based on its unique ID. It returns a single element.

**Syntax:**
```javascript
let element = document.getElementById("elementId");
```

**Example:**
```html
<h1 id="mainHeading">Welcome!</h1>
<script>
    let heading = document.getElementById("mainHeading");
    console.log(heading); // Outputs: <h1 id="mainHeading">Welcome!</h1>
</script>
```

### 1.2 `querySelector()`

The `querySelector()` method selects the first element that matches a specified CSS selector. It can be used to select elements by class, tag, or any valid CSS selector.

**Syntax:**
```javascript
let element = document.querySelector("selector");
```

**Example:**
```html
<p class="description">This is a description paragraph.</p>
<script>
    let paragraph = document.querySelector(".description");
    console.log(paragraph); // Outputs: <p class="description">This is a description paragraph.</p>
</script>
```

### 1.3 `querySelectorAll()`

The `querySelectorAll()` method selects all elements that match a specified CSS selector and returns a NodeList. This is useful for selecting multiple elements.

**Syntax:**
```javascript
let elements = document.querySelectorAll("selector");
```

**Example:**
```html
<ul>
    <li class="item">Item 1</li>
    <li class="item">Item 2</li>
    <li class="item">Item 3</li>
</ul>
<script>
    let items = document.querySelectorAll(".item");
    items.forEach(item => {
        console.log(item.textContent); // Outputs: Item 1, Item 2, Item 3
    });
</script>
```

## 2. Modifying DOM Elements

Once you have selected DOM elements, you can modify their properties, styles, and content dynamically.

### 2.1 Changing Content

You can change the text content or HTML content of an element using the `textContent` or `innerHTML` properties.

- **`textContent`**: Sets or gets the text content of an element, stripping any HTML tags.
- **`innerHTML`**: Sets or gets the HTML content of an element, allowing you to include HTML tags.

**Example:**
```html
<p id="myParagraph">Original text.</p>
<script>
    let paragraph = document.getElementById("myParagraph");
    paragraph.textContent = "Updated text."; // Changes the text
    console.log(paragraph.textContent); // Outputs: Updated text.

    paragraph.innerHTML = "<strong>Updated with HTML!</strong>"; // Changes the HTML content
    console.log(paragraph.innerHTML); // Outputs: <strong>Updated with HTML!</strong>
</script>
```

### 2.2 Changing Styles

You can modify the CSS styles of an element using the `style` property. This allows you to change individual CSS properties dynamically.

**Example:**
```html
<div id="myDiv" style="width: 100px; height: 100px; background-color: red;"></div>
<script>
    let div = document.getElementById("myDiv");
    div.style.backgroundColor = "blue"; // Changes background color
    div.style.width = "200px"; // Changes width
</script>
```

### 2.3 Changing Attributes

You can change the attributes of an element using the `setAttribute()` method or by directly accessing the attribute property.

**Example:**
```html
<a id="myLink" href="https://www.example.com">Visit Example</a>
<script>
    let link = document.getElementById("myLink");
    link.setAttribute("href", "https://www.new-url.com"); // Changes the href attribute
    link.textContent = "Visit New URL"; // Changes the link text
</script>
```

### 2.4 Removing Elements

You can remove an element from the DOM using the `remove()` method.

**Example:**
```html
<p id="removeMe">This paragraph will be removed.</p>
<script>
    let paragraph = document.getElementById("removeMe");
    paragraph.remove(); // Removes the paragraph from the DOM
</script>
```

## Conclusion

In this lesson, you learned how to select DOM elements using `getElementById`, `querySelector`, and `querySelectorAll`. You also explored how to modify the content, styles, and attributes of these elements dynamically. Understanding how to manipulate the DOM is essential for creating interactive web applications. In the next lesson, we will dive into event handling, which allows you to respond to user interactions on your web pages!

[Next: 14-Event-Handling](./14-Event-Handling.md)