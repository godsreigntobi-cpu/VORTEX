# miss lovely 
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>For Alenosi 🌸</title>
    <script src="https://cdn.jsdelivr.net/npm/sweetalert2@11"></script>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            overflow: hidden;
            background: linear-gradient(135deg, #ff9ecb, #ffd6e8, #fff5f8);
        }

        .flowers span {
            position: absolute;
            font-size: 30px;
            animation: fall linear infinite;
            opacity: .8;
            user-select: none;
            pointer-events: none;
        }

        @keyframes fall {
            0% { transform: translateY(-10vh) rotate(0deg); }
            100% { transform: translateY(110vh) rotate(360deg); }
        }

        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.03); }
            100% { transform: scale(1); }
        }

        .card {
            background: rgba(255, 255, 255, 0.25);
            backdrop-filter: blur(12px);
            -webkit-backdrop-filter: blur(12px);
            padding: 40px;
            border-radius: 20px;
            text-align: center;
            color: #5c2d42;
            max-width: 500px;
            width: 90%;
            box-shadow: 0 8px 32px 0 rgba(255, 182, 193, 0.37);
            border: 1px solid rgba(255, 255, 255, 0.4);
            z-index: 10;
        }

        h1 {
            font-size: 2.2rem;
            margin-bottom: 20px;
            color: #d81b60;
            text-shadow: 1px 1px 2px rgba(255, 255, 255, 0.8);
            animation: pulse 3s ease-in-out infinite;
        }

        #text {
            font-size: 1.1rem;
            line-height: 1.8;
            min-height: 250px;
            white-space: pre-line;
            font-weight: 500;
        }

        button {
            margin-top: 20px;
            padding: 12px 28px;
            border: none;
            border-radius: 30px;
            background: #d81b60;
            color: white;
            font-size: 18px;
            font-weight: bold;
            cursor: pointer;
            transition: transform .3s ease, background .3s ease, opacity 1s ease;
            box-shadow: 0 4px 15px rgba(216, 27, 96, 0.3);
            opacity: 0; /* Hidden at first, fades in later */
            pointer-events: none;
        }

        button.show {
            opacity: 1;
            pointer-events: auto;
        }

        button:hover {
            transform: scale(1.08);
            background: #e91e63;
            box-shadow: 0 6px 20px rgba(216, 27, 96, 0.5);
        }
    </style>
</head>
<body>

    <div class="flowers" id="flowers"></div>

    <div class="card">
        <h1>🌸 To My Alenosi 🌸</h1>
        <p id="text"></p>
        <button id="loveBtn" onclick="showLove()">🌷 Tap Me 🌷</button>
    </div>

    <script>
        const message = `Dear Lovely,

Just wanted to say...

Well done for today's work. ❤️

No matter how tiring today was, I'm proud of you.

Keep shining because you make hard work look effortless.

You deserve every flower in every garden. 🌹🌸🌷

Rest well, Alenosi.

Keep smiling...

Someone out here admires you more than words can explain. 🤍`;

        let i = 0;
        function type() {
            if (i < message.length) {
                document.getElementById("text").innerHTML += message.charAt(i);
                i++;
                setTimeout(type, 45);
            } else {
                // Fade the button in when typing finishes
                document.getElementById("loveBtn").classList.add("show");
            }
        }

        window.onload = type;

        const emojis = ["🌸", "🌷", "🌹", "💐", "🌺", "🪷", "🌼"];
        const flowersContainer = document.getElementById("flowers");

        for (let i = 0; i < 60; i++) {
            let flower = document.createElement("span");
            flower.innerHTML = emojis[Math.floor(Math.random() * emojis.length)];
            flower.style.left = Math.random() * 100 + "vw";
            flower.style.animationDuration = (6 + Math.random() * 7) + "s";
            flower.style.fontSize = (18 + Math.random() * 22) + "px";
            flower.style.animationDelay = Math.random() * 5 + "s";
            flowersContainer.appendChild(flower);
        }

        function showLove() {
            Swal.fire({
                title: 'For Alenosi 🌸',
                text: "You're amazing, Lovely. Never stop being the beautiful soul you are. 🤍",
                background: '#fff5f8',
                color: '#5c2d42',
                confirmButtonColor: '#d81b60',
                confirmButtonText: 'Close ✨'
            });
        }
    </script>

</body>
</html>
