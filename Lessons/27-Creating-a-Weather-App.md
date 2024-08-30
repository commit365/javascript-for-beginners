# Lesson 27: Creating a Weather App

In this lesson, we will build a simple weather application that fetches real-time weather data from a public API. We will allow users to input a city name and display the current weather conditions for that city. This project will help you understand how to work with APIs, handle user input, and dynamically update the UI with JavaScript.

## 1. Setting Up the Project

First, create the following project structure:

```plaintext
weather-app/
index.html
style.css
script.js
```

### `index.html`

This file will contain the HTML structure for our weather app.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Weather App</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <h1>Weather App</h1>
    <input type="text" id="cityInput" placeholder="Enter city name">
    <button id="getWeatherButton">Get Weather</button>
    <div id="weatherResult"></div>

    <script src="script.js"></script>
</body>
</html>
```

### `style.css`

Add some basic styles to make the application look better.

```css
body {
    font-family: Arial, sans-serif;
    text-align: center;
    margin: 20px;
}

input {
    padding: 10px;
    font-size: 16px;
    margin-right: 10px;
}

button {
    padding: 10px;
    font-size: 16px;
    cursor: pointer;
}

#weatherResult {
    margin-top: 20px;
    font-size: 18px;
}
```

## 2. Fetching Weather Data from a Public API

We will use the OpenWeatherMap API to fetch weather data. You will need to sign up for a free account and obtain an API key from [OpenWeatherMap](https://openweathermap.org/api).

### `script.js`

Now, let's write the JavaScript code to handle user input, fetch weather data, and display the results.

```javascript
document.addEventListener("DOMContentLoaded", function() {
    const cityInput = document.getElementById("cityInput");
    const getWeatherButton = document.getElementById("getWeatherButton");
    const weatherResult = document.getElementById("weatherResult");

    getWeatherButton.addEventListener("click", function() {
        const city = cityInput.value.trim();
        if (city) {
            getWeather(city);
        } else {
            weatherResult.textContent = "Please enter a city name.";
        }
    });

    async function getWeather(city) {
        const apiKey = "YOUR_API_KEY"; // Replace with your OpenWeatherMap API key
        const url = `https://api.openweathermap.org/data/2.5/weather?q=${city}&appid=${apiKey}&units=metric`;

        try {
            const response = await fetch(url);
            if (!response.ok) {
                throw new Error("City not found");
            }
            const data = await response.json();
            displayWeather(data);
        } catch (error) {
            weatherResult.textContent = error.message; // Display error message
        }
    }

    function displayWeather(data) {
        const { name, main, weather } = data;
        weatherResult.innerHTML = `
            <h2>Weather in ${name}</h2>
            <p>Temperature: ${main.temp} °C</p>
            <p>Condition: ${weather[0].description}</p>
        `;
    }
});
```

### Explanation of the Code

1. **Event Listener for Button Click**: When the "Get Weather" button is clicked, the app checks if the user has entered a city name. If not, it prompts the user to enter a valid name.

2. **Fetching Weather Data**: The `getWeather` function constructs the API URL using the city name and the API key, then fetches the data using the `fetch` API. If the response is not OK (e.g., city not found), it throws an error.

3. **Displaying Weather Data**: If the fetch is successful, the `displayWeather` function extracts the relevant data (city name, temperature, and weather condition) and updates the UI with this information.

4. **Error Handling**: If an error occurs (e.g., invalid city name), it displays an appropriate error message.

## 3. Testing the Weather App

1. Replace `YOUR_API_KEY` in `script.js` with your actual OpenWeatherMap API key.
2. Open `index.html` in your web browser.
3. Enter a city name (e.g., "London") and click the "Get Weather" button.
4. The current temperature and weather condition for the specified city will be displayed.

## Conclusion

In this lesson, you built a simple weather application that fetches real-time weather data from a public API. You learned how to handle user input, make API calls using the `fetch` API, and dynamically update the UI with JavaScript. This project demonstrates how to apply various JavaScript concepts to create a functional web application. In the next lesson, we will explore more advanced topics in JavaScript, including working with asynchronous programming and additional API integrations!

[Next: 28-Version-Control-with-Git](./28-Version-Control-with-Git.md)