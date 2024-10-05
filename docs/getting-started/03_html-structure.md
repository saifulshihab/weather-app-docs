---
title: HTML Structure
---

Here is a simple HTML structure for your weather app. This includes an input field for users to type the city name and a button to fetch the weather data.

```
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Weather App</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <div class="container">
    <h1>Weather App</h1>
    <input type="text" id="city-input" placeholder="Enter city name" />
    <button id="get-weather-btn">Get Weather</button>
    <div id="weather-info"></div>
  </div>
  <script src="script.js"></script>
</body>
</html>
```
