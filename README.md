<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Pilih Jawaban</title>
    <style>
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            font-family: Arial, sans-serif;
            background-color: #f0f0f0;
        }
        .container {
            text-align: center;
        }
        #response {
            margin-top: 20px;
            font-size: 24px;
            color: #333;
        }
        button {
            padding: 10px 20px;
            font-size: 18px;
            margin: 10px;
            cursor: pointer;
            border: none;
            border-radius: 5px;
            background-color: #6200ea;
            color: white;
            transition: background-color 0.3s;
        }
        button:hover {
            background-color: #3700b3;
        }
        .moving-button {
            position: absolute;
            transition: all 0.3s ease;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Apakah kamu mau tahu sesuatu?</h1>
        <button id="yesButton">Yes</button>
        <button id="noButton" class="moving-button">No</button>
        <div id="response"></div>
    </div>

    <script>
        const yesButton = document.getElementById("yesButton");
        const noButton = document.getElementById("noButton");
        const response = document.getElementById("response");

        yesButton.addEventListener("click", function() {
            response.innerText = "Kamu adalah wanita tercantik ku";
            noButton.style.display = "none"; // Menghilangkan tombol No
        });

        noButton.addEventListener("click", function() {
            moveButton();
        });

        function moveButton() {
            const windowWidth = window.innerWidth - noButton.offsetWidth;
            const windowHeight = window.innerHeight - noButton.offsetHeight;
            const randomX = Math.floor(Math.random() * windowWidth);
            const randomY = Math.floor(Math.random() * windowHeight);
            noButton.style.left = randomX + "px";
            noButton.style.top = randomY + "px";
        }
    </script>
</body>
</html>
