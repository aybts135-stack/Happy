#Happiest 20th Birthday 
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Siblings Forever</title>
    <style>
        body {
            margin: 0;
            height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            /* Dreamy Purple Sparkle Gradient */
            background: radial-gradient(circle at center, #8e44ad, #4b0082, #2c003e);
            background-size: 400% 400%;
            animation: glitterMove 10s ease infinite;
            overflow: hidden;
            color: white;
            text-align: center;
        }

        /* Animated Sparkling Background Effect */
        @keyframes glitterMove {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        .container {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            padding: 40px;
            border-radius: 20px;
            border: 1px solid rgba(255, 255, 255, 0.3);
            box-shadow: 0 0 20px rgba(231, 76, 190, 0.5);
            max-width: 80%;
        }

        h1 {
            font-size: 2.5rem;
            text-shadow: 0 0 10px #fff, 0 0 20px #e0aaff;
            margin-bottom: 20px;
        }

        .btn-container {
            display: flex;
            gap: 20px;
            justify-content: center;
            margin-top: 20px;
        }

        button {
            padding: 12px 30px;
            font-size: 1.1rem;
            border: none;
            border-radius: 50px;
            cursor: pointer;
            transition: transform 0.2s, box-shadow 0.2s;
            font-weight: bold;
        }

        .btn-yes { background-color: #ff85a2; color: white; }
        .btn-no { background-color: #a29bfe; color: white; }
        
        button:hover {
            transform: scale(1.1);
            box-shadow: 0 0 15px white;
        }

        .footer {
            margin-top: 30px;
            font-style: italic;
            font-size: 0.9rem;
            opacity: 0.8;
        }

        .hidden { display: none; }
    </style>
</head>
<body>

    <div class="container" id="mainCard">
        <div id="page1">
            <h1 id="mainText">Siblings Forever????</h1>
            <div class="btn-container">
                <button class="btn-yes" onclick="showBirthday()">Yes!</button>
                <button class="btn-no" onclick="askPretty()">No</button>
            </div>
        </div>

        <div id="page2" class="hidden">
            <h1>Happiest 20th birthday myyy darling sister💐💕</h1>
            <p>Are you enjoying this?</p>
            <div class="btn-container">
                <button class="btn-yes" onclick="showFinal()">Yes</button>
            </div>
        </div>

        <div id="page3" class="hidden">
            <h1>Me toooo sis🥳</h1>
            <div class="footer">
                With immense love from Akash and Tiya💖💐💕
            </div>
        </div>
    </div>

    <script>
        function askPretty() {
            document.getElementById('mainText').innerText = "Prweeeeety pls💖";
        }

        function showBirthday() {
            document.getElementById('page1').classList.add('hidden');
            document.getElementById('page2').classList.remove('hidden');
        }

        function showFinal() {
            document.getElementById('page2').classList.add('hidden');
            document.getElementById('page3').classList.remove('hidden');
        }
    </script>

</body>
</html>
