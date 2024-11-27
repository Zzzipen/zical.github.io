<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Pesan Cinta</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            background-color: #f0f0f0;
        }
        .container {
            text-align: center;
        }
        .message {
            font-size: 24px;
            margin-bottom: 20px;
        }
        button {
            padding: 10px 20px;
            font-size: 16px;
            cursor: pointer;
            margin-top: 10px;
        }
        .options {
            display: none;
            margin-top: 20px;
        }
        .option-btn {
            margin: 10px;
            padding: 10px 20px;
            font-size: 16px;
        }
        .move-button {
            position: relative;
            animation: move 2s infinite;
        }
        @keyframes move {
            0% { left: 0; top: 0; }
            25% { left: 50px; top: 0; }
            50% { left: 0; top: 50px; }
            75% { left: -50px; top: 0; }
            100% { left: 0; top: -50px; }
        }
    </style>
</head>
<body>

<div class="container">
    <div class="message" id="message">Halo</div>
    <button onclick="nextMessage()">Next</button>

    <div class="options" id="options">
        <div class="message" id="question">Sayang mau maafin aku?</div>
        <button class="option-btn" onclick="sayangYa()">Ya</button>
        <button class="option-btn move-button" id="noBtn" onclick="sayangTidak()">Tidak</button>
    </div>
</div>

<script>
    const messages = [
        "Aku pacarmu Venoo!",
        "Sayang masih marah?",
        "Sayang masih sedih?",
        "Sayang aku minta maaf ya :(",
        "Maafin aku kelakuanku udah salah selama ini, bikin kamu sakit hati",
        "Aku nyesel banget bikin kamu gini :("
    ];

    let currentMessageIndex = 0;

    function nextMessage() {
        if (currentMessageIndex < messages.length) {
            document.getElementById('message').textContent = messages[currentMessageIndex];
            currentMessageIndex++;
        } else {
            document.getElementById('options').style.display = 'block';
            document.querySelector('button').style.display = 'none';
        }
    }

    function sayangYa() {
        document.getElementById('message').textContent = "I LOVE YOU SAYANG!!";
        document.getElementById('question').textContent = "Sayang angkat call ku yaaa?";
        document.getElementById('options').style.display = 'none';
    }

    function sayangTidak() {
        const noBtn = document.getElementById('noBtn');
        const randomLeft = Math.floor(Math.random() * 200) - 100;  // Random horizontal movement
        const randomTop = Math.floor(Math.random() * 200) - 100;   // Random vertical movement
        noBtn.style.left = randomLeft + "px";
        noBtn.style.top = randomTop + "px";
    }
</script>

</body>
</html>
