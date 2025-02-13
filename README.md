# ToYunWatty
this is one and only accessible by YunWatty
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Will You Be My Valentine?</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            background-color: pink;
            margin: 0;
            padding: 50px;
            overflow: hidden;
        }
        .container {
            background: white;
            padding: 20px;
            border-radius: 10px;
            display: inline-block;
            box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.2);
            position: relative;
            z-index: 2;
        }
        h1 {
            color: red;
        }
        .buttons {
            margin-top: 20px;
        }
        button {
            font-size: 18px;
            padding: 10px 20px;
            margin: 10px;
            border: none;
            cursor: pointer;
            border-radius: 5px;
            transition: all 0.3s ease-in-out;
        }
        .yes {
            background-color: red;
            color: white;
        }
        .no {
            background-color: gray;
            color: white;
        }
        .heart {
            position: absolute;
            color: red;
            font-size: 24px;
            animation: floatUp 2s linear infinite;
        }
        @keyframes floatUp {
            0% { transform: translateY(0); opacity: 1; }
            100% { transform: translateY(-200px); opacity: 0; }
        }
    </style>
</head>
<body>

    <div class="container">
        <h1>Will you be my Valentine? 💖</h1>
        <div class="buttons">
            <button class="yes" onclick="goToChocolatePage()">Yes</button>
            <button class="no" onclick="makeYesBigger()">No</button>
        </div>
    </div>

    <script>
        let yesButton = document.querySelector(".yes");
        let yesSize = 18; // Initial font size

        function goToChocolatePage() {
            createHearts(); // Show hearts
            setTimeout(() => {
                window.location.href = "chocolate.html"; // Redirect after hearts
            }, 2000);
        }

        function makeYesBigger() {
            yesSize += 10; // Increase font size
            yesButton.style.fontSize = yesSize + "px";
            yesButton.style.padding = (yesSize / 2) + "px"; // Adjust padding
        }

        function createHearts() {
            for (let i = 0; i < 10; i++) {
                let heart = document.createElement("div");
                heart.innerHTML = "❤️";
                heart.classList.add("heart");
                heart.style.left = Math.random() * 100 + "vw";
                heart.style.bottom = "0px";
                heart.style.fontSize = Math.random() * 30 + 20 + "px";
                heart.style.animationDuration = Math.random() * 2 + 2 + "s";
                document.body.appendChild(heart);

                setTimeout(() => {
                    heart.remove();
                }, 2000);
            }
        }
    </script>

</body>
</html>
