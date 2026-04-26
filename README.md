#Happiest 20th Birthday 
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>For My Universe - Sister</title>
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
            
            /* -- THE UNIVERSE BACKGROUND -- */
            /* Layer 1: Base deep space gradient */
            /* Layer 2: Cosmic Nebula clouds (moving) */
            /* Layer 3: Distant fixed starfield */
            background-color: #050010;
            background-image: 
                radial-gradient(circle at 20% 30%, rgba(76, 0, 130, 0.6) 0%, transparent 50%),
                radial-gradient(circle at 80% 70%, rgba(218, 112, 214, 0.4) 0%, transparent 50%),
                radial-gradient(circle at 50% 50%, rgba(25, 0, 80, 0.8) 0%, transparent 80%),
                url('data:image/svg+xml,%3Csvg xmlns="http://www.w3.org/2000/svg" width="400" height="400" viewBox="0 0 800 800"%3E%3Cg fill="none" stroke="%23FFFFFF" stroke-opacity="0.1"%3E%3Ccircle cx="400" cy="400" r="1"/%3E%3Ccircle cx="100" cy="200" r="1"/%3E%3Ccircle cx="300" cy="600" r="1"/%3E%3Ccircle cx="700" cy="150" r="1"/%3E%3Ccircle cx="600" cy="500" r="1"/%3E%3Ccircle cx="200" cy="700" r="1"/%3E%3C/g%3E%3C/svg%3E');
            background-size: cover, cover, cover, 200px 200px; /* Small tiled stars */
            animation: spaceDrift 20s linear infinite;
        }

        /* Moving the cosmic clouds slowely */
        @keyframes spaceDrift {
            0% { background-position: 0% 0%, 0% 0%, 0% 0%, 0% 0%; }
            100% { background-position: 10% 5%, -10% -5%, 0% 0%, 100px 100px; }
        }

        /* Sparkle Canvas Overlay (Twinkling stars) */
        #sparkleCanvas {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 1;
        }

        /* The Content Card */
        .container {
            position: relative;
            z-index: 10;
            background: rgba(20, 0, 40, 0.4); /* Darker transperency */
            backdrop-filter: blur(20px);
            padding: 50px;
            border-radius: 30px;
            border: 2px solid rgba(230, 150, 255, 0.3);
            box-shadow: 0 0 50px rgba(142, 68, 173, 0.6);
            text-align: center;
            color: white;
            max-width: 450px;
            transform-style: preserve-3d;
            perspective: 1000px;
        }

        h1 {
            font-size: 2.2rem;
            /* Glowing cosmic text */
            text-shadow: 0 0 10px #e0aaff, 0 0 20px #8e44ad, 0 0 40px #ff00de;
            margin-bottom: 30px;
            animation: textPulse 2s infinite alternate;
        }

        @keyframes textPulse {
            from { transform: scale(1); text-shadow: 0 0 10px #e0aaff, 0 0 20px #8e44ad; }
            to { transform: scale(1.02); text-shadow: 0 0 15px #e0aaff, 0 0 30px #8e44ad, 0 0 50px #ff00de; }
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
            text-transform: uppercase;
            letter-spacing: 1px;
            box-shadow: 0 4px 15px rgba(0,0,0,0.5);
        }

        /* Cosmic Magenta Button */
        .btn-yes { 
            background: linear-gradient(45deg, #ff00de, #8e44ad, #ff00de); 
            background-size: 200% auto;
            color: white; 
            animation: buttonGlow 3s infinite;
        }

        /* Simple Space Outline Button */
        .btn-no { 
            background: rgba(255, 255, 255, 0.1); 
            color: white; 
            border: 2px solid rgba(255, 255, 255, 0.5); 
        }
        
        button:hover {
            transform: translateY(-5px) scale(1.1);
            box-shadow: 0 0 30px #ff00de;
        }

        @keyframes buttonGlow {
            0% { background-position: 0% 50%; box-shadow: 0 0 10px #ff00de; }
            50% { background-position: 100% 50%; box-shadow: 0 0 25px #8e44ad; }
            100% { background-position: 0% 50%; box-shadow: 0 0 10px #ff00de; }
        }

        .footer {
            margin-top: 40px;
            font-size: 1.1rem;
            line-height: 1.8;
            opacity: 0;
            animation: fadeIn 3s forwards 0.5s;
        }

        @keyframes fadeIn { to { opacity: 1; } }

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
            <p style="font-size: 1.3rem; text-shadow: 0 0 5px white;">Are you enjoying this?</p>
            <div class="btn-container">
                <button class="btn-yes" onclick="nextStep(3)">Yes!</button>
            </div>
        </div>

        <div id="step3" class="hidden">
            <h1>me toooo sis🥳</h1>
            <div class="footer">
                with immense love from the cosmos<br>
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

        // Universe Particle Class (Stars & Sparkles)
        class Particle {
            constructor() {
                this.reset();
            }
            reset() {
                this.x = Math.random() * canvas.width;
                this.y = Math.random() * canvas.height;
                // Size variety: mostly tiny stars, a few large "flares"
                this.size = Math.random() < 0.98 ? Math.random() * 2 + 0.5 : Math.random() * 5 + 2; 
                
                // Slow cosmic drift
                this.speedX = Math.random() * 0.1 - 0.05;
                this.speedY = Math.random() * 0.1 - 0.05;
                
                this.opacity = Math.random();
                // Random blinking speeds
                this.blinkSpeed = Math.random() * 0.015 + 0.005;
                // Magenta, Purple, or White sparkles
                const colors = ["#FFFFFF", "#ffe0ff", "#e0aaff", "#ff00de"];
                this.color = colors[Math.floor(Math.random() * colors.length)];
            }
            update() {
                this.x += this.speedX;
                this.y += this.speedY;
                
                // Blink logic
                this.opacity += this.blinkSpeed;
                if (this.opacity > 1 || this.opacity < 0) this.blinkSpeed *= -1;
                
                // Wrap around screen
                if (this.x < 0) this.x = canvas.width;
                if (this.x > canvas.width) this.x = 0;
                if (this.y < 0) this.y = canvas.height;
                if (this.y > canvas.height) this.y = 0;
            }
            draw() {
                ctx.save();
                ctx.fillStyle = this.color;
                ctx.globalAlpha = Math.abs(this.opacity); // Ensure no negative alpha
                
                // Add "glow" shadow to larger particles
                if (this.size > 2) {
                    ctx.shadowBlur = this.size * 2;
                    ctx.shadowColor = this.color;
                }
                
                ctx.beginPath();
                // Randomly draw cross shape for "shimmer" or circle for star
                if (this.size > 4 && Math.random() > 0.5) {
                   // Draw a basic star flare shape
                   ctx.moveTo(this.x, this.y - this.size);
                   ctx.lineTo(this.x, this.y + this.size);
                   ctx.moveTo(this.x - this.size, this.y);
                   ctx.lineTo(this.x + this.size, this.y);
                   ctx.lineWidth = 0.5;
                   ctx.strokeStyle = this.color;
                   ctx.stroke();
                } else {
                    ctx.arc(this.x, this.y, this.size, 0, Math.PI * 2);
                    ctx.fill();
                }
                ctx.restore();
            }
        }

        function init() {
            // High number of particles for "universe" density
            for (let i = 0; i < 350; i++) {
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

        // Interactivity Logic
        function bePretty() {
            const txt = document.getElementById('questionText');
            txt.innerHTML = "prweeeeety pls💖";
            txt.style.fontSize = "2.8rem";
            txt.style.color = "#ff85a2"; // Change color on no
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
