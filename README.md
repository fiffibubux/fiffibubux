<!DOCTYPE html>
<html lang="it">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Flip Clock Widget</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Fredoka+One&display=swap');
        
        body {
            background: transparent;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            position: relative;
            flex-direction: column;
        }

        .clock {
            font-family: 'Fredoka One', cursive;
            font-size: 48px;
            color: #FF99CC;
            display: flex;
            align-items: center;
            gap: 10px;
            position: relative;
        }

        .heart {
            font-size: 24px;
            color: #FF99CC;
            animation: bounce 1.5s infinite alternate;
        }

        @keyframes bounce {
            0% { transform: translateY(0); }
            100% { transform: translateY(-5px); }
        }

        .gif-container {
            position: relative;
            margin-bottom: -10px; /* Avvicina la GIF all'orologio */
        }

        .gif-container img {
            width: 50px; /* Rende la GIF più piccola */
        }
    </style>
</head>
<body>
    <div class="gif-container">
        <img src="https://media.giphy.com/media/1HEfctM48fTSanADqj/giphy.gif" alt="Cute GIF">
    </div>
    <div class="clock">
        <span class="heart">💗</span>
        <span id="time">00:00:00</span>
        <span class="heart">💗</span>
    </div>

    <script>
        function updateTime() {
            const now = new Date();
            const hours = String(now.getHours()).padStart(2, '0');
            const minutes = String(now.getMinutes()).padStart(2, '0');
            const seconds = String(now.getSeconds()).padStart(2, '0');
            document.getElementById('time').textContent = `${hours}:${minutes}:${seconds}`;
        }
        setInterval(updateTime, 1000);
        updateTime();
    </script>
</body>
</html>
