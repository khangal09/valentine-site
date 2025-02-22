<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Будешь моей Валентинкой?</title>
    <style>
        body {
            font-family: 'Comic Sans MS', cursive, sans-serif;
            background: linear-gradient(135deg, #ff9aa2, #ffb7b2, #ffdac1);
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            overflow: hidden;
        }

        .container {
            text-align: center;
            background-color: rgba(255, 255, 255, 0.9);
            padding: 40px;
            border-radius: 20px;
            box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2);
            position: relative;
        }

        h1 {
            color: #ff477e;
            font-size: 3em;
            margin-bottom: 30px;
            animation: fadeIn 2s ease-in-out;
        }

        .buttons {
            margin: 20px;
        }

        button {
            font-size: 1.5em;
            padding: 15px 30px;
            margin: 15px;
            border: none;
            border-radius: 15px;
            cursor: pointer;
            transition: all 0.3s ease;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
        }

        #yesBtn {
            background-color: #ff477e;
            color: white;
        }

        #yesBtn:hover {
            background-color: #ff1c61;
            transform: scale(1.1);
        }

        #noBtn {
            background-color: #ff8fa3;
            color: white;
            position: relative;
        }

        #noBtn:hover {
            background-color: #ff6b81;
        }

        #responseMessage {
            font-size: 1.8em;
            color: #d00000;
            margin-top: 20px;
            animation: fadeIn 1s ease-in-out;
        }

        /* Heart animation */
        @keyframes fadeIn {
            from { opacity: 0; transform: scale(0.9); }
            to { opacity: 1; transform: scale(1); }
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Будешь моей Валентинкой? 💌</h1>
        <div class="buttons">
            <button id="yesBtn">Да! ❤️</button>
            <button id="noBtn">Нет... 😢</button>
        </div>
        <p id="responseMessage"></p>
    </div>

    <script>
        const yesBtn = document.getElementById('yesBtn');
        const noBtn = document.getElementById('noBtn');
        const responseMessage = document.getElementById('responseMessage');

        // When "Yes" is clicked
        yesBtn.addEventListener('click', () => {
            responseMessage.textContent = "Ура! Я так счастлив(а)! 💕🌸";
            createHearts();
        });

        // When "No" is hovered over, it moves away
        noBtn.addEventListener('mouseover', () => {
            const randomX = Math.floor(Math.random() * (window.innerWidth - noBtn.offsetWidth));
            const randomY = Math.floor(Math.random() * (window.innerHeight - noBtn.offsetHeight));
            noBtn.style.position = 'absolute';
            noBtn.style.left = `${randomX}px`;
            noBtn.style.top = `${randomY}px`;
        });

        // Function to create hearts when "Yes" is clicked
        function createHearts() {
            for (let i = 0; i < 30; i++) {
                const heart = document.createElement('div');
                heart.textContent = '💖';
                heart.style.position = 'absolute';
                heart.style.left = `${Math.random() * 100}%`;
                heart.style.top = `${Math.random() * 100}%`;
                heart.style.fontSize = `${Math.random() * 30 + 20}px`;
                heart.style.animation = `fadeIn 2s ease-in-out`;
                document.body.appendChild(heart);

                setTimeout(() => heart.remove(), 3000); // Hearts disappear after 3 seconds
            }
        }
    </script>
</body>
</html>