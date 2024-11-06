<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Clock</title>
    <style>
        /* CSS styling for the clock */
        body {
            display: flex;
            align-items: center;
            justify-content: center;
            height: 100vh;
            margin: 0;
            background-color: #282c34;
            font-family: Arial, sans-serif;
            color: #61dafb;
        }
        #clock {
            font-size: 4rem;
            font-weight: bold;
            text-align: center;
        }
    </style>
</head>
<body>
    <!-- Clock Container -->
    <div id="clock">
        <span id="hours">00</span>:<span id="minutes">00</span>:<span id="seconds">00</span>
        <span id="period">AM</span>
    </div>

    <script>
        // JavaScript to update the clock every second
        function updateClock() {
            const now = new Date();
            let hours = now.getHours();
            const minutes = now.getMinutes();
            const seconds = now.getSeconds();
            const period = hours >= 12 ? "PM" : "AM";

            // Convert to 12-hour format
            hours = hours % 12 || 12;

            // Format hours, minutes, and seconds with leading zeros
            const formattedHours = String(hours).padStart(2, '0');
            const formattedMinutes = String(minutes).padStart(2, '0');
            const formattedSeconds = String(seconds).padStart(2, '0');

            // Update clock elements
            document.getElementById("hours").textContent = formattedHours;
            document.getElementById("minutes").textContent = formattedMinutes;
            document.getElementById("seconds").textContent = formattedSeconds;
            document.getElementById("period").textContent = period;
        }

        // Call updateClock every 1 second
        setInterval(updateClock, 1000);

        // Initial call to display the clock immediately
        updateClock();
    </script>
</body>
</html>
