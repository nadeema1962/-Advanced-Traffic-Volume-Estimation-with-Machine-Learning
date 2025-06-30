<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Traffic Volume Estimation</title>
    <style>
        body {
            background-image: url("/static/images/background.jpg");
            color: black;
            background-size: cover;
            background-repeat: no-repeat;
        }
        .container {
            max-width: 600px;
            margin: 0 auto;
            padding: 20px;
            background-color: rgba(255, 255, 255, 0.8);
            border-radius: 10px;
            margin-top: 50px;
        }
        form {
            margin-top: 20px;
        }
    </style>
</head>
<body>

<div class="container">
    <h1 style="text-align: center;">Traffic Volume Estimation</h1>
        <!-- Main Input Form -->
 <form action="{{ url_for('predict') }}" method="post">
        <h2>Please enter the following details:</h2>

        <label for="holiday">Holiday:</label>
        <select id="holiday" name="holiday">
            <option value="7">None</option>
            <option value="1">Columbus Day</option>
            <option value="10">Veterans Day</option>
            <option value="9">Thanksgiving Day</option>
            <option value="0">Christmas Day</option>
            <option value="6">New Years Day</option>
            <option value="11">Washingtons Birthday</option>
            <option value="5">Memorial Day</option>
            <option value="2">Independence Day</option>
            <option value="8">State Fair</option>
            <option value="3">Labor Day</option>
            <option value="4">Martin Luther King Jr Day</option>
        </select><br><br>

        <label for="temp">Temperature:</label>
        <input type="number" name="temp" placeholder="Temperature" required><br><br>

        <label for="rain">Rain (0 or 1):</label>
        <input type="number" min="0" max="1" name="rain" placeholder="Rain" required><br><br>

        <label for="snow">Snow (0 or 1):</label>
        <input type="number" min="0" max="1" name="snow" placeholder="Snow" required><br><br>

        <label for="weather">Weather:</label>
        <select id="weather" name="weather">
            <option value="1">Clouds</option>
            <option value="6">Clear</option>
            <option value="4">Rain</option>
            <option value="2">Drizzle</option>
            <option value="5">Mist</option>
            <option value="3">Haze</option>
            <option value="8">Fog</option>
            <option value="10">Thunderstorm</option>
            <option value="8">Snow</option>
            <option value="9">Squall</option>
            <option value="7">Smoke</option>
        </select><br><br>

        <label for="year">Year:</label>
        <input type="number" min="2012" max="2022" name="year" placeholder="Year" required><br><br>

        <label for="month">Month:</label>
        <input type="number" min="1" max="12" name="month" placeholder="Month" required><br><br>

        <label for="day">Day:</label>
        <input type="number" min="1" max="31" name="day" placeholder="Day" required><br><br>

        <label for="hours">Hours:</label>
        <input type="number" min="0" max="23" name="hours" placeholder="Hours" required><br><br>

        <label for="minutes">Minutes:</label>
        <input type="number" min="0" max="59" name="minutes" placeholder="Minutes" required><br><br>

        <label for="seconds">Seconds:</label>
        <input type="number" min="0" max="59" name="seconds" placeholder="Seconds" required><br><br>

        <button type="submit" style="height: 30px; width: 200px;">Predict</button>
    </form>

    <!-- Display prediction result -->
 <div id="predictionResult" style="margin-top: 20px;">
        {{ prediction_text }}
    </div>

    <!-- Image -->
<img src="/static/images/car.avif" alt="Car" height="180" width="240">
</div>

</body>
</html>
