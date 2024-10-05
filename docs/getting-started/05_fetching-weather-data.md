---
title: JavaScript and Fetching Data
---

To fetch the weather data, we’ll use the OpenWeatherMap API. First, sign up at OpenWeatherMap and get an API key.

Next, write the following JavaScript code in your script.js file. This code will fetch the weather data for the city entered by the user and display it on the page.

```
const apiKey = 'YOUR_API_KEY';

document.getElementById('get-weather-btn').addEventListener('click', () => {
  const city = document.getElementById('city-input').value;
  if (city) {
    getWeather(city);
  } else {
    alert('Please enter a city name');
  }
});

function getWeather(city) {
  fetch(`https://api.openweathermap.org/data/2.5/weather?q=${city}&appid=${apiKey}&units=metric`)
    .then(response => response.json())
    .then(data => {
      if (data.cod === 200) {
        displayWeather(data);
      } else {
        alert('City not found');
      }
    })
    .catch(error => console.error('Error fetching weather data:', error));
}

function displayWeather(data) {
  const weatherInfo = `
    <h2>${data.name}</h2>
    <p>Temperature: ${data.main.temp}°C</p>
    <p>Weather: ${data.weather[0].description}</p>
    <p>Humidity: ${data.main.humidity}%</p>
  `;
  document.getElementById('weather-info').innerHTML = weatherInfo;
}
```
