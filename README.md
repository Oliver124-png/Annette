<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>¿Quieres ser mi Valentine?</title>
    <style>
        body {
            text-align: center;
            font-family: 'Arial', sans-serif;
            background: linear-gradient(to bottom, #ff4d6d, #ff99ac);
            overflow: hidden;
            color: white;
        }
        .container {
            margin-top: 100px;
        }
        .btn {
            font-size: 20px;
            padding: 10px 20px;
            margin: 10px;
            border: none;
            cursor: pointer;
            background-color: red;
            color: white;
            border-radius: 10px;
            font-weight: bold;
        }
        .hidden {
            display: none;
        }
        .message {
            font-size: 24px;
            background-color: rgba(255, 0, 0, 0.8);
            padding: 20px;
            border-radius: 10px;
            display: inline-block;
            margin-top: 20px;
            box-shadow: 0 0 15px rgba(255, 255, 255, 0.7);
        }
        .animation-container {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
        }
        .heart {
            position: absolute;
            color: red;
            font-size: 50px;
            font-weight: bold;
            text-shadow: 2px 2px 5px rgba(0, 0, 0, 0.3);
            animation: float 4s infinite ease-in-out;
        }
        .white-text {
            color: white;
        }
        @keyframes float {
            0% { transform: translateY(0); opacity: 1; }
            50% { transform: translateY(-200px); opacity: 0.5; }
            100% { transform: translateY(-400px); opacity: 0; }
        }
        .bears {
            margin-top: 20px;
        }
    </style>
</head>
<body>

    <div class="container">
        <h1>¿Quieres ser mi Valentine? ❤️</h1>
        <button class="btn" onclick="showLoveMessage()">Sí</button>
    </div>

    <div id="loveMessage" class="hidden">
        <div class="message">
            Sabía que dirías que sí, amor. ¡Te amo mucho! ❤️  
            <br><br>
            <strong>Sal, estoy afuera amor.</strong>
        </div>
        <div class="bears">
            <img src="https://media.tenor.com/qkKNy0CRwaAAAAAC/love-bears.gif" alt="Ositos besándose">
        </div>
    </div>

    <div class="animation-container" id="animationContainer"></div>

    <script>
        function showLoveMessage() {
            document.querySelector(".container").style.display = "none";
            document.getElementById("loveMessage").classList.remove("hidden");
            createHearts();
        }

        function createHearts() {
            const container = document.getElementById("animationContainer");
            for (let i = 0; i < 20; i++) {
                let heart = document.createElement("div");
                heart.classList.add("heart");
                heart.innerHTML = "<span class='white-text'>❤️ O&A ❤️</span>";
                heart.style.left = Math.random() * window.innerWidth + "px";
                heart.style.animationDuration = (Math.random() * 2 + 2) + "s";
                container.appendChild(heart);
                setTimeout(() => heart.remove(), 4000);
            }
            setInterval(createHearts, 2000);
        }
    </script>

</body>
</html>
