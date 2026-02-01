<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Will You Be My Valentine?</title>
    <style>
        body {
            background-color: pink;
            font-family: Arial, sans-serif;
            text-align: center;
            padding-top: 100px;
        }
        h1 {
            color: #ff69b4; /* Hot pink */
            font-size: 2em;
        }
        .cow {
            font-size: 5em;
            margin: 20px;
        }
        button {
            padding: 10px 20px;
            font-size: 1.2em;
            margin: 20px;
            cursor: pointer;
            border: none;
            border-radius: 5px;
            transition: all 0.3s ease;
        }
        #yesBtn {
            background-color: #ff1493; /* Deep pink */
            color: white;
        }
        #noBtn {
            background-color: #ffb6c1; /* Light pink */
            color: #333;
            position: relative;
        }
        #message {
            display: none;
            font-size: 1.5em;
            color: #ff1493;
            margin-top: 50px;
        }
    </style>
</head>
<body>
    <h1>Hey Bombomcito, will you be my Valentine? 🐄💕</h1>
    <div class="cow">🐮 Moo! Be my Valentine? 🐮</div>
    <button id="yesBtn">Yes!</button>
    <button id="noBtn">No</button>
    <div id="message"></div>

    <script>
        const noBtn = document.getElementById('noBtn');
        const yesBtn = document.getElementById('yesBtn');
        const message = document.getElementById('message');
        let yesScale = 1; // Initial scale for Yes button

        // Function to move No button randomly
        function dodge() {
            const x = Math.random() * (window.innerWidth - noBtn.offsetWidth);
            const y = Math.random() * (window.innerHeight - noBtn.offsetHeight);
            noBtn.style.position = 'absolute';
            noBtn.style.left = `${x}px`;
            noBtn.style.top = `${y}px`;

            // Make Yes button bigger each time
            yesScale += 0.2;
            yesBtn.style.transform = `scale(${yesScale})`;
        }

        // Dodge on hover
        noBtn.addEventListener('mouseover', dodge);

        // Prevent clicking No by dodging on click attempt too
        noBtn.addEventListener('click', dodge);

        // On Yes click, show message
        yesBtn.addEventListener('click', () => {
            message.textContent = 'Yay! I knew you would say yes! 💖🐄 Happy Valentine\'s Day!';
            message.style.display = 'block';
            noBtn.style.display = 'none'; // Hide No button
        });
    </script>
</body>
</html>
