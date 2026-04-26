#Happiest 20th Birthday 
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>For My Favorite Sister</title>
    <style>
        body, html {
            margin: 0;
            padding: 0;
            width: 100%;
            height: 100%;
            overflow: hidden;
            font-family: 'Comic Sans MS', 'cursive', sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            background: radial-gradient(circle at center, #6a0dad, #2c003e);
        }

        /* Sparkle Canvas Overlay */
        #sparkleCanvas {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none; /* Allows clicking through to buttons */
            z-index: 1;
        }

        .container {
            position: relative;
            z-index: 10;
            background: rgba(255, 255, 255, 0.15);
            backdrop-filter: blur(15px);
            padding: 50px;
            border-radius: 30px;
            border: 2px solid rgba(255, 255, 255, 0.4);
            box-shadow: 0 0 30px rgba(230, 150, 255, 0.5);
            text-align: center;
            color: white;
            max-width: 450px;
        }

        h1 {
            font-size: 2.2rem;
            text-shadow: 0 0 15px #e0aaff, 0 0 30px #8e44ad;
            margin-bottom: 30px;
        }

        .btn-container {
            display: flex;
            gap: 15px;
            justify-content: center;
        }

        button {
            padding: 15px 35px;
            font-size: 1.2rem;
            border: none;
            border-radius: 50px;
            cursor: pointer;
            transition: all 0.3s ease;
            font-weight: bold;
            box-shadow: 0 4px 15px rgba(0,0,0,0.3);
        }

        .btn-yes { background: linear-gradient(45deg, #ff85a2, #ff0055); color: white; }
        .btn-no { background: rgba(255, 255, 255, 0.2); color: white; border: 1px solid white; }
        
        button:hover {
            transform: translateY(-5px) scale(1.05);
            box-shadow: 0 0 20px #fff;
        }

        .footer {
            margin-top: 30px;
            font-size: 1.1rem;
            line-height: 1.6;
            animation: fadeIn 2s ease;
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        .hidden { display: none; }
    </style>
</head>
<body>

    <canvas id="sparkleCanvas"></canvas>

    <div class="container">
        <div id="step1">
            <h1 id="questionText">siblings forever????</h1>
            <div class="btn-container">
                <button class="btn-yes" onclick="nextStep(2)">Yes!</button>
                <button class="btn-no" onclick="bePretty()">no</button>
            </div>
        </div>

        <div id="step2" class="hidden">
            <h1>happiest 20th birthday myyy darling sister💐💕</h1>
            <p style="font-size: 1.3rem;">Are you enjoying this?</p>
            <div class="btn-container">
                <button class="btn-yes" onclick="nextStep(3)">Yes!</button>
            </div>
        </div>

        <div id="step3" class="hidden">
            <h1>me toooo sis🥳</h1>
            <div class="footer">
                with immense love from <br>
                <strong>Akash and Tiya💖💐💕</strong>
            </div>
        </div>
    </div>

    <script>
        const canvas = document.getElementById('sparkleCanvas');
        const ctx = canvas.getContext('2d');
        let particles = [];

        function resize() {
            canvas.width = window.innerWidth;
            canvas.height = window.innerHeight;
        }

        window.addEventListener('resize', resize);
        resize();

        // Sparkle Particle Class
        class Particle {
            constructor() {
                this.reset();
            }
            reset() {
                this.x = Math.random() * canvas.width;
                this.y = Math.random() * canvas.height;
                this.size = Math.random() * 3 + 1;
                this.speedX = Math.random() * 0.5 - 0.25;
                this.speedY = Math.random() * 0.5 - 0.25;
                this.opacity = Math.random();
                this.blinkSpeed = Math.random() * 0.02 + 0.01;
            }
            update() {
                this.x += this.speedX;
                this.y += this.speedY;
                this.opacity += this.blinkSpeed;
                if (this.opacity > 1 || this.opacity < 0) this.blinkSpeed *= -1;
                
                if (this.x < 0 || this.x > canvas.width || this.y < 0 || this.y > canvas.height) {
                    this.reset();
                }
            }
            draw() {
                ctx.fillStyle = `rgba(255, 255, 255, ${this.opacity})`;
                ctx.shadowBlur = 10;
                ctx.shadowColor = "white";
                ctx.beginPath();
                ctx.arc(this.x, this.y, this.size, 0, Math.PI * 2);
                ctx.fill();
            }
        }

        function init() {
            for (let i = 0; i < 150; i++) {
                particles.push(new Particle());
            }
        }

        function animate() {
            ctx.clearRect(0, 0, canvas.width, canvas.height);
            particles.forEach(p => {
                p.update();
                p.draw();
            });
            requestAnimationFrame(animate);
        }

        init();
        animate();

        // Logic Functions
        function bePretty() {
            document.getElementById('questionText').innerHTML = "prweeeeety pls💖";
            document.getElementById('questionText').style.fontSize = "2.5rem";
        }

        function nextStep(step) {
            document.getElementById('step1').classList.add('hidden');
            document.getElementById('step2').classList.add('hidden');
            document.getElementById('step3').classList.add('hidden');
            document.getElementById('step' + step).classList.remove('hidden');
        }
    </script>
</body>
</html>
