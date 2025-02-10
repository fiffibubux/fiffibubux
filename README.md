<!DOCTYPE html>
<html lang="it">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Notion Flip Clock Widget</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Pacifico&display=swap');
        
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: transparent;
            font-family: 'Pacifico', cursive;
        }
        .flip-clock {
            display: flex;
            font-size: 3em;
            font-weight: bold;
            color: #D87093;
            text-shadow: 2px 2px 5px rgba(216, 112, 147, 0.5);
        }
        .digit {
            background: rgba(255, 209, 220, 0.8);
            padding: 10px 15px;
            margin: 5px;
            border-radius: 10px;
            box-shadow: 2px 2px 5px rgba(255, 192, 203, 0.5);
            display: inline-block;
            position: relative;
        }
        .separator {
            padding: 0 10px;
            color: #D87093;
        }
    </style>
</head>
<body>
    <div class="flip-clock" id="clock">
        <span class="digit" id="hours">00</span>
        <span class="separator">❤</span>
        <span class="digit" id="minutes">00</span>
        <span class="separator">❤</span>
        <span class="digit" id="seconds">00</span>
    </div>
    <script>
        function updateClock() {
            const now = new Date();
            let hours = now.getHours().toString().padStart(2, '0');
            let minutes = now.getMinutes().toString().padStart(2, '0');
            let seconds = now.getSeconds().toString().padStart(2, '0');
            document.getElementById('hours').innerText = hours;
            document.getElementById('minutes').innerText = minutes;
            document.getElementById('seconds').innerText = seconds;
        }
        setInterval(updateClock, 1000);
        updateClock();
    </script>
</body>
</html>
