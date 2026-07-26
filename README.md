<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>¡Feliz Cumpleaños, Mi Amor! ❤️</title>
    <style>
        /* RESET & BASE STYLES */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Georgia', serif;
            background: #060713;
            color: #f1f5f9;
            min-height: 100vh;
            overflow-x: hidden;
            position: relative;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: space-between;
        }

        /* CANVAS BACKGROUND FOR STARS, BUTTONS, FIREFLIES, LEAVES, FOG, BLACK CAT */
        #bg-canvas {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 1;
        }

        /* OTHER WORLD MOON */
        .moon-container {
            position: fixed;
            top: 35px;
            right: 7%;
            width: 130px;
            height: 130px;
            border-radius: 50%;
            background: radial-gradient(circle at 35% 35%, #fffdf0 0%, #cbd5e1 60%, #94a3b8 100%);
            box-shadow: 0 0 35px rgba(255, 253, 240, 0.45),
                        0 0 75px rgba(250, 204, 21, 0.25),
                        0 0 110px rgba(168, 85, 247, 0.2);
            z-index: 1;
            animation: moonGlow 5s ease-in-out infinite alternate;
            pointer-events: none;
        }

        /* PINK PALACE FOREST SILHOUETTE AT BOTTOM */
        .forest-silhouette {
            position: fixed;
            bottom: 0;
            left: 0;
            width: 100%;
            height: 150px;
            background: radial-gradient(ellipse at bottom, rgba(15, 23, 42, 0.6) 0%, transparent 85%);
            pointer-events: none;
            z-index: 2;
        }

        /* CONTAINER STRUCTURE */
        .container {
            position: relative;
            z-index: 3;
            width: 100%;
            max-width: 850px;
            padding: 55px 20px 40px 20px;
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        /* HERO HEADER */
        header {
            text-align: center;
            margin-bottom: 35px;
            animation: fadeInDown 1.8s ease-out;
        }

        h1 {
            font-size: 2.8rem;
            font-weight: 700;
            background: linear-gradient(135deg, #facc15 0%, #38bdf8 50%, #c084fc 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            text-shadow: 0 0 30px rgba(250, 204, 21, 0.35);
            margin-bottom: 16px;
            line-height: 1.25;
            letter-spacing: 0.8px;
        }

        .subtitle-container {
            min-height: 32px;
            display: flex;
            justify-content: center;
            align-items: center;
        }

        .typewriter {
            font-size: 1.15rem;
            color: #fde047;
            border-right: 2px solid #facc15;
            white-space: nowrap;
            overflow: hidden;
            letter-spacing: 1.5px;
            animation: blinkCursor 0.75s step-end infinite;
            font-style: italic;
            font-family: 'Segoe UI', sans-serif;
            text-shadow: 0 0 10px rgba(250, 204, 21, 0.5);
        }

        /* CORALINE GLASSMORPHISM CARD */
        .card {
            background: rgba(10, 15, 30, 0.65);
            backdrop-filter: blur(18px);
            -webkit-backdrop-filter: blur(18px);
            border: 1px solid rgba(250, 204, 21, 0.35);
            border-radius: 24px;
            padding: 45px 40px;
            box-shadow: 0 20px 50px rgba(0, 0, 0, 0.8), 
                        0 0 30px rgba(168, 85, 247, 0.15),
                        inset 0 0 25px rgba(250, 204, 21, 0.08);
            margin-bottom: 40px;
            width: 100%;
            animation: fadeInUp 2s ease-out;
            transition: transform 0.4s ease, box-shadow 0.4s ease, border-color 0.4s ease;
            position: relative;
        }

        .card::before {
            content: '🗝️';
            position: absolute;
            top: 15px;
            left: 20px;
            font-size: 1.3rem;
            opacity: 0.8;
        }

        .card::after {
            content: '🧵';
            position: absolute;
            bottom: 15px;
            right: 20px;
            font-size: 1.3rem;
            opacity: 0.8;
        }

        .card:hover {
            transform: translateY(-6px);
            border-color: rgba(250, 204, 21, 0.7);
            box-shadow: 0 25px 65px rgba(0, 0, 0, 0.9), 
                        0 0 45px rgba(250, 204, 21, 0.3),
                        inset 0 0 30px rgba(250, 204, 21, 0.15);
        }

        .card p {
            font-family: 'Segoe UI', 'Georgia', serif;
            font-size: 1.12rem;
            line-height: 1.85;
            color: #f1f5f9;
            margin-bottom: 20px;
            font-weight: 300;
            letter-spacing: 0.4px;
            text-align: justify;
        }

        .card p:last-child {
            margin-bottom: 0;
        }

        /* SEÇÃO DOS BOTÕES LADO A LADO */
        .interactive-section {
            margin-top: 35px;
            text-align: center;
            border-top: 1px dashed rgba(250, 204, 21, 0.3);
            padding-top: 25px;
        }

        .question-title {
            font-size: 1.25rem;
            color: #facc15;
            font-weight: 600;
            margin-bottom: 20px;
            text-shadow: 0 0 10px rgba(250, 204, 21, 0.4);
        }

        .btn-container {
            position: relative;
            display: flex;
            flex-direction: row; /* Força os botões a ficarem lado a lado */
            justify-content: center;
            align-items: center;
            gap: 25px;
            min-height: 60px;
            width: 100%;
        }

        .btn-action {
            padding: 12px 35px;
            font-size: 1.1rem;
            font-weight: bold;
            font-family: 'Segoe UI', sans-serif;
            border-radius: 30px;
            cursor: pointer;
            border: 2px solid #facc15;
            box-shadow: 0 4px 15px rgba(0,0,0,0.5);
        }

        .btn-sim {
            background-color: #4b0082;
            color: #facc15;
            transition: transform 0.2s, background-color 0.2s;
            z-index: 2;
        }

        .btn-sim:hover {
            background-color: #6a0dad;
            transform: scale(1.08);
            box-shadow: 0 0 20px rgba(250, 204, 21, 0.6);
        }

        .btn-nao {
            background-color: #1e293b;
            color: #94a3b8;
            border-color: #475569;
            position: relative; /* Começa alinhado ao lado do SIM */
            z-index: 2;
        }

        /* VIDEO BUTTON SECTION */
        .video-section {
            margin-bottom: 45px;
            text-align: center;
            animation: fadeIn 2.2s ease-out;
        }

        .btn-video {
            display: inline-flex;
            align-items: center;
            gap: 12px;
            padding: 18px 40px;
            font-size: 1.15rem;
            font-weight: 600;
            font-family: 'Segoe UI', sans-serif;
            color: #0d1117;
            background: linear-gradient(135deg, #facc15 0%, #eab308 50%, #ca8a04 100%);
            border: 1px solid rgba(250, 204, 21, 0.8);
            border-radius: 50px;
            text-decoration: none;
            box-shadow: 0 10px 30px rgba(250, 204, 21, 0.4),
                        0 0 20px rgba(168, 85, 247, 0.3);
            transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            cursor: pointer;
            position: relative;
            overflow: hidden;
        }

        .btn-video::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.45), transparent);
            transition: left 0.75s;
        }

        .btn-video:hover::before {
            left: 100%;
        }

        .btn-video:hover {
            transform: scale(1.06) translateY(-3px);
            box-shadow: 0 15px 40px rgba(250, 204, 21, 0.7),
                        0 0 35px rgba(56, 189, 248, 0.5);
        }

        /* SPOTIFY CONTAINER */
        .spotify-section {
            width: 100%;
            margin-bottom: 45px;
            display: flex;
            justify-content: center;
            animation: fadeIn 2.4s ease-out;
        }

        .spotify-card {
            width: 100%;
            max-width: 100%;
            border-radius: 22px;
            overflow: hidden;
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.8),
                        0 0 25px rgba(168, 85, 247, 0.25);
            background: rgba(15, 23, 42, 0.6);
            backdrop-filter: blur(12px);
            border: 1px solid rgba(250, 204, 21, 0.3);
            padding: 8px;
        }

        .spotify-card iframe {
            border-radius: 14px;
            width: 100%;
            height: 380px;
            border: none;
        }

        /* FOOTER */
        footer {
            position: relative;
            z-index: 3;
            width: 100%;
            padding: 28px 20px;
            text-align: center;
            background: rgba(6, 7, 19, 0.85);
            backdrop-filter: blur(12px);
            border-top: 1px solid rgba(250, 204, 21, 0.2);
        }

        footer p {
            font-size: 1.05rem;
            color: #94a3b8;
            letter-spacing: 0.8px;
            font-weight: 300;
            font-family: 'Segoe UI', sans-serif;
        }

        footer span {
            color: #facc15;
            text-shadow: 0 0 10px rgba(250, 204, 21, 0.6);
        }

        /* KEYFRAME ANIMATIONS */
        @keyframes moonGlow {
            0% {
                box-shadow: 0 0 30px rgba(255, 253, 240, 0.35),
                            0 0 60px rgba(250, 204, 21, 0.2);
            }
            100% {
                box-shadow: 0 0 50px rgba(255, 253, 240, 0.55),
                            0 0 90px rgba(168, 85, 247, 0.35);
            }
        }

        @keyframes fadeInDown {
            from {
                opacity: 0;
                transform: translateY(-35px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(45px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        @keyframes blinkCursor {
            from, to { border-color: transparent; }
            50% { border-color: #facc15; }
        }

        /* RESPONSIVE DESIGN */
        @media (max-width: 768px) {
            .moon-container {
                width: 85px;
                height: 85px;
                top: 20px;
                right: 5%;
            }

            h1 {
                font-size: 2.1rem;
            }

            .typewriter {
                font-size: 0.98rem;
            }

            .card {
                padding: 30px 22px;
                border-radius: 20px;
            }

            .card p {
                font-size: 1rem;
                line-height: 1.75;
                text-align: left;
            }

            .btn-video {
                padding: 15px 30px;
                font-size: 1rem;
            }

            .spotify-card iframe {
                height: 350px;
            }
        }

        @media (max-width: 480px) {
            h1 {
                font-size: 1.75rem;
            }

            .typewriter {
                font-size: 0.88rem;
            }

            .card {
                padding: 24px 18px;
            }

            .btn-video {
                width: 100%;
                justify-content: center;
            }
        }
    </style>

    <!-- BIBLIOTECA PARA EFEITO DE CONFETI / FESTIM -->
    <script src="https://cdn.jsdelivr.net/npm/canvas-confetti@1.6.0/dist/confetti.browser.min.js"></script>
</head>
<body>

    <canvas id="bg-canvas"></canvas>
    
    <div class="moon-container"></div>
    <div class="forest-silhouette"></div>

    <div class="container">
        <header>
            <h1>¡Feliz Cumpleaños, Mi Amor! ❤️</h1>
            <div class="subtitle-container">
                <span id="typewriter" class="typewriter"></span>
            </div>
        </header>

        <section class="card">
            <p>Hola, mi amor. ❤️</p>
            <p>Conocerte ha sido la mejor cosa que me ha pasado en la vida. Nunca voy a olvidar la primera vez que te vi. En ese momento pensé para mí mismo: "Algún día quiero estar con ella."</p>
            <p>Con el tiempo, ese día llegó. Nos fuimos acercando poco a poco y, desde entonces, hemos estado juntos compartiendo momentos inolvidables.</p>
            <p>Hoy, en tu cumpleaños, quiero que sepas lo especial que eres para mí. Gracias por tu cariño, por tu compañía y por hacer mi vida mucho más feliz.</p>
            <p>Espero que este nuevo año de vida esté lleno de alegría, salud, sueños cumplidos y mucho amor.</p>
            <p>Siempre estaré a tu lado para apoyarte, cuidarte y seguir construyendo nuestra historia juntos.</p>
            <p>Espero que te guste este pequeño detalle. Lo hice con todo mi cariño para ti.</p>
            <p>También espero que te guste este pequeño ramo de girasoles. 🌻 Sé cuánto te gustan y quise regalártelos como un símbolo de la alegría y la luz que traes a mi vida.</p>
            <p>Y, por cierto... ¿Recuerdas que me dijiste que en tu próximo cumpleaños saldrías conmigo? Bueno... ese día por fin llegó. ❤️ Espero que podamos crear muchos recuerdos bonitos juntos y seguir escribiendo nuestra historia.</p>

            <!-- INTERACTIVE BUTTON SECTION (BOTÕES LADO A LADO) -->
            <div class="interactive-section">
                <p class="question-title">¿Aceptas abrir la pequeña puerta conmigo hoy? 🗝️✨</p>
                <div class="btn-container">
                    <button class="btn-action btn-sim" onclick="respostaSim()">¡SÍ! ❤️</button>
                    <button class="btn-action btn-nao" id="btnNao" onmouseover="desviar()" ontouchstart="desviar()">NO</button>
                </div>
            </div>
        </section>

        <section class="video-section">
            <a href="https://www.instagram.com/reel/DbOpWbKi3Ri/?igsh=MXhlOG81eGs0aWlyMw==" target="_blank" rel="noopener noreferrer" class="btn-video">
                🎥 Mira este video ❤️
            </a>
        </section>

        <section class="spotify-section">
            <div class="spotify-card">
                <iframe src="https://open.spotify.com/embed/playlist/2u7hAgL7NegOZq3F2k0Ehm?utm_source=generator&theme=0" allowfullscreen="" allow="autoplay; clipboard-write; encrypted-media; fullscreen; picture-in-picture" loading="lazy"></iframe>
            </div>
        </section>
    </div>

    <footer>
        <p>A través de la pequeña puerta y más allá de las estrellas... <span>🗝️ 🧵 ❤️</span></p>
    </footer>

    <script>
        // TYPEWRITER EFFECT
        const textToType = "Detrás de la puerta secreta, un regalo hecho especialmente para ti... 🗝️✨";
        const typewriterElement = document.getElementById("typewriter");
        let charIndex = 0;

        function typeEffect() {
            if (charIndex < textToType.length) {
                typewriterElement.textContent += textToType.charAt(charIndex);
                charIndex++;
                setTimeout(typeEffect, 65);
            }
        }

        window.addEventListener("DOMContentLoaded", () => {
            setTimeout(typeEffect, 900);
        });

        // BOTÃO FUJÃO (APENAS MOVE O BOTÃO NO E NINGUÉM DISPARA FESTIM AQUI)
        function desviar() {
            const btn = document.getElementById("btnNao");

            // Define os limites da tela para fuga
            const larguraJanela = window.innerWidth - btn.offsetWidth - 20;
            const alturaJanela = window.innerHeight - btn.offsetHeight - 20;

            const novaPosicaoX = Math.max(10, Math.floor(Math.random() * larguraJanela));
            const novaPosicaoY = Math.max(10, Math.floor(Math.random() * alturaJanela));

            // Muda para posicionamento fixo para conseguir voar para qualquer canto
            btn.style.position = "fixed";
            btn.style.left = `${novaPosicaoX}px`;
            btn.style.top = `${novaPosicaoY}px`;
        }

        // APENAS AQUI NO BOTÃO SIM O FESTIM É DISPARADO
        function respostaSim() {
            // 1. Explosão de festim/confeti
            confetti({
                particleCount: 120,
                spread: 80,
                origin: { y: 0.6 }
            });

            // Efeito secundário
            setTimeout(() => {
                confetti({ particleCount: 50, angle: 60, spread: 55, origin: { x: 0 } });
                confetti({ particleCount: 50, angle: 120, spread: 55, origin: { x: 1 } });
            }, 250);

            // 2. Abre o seu WhatsApp após 1,5s com a mensagem pronta
            setTimeout(() => {
                const meuNumero = "5592994205721";
                const mensagem = encodeURIComponent("¡SÍ! Acepto abrir la pequeña puerta contigo hoy... 🗝️❤️");
                window.location.href = `https://wa.me/${meuNumero}?text=${mensagem}`;
            }, 1500);
        }

        // CANVAS ANIMATIONS: BUTTON STARS, REGULAR STARS, FIREFLIES, LEAVES, FOG, FLOWERS, CORALINE'S CAT
        const canvas = document.getElementById("bg-canvas");
        const ctx = canvas.getContext("2d");

        let width, height;

        function resizeCanvas() {
            width = canvas.width = window.innerWidth;
            height = canvas.height = window.innerHeight;
        }

        window.addEventListener("resize", resizeCanvas);
        resizeCanvas();

        // REGULAR STAR CLASS
        class Star {
            constructor() { this.reset(); }
            reset() {
                this.x = Math.random() * width;
                this.y = Math.random() * height * 0.8;
                this.size = Math.random() * 1.5 + 0.4;
                this.alpha = Math.random();
                this.speed = Math.random() * 0.012 + 0.004;
                this.increasing = Math.random() > 0.5;
            }
            update() {
                if (this.increasing) {
                    this.alpha += this.speed;
                    if (this.alpha >= 1) this.increasing = false;
                } else {
                    this.alpha -= this.speed;
                    if (this.alpha <= 0.15) this.increasing = true;
                }
            }
            draw() {
                ctx.save();
                ctx.globalAlpha = this.alpha;
                ctx.fillStyle = "#ffffff";
                ctx.beginPath();
                ctx.arc(this.x, this.y, this.size, 0, Math.PI * 2);
                ctx.fill();
                ctx.restore();
            }
        }

        // BUTTON STAR CLASS (BUTTON-SHAPED STARS FOR CORALINE THEME)
        class ButtonStar {
            constructor() { this.reset(); }
            reset() {
                this.x = Math.random() * width;
                this.y = Math.random() * height * 0.75;
                this.size = Math.random() * 6 + 6; // Button size 6px to 12px
                this.alpha = Math.random() * 0.6 + 0.3;
                this.rotation = Math.random() * Math.PI * 2;
                this.rotSpeed = (Math.random() - 0.5) * 0.01;
            }
            update() {
                this.rotation += this.rotSpeed;
                this.alpha += Math.sin(Date.now() * 0.002) * 0.005;
            }
            draw() {
                ctx.save();
                ctx.translate(this.x, this.y);
                ctx.rotate(this.rotation);
                ctx.globalAlpha = Math.max(0.2, Math.min(0.8, this.alpha));

                const r = this.size / 2;

                // Outer Button
                ctx.fillStyle = "#0f172a";
                ctx.strokeStyle = "#facc15";
                ctx.lineWidth = 1;
                ctx.beginPath();
                ctx.arc(0, 0, r, 0, Math.PI * 2);
                ctx.fill();
                ctx.stroke();

                // Inner Ring
                ctx.strokeStyle = "rgba(250, 204, 21, 0.5)";
                ctx.beginPath();
                ctx.arc(0, 0, r * 0.65, 0, Math.PI * 2);
                ctx.stroke();

                // 4 Button Holes
                ctx.fillStyle = "#facc15";
                const hOffset = r * 0.3;
                [-hOffset, hOffset].forEach(hx => {
                    [-hOffset, hOffset].forEach(hy => {
                        ctx.beginPath();
                        ctx.arc(hx, hy, r * 0.12, 0, Math.PI * 2);
                        ctx.fill();
                    });
                });

                ctx.restore();
            }
        }

        // FIREFLY / PARTICLES CLASS
        class Firefly {
            constructor() { this.reset(); }
            reset() {
                this.x = Math.random() * width;
                this.y = Math.random() * height;
                this.size = Math.random() * 2.2 + 1.2;
                this.alpha = Math.random() * 0.5 + 0.2;
                this.vx = (Math.random() - 0.5) * 0.5;
                this.vy = (Math.random() - 0.5) * 0.5;
                this.color = Math.random() > 0.4 ? "#facc15" : "#38bdf8";
            }
            update() {
                this.x += this.vx;
                this.y += this.vy;
                if (this.x < 0 || this.x > width || this.y < 0 || this.y > height) {
                    this.reset();
                }
            }
            draw() {
                ctx.save();
                ctx.globalAlpha = this.alpha;
                ctx.fillStyle = this.color;
                ctx.shadowBlur = 10;
                ctx.shadowColor = this.color;
                ctx.beginPath();
                ctx.arc(this.x, this.y, this.size, 0, Math.PI * 2);
                ctx.fill();
                ctx.restore();
            }
        }

        // FLOATING LEAF CLASS
        class FloatingLeaf {
            constructor() { this.reset(true); }
            reset(initial = false) {
                this.x = Math.random() * width;
                this.y = initial ? Math.random() * height : -20;
                this.size = Math.random() * 8 + 7;
                this.speedY = Math.random() * 0.55 + 0.25;
                this.speedX = Math.random() * 0.4 - 0.2;
                this.rotation = Math.random() * Math.PI * 2;
                this.rotSpeed = (Math.random() - 0.5) * 0.025;
                this.oscillation = Math.random() * Math.PI * 2;
                this.alpha = Math.random() * 0.4 + 0.25;
            }
            update() {
                this.y += this.speedY;
                this.oscillation += 0.02;
                this.x += this.speedX + Math.sin(this.oscillation) * 0.5;
                this.rotation += this.rotSpeed;
                if (this.y > height + 30) this.reset(false);
            }
            draw() {
                ctx.save();
                ctx.translate(this.x, this.y);
                ctx.rotate(this.rotation);
                ctx.globalAlpha = this.alpha;
                ctx.fillStyle = "#1e293b";
                ctx.beginPath();
                ctx.ellipse(0, 0, this.size * 0.4, this.size, 0, 0, Math.PI * 2);
                ctx.fill();
                ctx.restore();
            }
        }

        // FOG / MIST CLASS
        class FogParticle {
            constructor() { this.reset(); }
            reset() {
                this.x = Math.random() * width;
                this.y = Math.random() * height * 0.5 + height * 0.5;
                this.radius = Math.random() * 180 + 120;
                this.alpha = Math.random() * 0.07 + 0.02;
                this.vx = Math.random() * 0.2 + 0.05;
            }
            update() {
                this.x += this.vx;
                if (this.x - this.radius > width) this.x = -this.radius;
            }
            draw() {
                ctx.save();
                ctx.globalAlpha = this.alpha;
                const grad = ctx.createRadialGradient(this.x, this.y, 10, this.x, this.y, this.radius);
                grad.addColorStop(0, "rgba(56, 189, 248, 0.25)");
                grad.addColorStop(1, "rgba(6, 7, 19, 0)");
                ctx.fillStyle = grad;
                ctx.beginPath();
                ctx.arc(this.x, this.y, this.radius, 0, Math.PI * 2);
                ctx.fill();
                ctx.restore();
            }
        }

        // SWAYING FLOWERS AT BOTTOM
        class SwayingFlower {
            constructor(x) {
                this.x = x;
                this.height = Math.random() * 28 + 32;
                this.angle = 0;
                this.speed = Math.random() * 0.02 + 0.01;
                this.color = Math.random() > 0.5 ? "#facc15" : "#c084fc";
            }
            update() {
                this.angle += this.speed;
            }
            draw() {
                const sway = Math.sin(this.angle) * 7;
                const baseY = height;
                const topY = height - this.height;

                ctx.save();
                ctx.strokeStyle = "#0f172a";
                ctx.lineWidth = 2.5;
                ctx.beginPath();
                ctx.moveTo(this.x, baseY);
                ctx.quadraticCurveTo(this.x + sway * 0.5, baseY - this.height * 0.5, this.x + sway, topY);
                ctx.stroke();

                // Petals
                ctx.fillStyle = this.color;
                ctx.shadowBlur = 8;
                ctx.shadowColor = this.color;
                ctx.beginPath();
                ctx.arc(this.x + sway, topY, 4, 0, Math.PI * 2);
                ctx.fill();
                ctx.restore();
            }
        }

        // CORALINE'S BLACK CAT WALKING AT BOTTOM
        class BlackCat {
            constructor() {
                this.x = -60;
                this.speed = 0.55;
                this.step = 0;
            }
            update() {
                this.x += this.speed;
                this.step += 0.075;
                if (this.x > width + 80) {
                    this.x = -120;
                }
            }
            draw() {
                const y = height - 12;
                const legOffset = Math.sin(this.step) * 4;

                ctx.save();
                ctx.fillStyle = "#020617";
                ctx.shadowBlur = 4;
                ctx.shadowColor = "rgba(0,0,0,0.8)";

                // Body
                ctx.beginPath();
                ctx.ellipse(this.x, y - 10, 16, 9, 0, 0, Math.PI * 2);
                ctx.fill();

                // Head
                ctx.beginPath();
                ctx.arc(this.x + 14, y - 17, 7, 0, Math.PI * 2);
                ctx.fill();

                // Ears
                ctx.beginPath();
                ctx.moveTo(this.x + 12, y - 22);
                ctx.lineTo(this.x + 15, y - 27);
                ctx.lineTo(this.x + 18, y - 22);
                ctx.fill();

                // GLOWING BLUE EYES (CORALINE CAT EYES)
                ctx.fillStyle = "#38bdf8";
                ctx.shadowBlur = 8;
                ctx.shadowColor = "#38bdf8";
                ctx.beginPath();
                ctx.arc(this.x + 17, y - 18, 1.4, 0, Math.PI * 2);
                ctx.fill();

                // Legs
                ctx.fillStyle = "#020617";
                ctx.shadowBlur = 0;
                ctx.fillRect(this.x - 8 + legOffset, y - 3, 2.5, 10);
                ctx.fillRect(this.x - 2 - legOffset, y - 3, 2.5, 10);
                ctx.fillRect(this.x + 6 + legOffset, y - 3, 2.5, 10);
                ctx.fillRect(this.x + 12 - legOffset, y - 3, 2.5, 10);

                // Tail
                ctx.strokeStyle = "#020617";
                ctx.lineWidth = 2.5;
                ctx.beginPath();
                ctx.moveTo(this.x - 15, y - 12);
                ctx.quadraticCurveTo(this.x - 25, y - 20 + Math.sin(this.step) * 3, this.x - 20, y - 28);
                ctx.stroke();

                ctx.restore();
            }
        }

        // INITIALIZE ANIMATION OBJECTS
        const stars = Array.from({ length: 90 }, () => new Star());
        const buttonStars = Array.from({ length: 18 }, () => new ButtonStar());
        const fireflies = Array.from({ length: 30 }, () => new Firefly());
        const leaves = Array.from({ length: 18 }, () => new FloatingLeaf());
        const fogs = Array.from({ length: 8 }, () => new FogParticle());
        const cat = new BlackCat();

        const flowerCount = Math.floor(window.innerWidth / 35);
        const flowers = [];
        for (let i = 0; i < flowerCount; i++) {
            flowers.push(new SwayingFlower(i * 35 + Math.random() * 15));
        }

        // MAIN ANIMATION LOOP
        function animate() {
            ctx.clearRect(0, 0, width, height);

            // 1. Regular Stars & Button Stars
            stars.forEach(s => { s.update(); s.draw(); });
            buttonStars.forEach(bs => { bs.update(); bs.draw(); });

            // 2. Fog
            fogs.forEach(f => { f.update(); f.draw(); });

            // 3. Swaying Flowers
            flowers.forEach(fl => { fl.update(); fl.draw(); });

            // 4. Coraline's Cat
            cat.update();
            cat.draw();

            // 5. Floating Leaves
            leaves.forEach(l => { l.update(); l.draw(); });

            // 6. Fireflies
            fireflies.forEach(ff => { ff.update(); ff.draw(); });

            requestAnimationFrame(animate);
        }

        animate();
    </script>
</body>
</html>
