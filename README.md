# Weather-service
@echo off

REM Create and navigate to the project directory
mkdir weather-service
cd weather-service

REM Initialize a new Node.js project
npm init -y

REM Install necessary dependencies
npm install express axios

REM Create server.js and write code into it
echo const express = require('express'); > server.js
echo const axios = require('axios'); >> server.js
echo. >> server.js
echo const app = express(); >> server.js
echo const port = 3000; >> server.js
echo const apiKey = 'YOUR_API_KEY_HERE';  REM Replace with your Weatherstack API key >> server.js
echo. >> server.js
echo app.get('/weather', async (req, res) => { >> server.js
echo    const city = req.query.city; >> server.js
echo    try { >> server.js
echo        const response = await axios.get(`http://api.weatherstack.com/current?access_key=%apiKey%&query=%city%`); >> server.js
echo        res.json(response.data); >> server.js
echo    } catch (error) { >> server.js
echo        res.status(500).send('Error fetching weather data'); >> server.js
echo    } >> server.js
echo }); >> server.js
echo. >> server.js
echo app.listen(port, () => { >> server.js
echo    console.log(`Weather service is running at http://localhost:%port%`); >> server.js
echo }); >> server.js

REM Start the server
node server.js
