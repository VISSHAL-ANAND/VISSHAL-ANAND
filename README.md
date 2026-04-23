<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes">
    <title>Visshal · Hyperdrive GitHub Profile</title>
    <!-- Google Fonts & Font Awesome 6 (free) -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,300;14..32,400;14..32,600;14..32,700;14..32,800&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <!-- Canvas effect library: particles.js light (optional but we use custom canvas for snake & effects) -->
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background: radial-gradient(circle at 20% 30%, #0a0f1e, #03050b);
            font-family: 'Inter', sans-serif;
            color: #eef5ff;
            display: flex;
            justify-content: center;
            padding: 2rem 1.5rem;
        }

        /* main container with glassmorphism */
        .glass-readme {
            max-width: 1300px;
            width: 100%;
            background: rgba(12, 20, 35, 0.55);
            backdrop-filter: blur(12px);
            border-radius: 3rem;
            border: 1px solid rgba(0, 255, 255, 0.25);
            box-shadow: 0 25px 45px rgba(0,0,0,0.5), 0 0 0 1px rgba(0, 255, 255, 0.1) inset;
            overflow: hidden;
            padding: 2rem 2rem 2rem 2rem;
            transition: all 0.3s ease;
        }

        /* animated gradient text */
        .gradient-text {
            background: linear-gradient(135deg, #A0F0FF, #6C63FF, #FF5F6D);
            background-size: 300% 300%;
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            animation: aurora 6s ease infinite;
        }

        @keyframes aurora {
            0% { background-position: 0% 50%;}
            50% { background-position: 100% 50%;}
            100% { background-position: 0% 50%;}
        }

        /* typewriter + glitch */
        .glitch {
            font-weight: 800;
            position: relative;
            text-shadow: 0.05em 0 0 rgba(255,0,0,0.4), -0.05em -0.025em 0 rgba(0,255,255,0.4);
            animation: glitch-skew 3s infinite alternate;
        }

        @keyframes glitch-skew {
            0% { transform: skew(0deg);}
            20% { transform: skew(2deg);}
            40% { transform: skew(-1deg);}
            60% { transform: skew(0.5deg);}
            100% { transform: skew(0deg);}
        }

        /* floating animations */
        @keyframes float {
            0% { transform: translateY(0px);}
            100% { transform: translateY(-8px);}
        }
        .float-card {
            transition: transform 0.3s ease, box-shadow 0.3s;
        }
        .float-card:hover {
            transform: translateY(-8px);
            box-shadow: 0 20px 30px -12px rgba(0,255,255,0.3);
        }

        /* stats & lang badges glass style */
        .stat-badge {
            background: rgba(0, 20, 40, 0.6);
            backdrop-filter: blur(4px);
            border-radius: 2rem;
            padding: 0.75rem 1.2rem;
            border: 1px solid rgba(0, 255, 255, 0.3);
            font-weight: 600;
            font-size: 1rem;
        }

        .lang-bar {
            height: 10px;
            border-radius: 20px;
            background: #2a2f3f;
            overflow: hidden;
        }

        .lang-fill {
            height: 100%;
            width: 0%;
            border-radius: 20px;
            background: linear-gradient(90deg, #38bdf8, #a855f7);
            animation: fillLang 1.2s cubic-bezier(0.2, 0.9, 0.4, 1.1) forwards;
        }

        @keyframes fillLang {
            to { width: var(--w); }
        }

        /* snake canvas container */
        .snake-container {
            background: #0a0f1ecc;
            border-radius: 2rem;
            padding: 1rem;
            border: 1px solid #2dd4bf55;
            box-shadow: 0 10px 25px -5px rgba(0,0,0,0.5);
            transition: 0.2s;
        }

        canvas#snakeCanvas {
            background: #01050f;
            border-radius: 1.5rem;
            display: block;
            margin: 0 auto;
            width: 100%;
            height: auto;
            cursor: pointer;
        }

        .social-icon {
            background: rgba(255,255,255,0.05);
            border-radius: 50%;
            width: 48px;
            height: 48px;
            display: inline-flex;
            align-items: center;
            justify-content: center;
            font-size: 1.8rem;
            transition: all 0.2s ease;
            color: #cbd5e6;
            backdrop-filter: blur(6px);
            border: 1px solid rgba(88, 166, 255, 0.4);
        }
        .social-icon:hover {
            transform: scale(1.2) rotate(5deg);
            background: #1e2a5e;
            color: #00ffff;
            border-color: cyan;
            box-shadow: 0 0 12px cyan;
        }

        .tech-tag {
            background: linear-gradient(145deg, #1f2a3e, #111827);
            padding: 0.3rem 1rem;
            border-radius: 40px;
            font-size: 0.85rem;
            font-weight: 500;
            letter-spacing: 0.3px;
            border-left: 2px solid cyan;
        }

        hr {
            border-color: rgba(0, 255, 255, 0.2);
            margin: 1rem 0;
        }

        .btn-ghost {
            background: none;
            border: 1px solid cyan;
            border-radius: 2rem;
            padding: 0.4rem 1.5rem;
            transition: 0.2s;
            color: cyan;
        }

        .btn-ghost:hover {
            background: cyan;
            color: black;
            box-shadow: 0 0 10px cyan;
        }
        @media (max-width: 850px) {
            .glass-readme { padding: 1.2rem; }
        }
        a { text-decoration: none; color: inherit; }
    </style>
</head>
<body>
<div class="glass-readme">
    <!-- HEADER with GIF left + info -->
    <div style="display: flex; flex-wrap: wrap; gap: 2rem; align-items: center; margin-bottom: 2rem;">
        <!-- Left animated coding GIF (person coding) -->
        <div style="flex: 1.2; min-width: 200px; border-radius: 2rem; overflow: hidden; box-shadow: 0 20px 30px -15px black; border: 1px solid cyan;">
            <img src="https://media3.giphy.com/media/qgQUggAC3Pfv687qPC/giphy.gif?cid=790b7611b1f2cs83o3wk914phijjtr5xcs3lty6c2xafdn1w&ep=v1_gifs_search&rid=giphy.gif&ct=g" 
                 alt="coding gif" style="width: 100%; height: 100%; object-fit: cover; display: block;">
        </div>
        <!-- Right intro -->
        <div style="flex: 2;">
            <h1 style="font-size: 3.2rem; font-weight: 800;"><span class="gradient-text glitch">Visshal</span> <i class="fas fa-bolt" style="color: #f0f921; text-shadow: 0 0 5px gold;"></i></h1>
            <div style="display: flex; gap: 12px; flex-wrap: wrap; margin: 0.5rem 0 0.8rem;">
                <span class="tech-tag"><i class="fas fa-microchip"></i> Edge AI</span>
                <span class="tech-tag"><i class="fas fa-cloud"></i> Distributed Systems</span>
                <span class="tech-tag"><i class="fas fa-brain"></i> Computer Vision</span>
                <span class="tech-tag"><i class="fas fa-robot"></i> LLMs</span>
            </div>
            <p style="font-size: 1.2rem; max-width: 550px;">🚀 First-year engineering student building <span style="color: #7df9ff;">real-world AI, IoT, and distributed systems</span> — solving practical problems with intelligent & scalable tech.</p>
            <div style="margin-top: 1rem; display: flex; gap: 0.8rem; flex-wrap: wrap;">
                <span class="stat-badge"><i class="fas fa-star"></i> 1.6k stars</span>
                <span class="stat-badge"><i class="fas fa-code-branch"></i> 413 commits</span>
                <span class="stat-badge"><i class="fas fa-pull-request"></i> 4 PRs</span>
                <span class="stat-badge"><i class="fas fa-exclamation-triangle"></i> 0 issues</span>
                <span class="stat-badge"><i class="fas fa-users"></i> 5 contributed</span>
            </div>
        </div>
    </div>

    <!-- Most used languages + fancy bars with percentages from given data -->
    <div style="margin: 2rem 0 1.5rem; background: rgba(0,0,0,0.3); border-radius: 2rem; padding: 1.2rem 1.5rem;">
        <h2 style="display: flex; align-items: center; gap: 0.6rem;"><i class="fas fa-chart-line" style="color: cyan;"></i> Most Used Languages <span style="font-size: 0.8rem;">⚡ actual stats</span></h2>
        <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(220px,1fr)); gap: 1rem; margin-top: 1rem;">
            <div><span>TypeScript 28.71%</span><div class="lang-bar mt-1"><div class="lang-fill" style="--w:28.71%"></div></div></div>
            <div><span>CSS 20.99%</span><div class="lang-bar"><div class="lang-fill" style="--w:20.99%"></div></div></div>
            <div><span>Python 15.04%</span><div class="lang-bar"><div class="lang-fill" style="--w:15.04%"></div></div></div>
            <div><span>JavaScript 12.29%</span><div class="lang-bar"><div class="lang-fill" style="--w:12.29%"></div></div></div>
            <div><span>C# 11.23%</span><div class="lang-bar"><div class="lang-fill" style="--w:11.23%"></div></div></div>
            <div><span>HTML 11.14%</span><div class="lang-bar"><div class="lang-fill" style="--w:11.14%"></div></div></div>
            <div><span>GAP 0.53%</span><div class="lang-bar"><div class="lang-fill" style="--w:0.53%"></div></div></div>
            <div><span>GDScript 0.06%</span><div class="lang-bar"><div class="lang-fill" style="--w:0.06%"></div></div></div>
        </div>
    </div>

    <!-- TECH STACK + Social Media section with icons -->
    <div style="display: flex; flex-wrap: wrap; justify-content: space-between; gap: 1rem; margin: 1rem 0 2rem;">
        <div class="float-card" style="background: rgba(20,30,55,0.5); border-radius: 1.8rem; padding: 1rem 1.8rem; flex:2; min-width: 200px;">
            <h3><i class="fas fa-cogs"></i> ⚙️ Tech Stack</h3>
            <div style="display: flex; flex-wrap: wrap; gap: 10px; margin-top: 12px;">
                <span class="tech-tag"><i class="fab fa-python"></i> Python</span> <span class="tech-tag"><i class="fab fa-js"></i> JS/TS</span> <span class="tech-tag"><i class="fas fa-microchip"></i> C/C++</span>
                <span class="tech-tag"><i class="fas fa-bolt"></i> FastAPI</span> <span class="tech-tag"><i class="fas fa-eye"></i> OpenCV</span>
                <span class="tech-tag"><i class="fas fa-chart-simple"></i> Scikit-learn</span> <span class="tech-tag"><i class="fab fa-raspberry-pi"></i> Raspberry Pi</span>
                <span class="tech-tag"><i class="fas fa-wifi"></i> LoRa</span> <span class="tech-tag"><i class="fas fa-brain"></i> TinyML</span>
                <span class="tech-tag"><i class="fas fa-network-wired"></i> Distributed Sys</span>
            </div>
        </div>
        <div class="float-card" style="background: rgba(20,30,55,0.5); border-radius: 1.8rem; padding: 1rem 1.8rem;">
            <h3><i class="fas fa-share-alt"></i> Social Cosmos</h3>
            <div style="display: flex; gap: 20px; margin-top: 14px; flex-wrap: wrap;">
                <a href="#" class="social-icon"><i class="fab fa-js"></i></a>
                <a href="#" class="social-icon"><i class="fab fa-ts"></i></a>
                <a href="#" class="social-icon"><i class="fab fa-instagram"></i></a>
                <a href="#" class="social-icon"><i class="fab fa-twitter"></i></a>
                <a href="#" class="social-icon"><i class="fab fa-discord"></i></a>
                <a href="#" class="social-icon"><i class="fas fa-envelope"></i></a>
                <a href="#" class="social-icon"><i class="fab fa-linkedin-in"></i></a>
            </div>
        </div>
    </div>

    <!-- FEATURED PROJECTS grid with animation -->
    <h2 style="margin-top: 1rem;"><i class="fas fa-rocket"></i> 🚀 Featured Projects</h2>
    <div style="display: grid; grid-template-columns: repeat(auto-fill, minmax(310px,1fr)); gap: 1.5rem; margin: 1.5rem 0;">
        <div class="float-card" style="background: #0f172a90; border-radius: 1.5rem; padding: 1.2rem; border-left: 4px solid #2dd4bf;">
            <h3>🎤 AI Mock Interviewer</h3>
            <p>Real-time AI questions + LLM evaluation. FastAPI + JS frontend.</p>
            <span class="badge">🔥 LLM APIs</span>
        </div>
        <div class="float-card" style="background: #0f172a90; border-radius: 1.5rem; padding: 1.2rem; border-left: 4px solid #a855f7;">
            <h3>🏥 Adaptive Image Compression (Tele-Health)</h3>
            <p>PDE denoising + DCT/PCA, 12:1 ratio, SSIM>0.85.</p>
            <span class="badge">📉 65% failure reduction</span>
        </div>
        <div class="float-card" style="background: #0f172a90; border-radius: 1.5rem; padding: 1.2rem; border-left: 4px solid #f97316;">
            <h3>🌲 Forest Guardian Edge-AI</h3>
            <p>CNN acoustic detection + LoRa + real-time dashboard.</p>
            <span class="badge">🌿 TinyML</span>
        </div>
        <div class="float-card" style="background: #0f172a90; border-radius: 1.5rem; padding: 1.2rem; border-left: 4px solid #38bdf8;">
            <h3>🌐 Smart Health Habit Coach</h3>
            <p>AI personalized recommendations & habit tracking.</p>
        </div>
        <div class="float-card" style="background: #0f172a90; border-radius: 1.5rem; padding: 1.2rem; border-left: 4px solid #e879f9;">
            <h3>🔐 Google OAuth System</h3>
            <p>OAuth 2.0 + FastAPI session management.</p>
        </div>
        <div class="float-card" style="background: #0f172a90; border-radius: 1.5rem; padding: 1.2rem; border-left: 4px solid #10b981;">
            <h3>📡 Multi-Agent Mesh Simulator</h3>
            <p>Leader election, Dijkstra routing, fault-tolerant visualization.</p>
        </div>
    </div>

    <!-- Snake Game with Git Commits theme (GitHub contribution style) -->
    <div style="margin: 2.5rem 0 1rem;">
        <div class="snake-container">
            <div style="display: flex; justify-content: space-between; align-items: baseline; flex-wrap: wrap; margin-bottom: 0.8rem;">
                <h2><i class="fas fa-gamepad"></i> 🐍 Git Commit Snake Game</h2>
                <p style="font-size: 0.8rem; background: #03060e; padding: 0.2rem 1rem; border-radius: 30px;"><i class="fas fa-arrow-up"></i> Eat commits to grow! (classic snake + contribution theme)</p>
            </div>
            <canvas id="snakeCanvas" width="800" height="400" style="width:100%; height:auto; max-width:800px; aspect-ratio:800/400;"></canvas>
            <div style="display: flex; justify-content: center; gap: 1rem; margin-top: 1rem;">
                <button id="restartSnakeBtn" class="btn-ghost"><i class="fas fa-undo-alt"></i> Restart Snake</button>
                <span style="font-family: monospace;">Score: <span id="snakeScore">0</span> &nbsp;|&nbsp; HighScore: <span id="highScore">0</span></span>
            </div>
            <p class="mt-2" style="font-size: 0.75rem; text-align: center;">⬆️ ⬇️ ⬅️ ➡️  — each pellet = git commit +1 🍎</p>
        </div>
    </div>

    <!-- 2026 GOALS + additional style -->
    <hr>
    <div style="display: flex; justify-content: space-between; flex-wrap: wrap; gap: 1rem; margin: 1rem 0;">
        <div><i class="fas fa-calendar-alt" style="color: cyan;"></i> <strong>📈 2026 Goals</strong><br>⚡ Production AI+IoT systems <br>⚡ Open source contributions <br>⚡ Edge intelligence deep dive</div>
        <div><i class="fas fa-quote-right"></i> <em style="color:#b9f2ff;">"I build things that actually solve problems."</em></div>
    </div>
    <footer style="text-align: center; margin-top: 2rem; opacity: 0.8; font-size: 0.8rem;">
        <i class="fas fa-infinity"></i> Crafted with crazy animation, live snake & GitHub aura — Visshal
    </footer>
</div>

<script>
    // ----------------------- SNAKE GAME (Git Commit themed) -----------------------
    const canvas = document.getElementById('snakeCanvas');
    const ctx = canvas.getContext('2d');
    const scoreSpan = document.getElementById('snakeScore');
    const highSpan = document.getElementById('highScore');

    // Set canvas dimensions (logical 800x400)
    canvas.width = 800;
    canvas.height = 400;
    let snake = [
        {x: 200, y: 200},
        {x: 190, y: 200},
        {x: 180, y: 200},
        {x: 170, y: 200},
        {x: 160, y: 200}
    ];
    let direction = 'RIGHT';
    let nextDirection = 'RIGHT';
    let food = {x: 400, y: 200};
    let score = 0;
    let highScore = localStorage.getItem('snakeHighScore') ? parseInt(localStorage.getItem('snakeHighScore')) : 0;
    let gameLoop = null;
    let gameRunning = true;
    highSpan.innerText = highScore;

    function randomFood() {
        const gridSize = 10;
        const maxX = canvas.width - gridSize;
        const maxY = canvas.height - gridSize;
        let newFood = {
            x: Math.floor(Math.random() * (maxX / gridSize)) * gridSize,
            y: Math.floor(Math.random() * (maxY / gridSize)) * gridSize
        };
        // avoid spawning on snake
        for (let segment of snake) {
            if (segment.x === newFood.x && segment.y === newFood.y) {
                return randomFood();
            }
        }
        return newFood;
    }

    function updateScoreUI() {
        scoreSpan.innerText = score;
        if (score > highScore) {
            highScore = score;
            highSpan.innerText = highScore;
            localStorage.setItem('snakeHighScore', highScore);
        }
    }

    function drawGitTheme() {
        // background
        ctx.fillStyle = '#01050f';
        ctx.fillRect(0, 0, canvas.width, canvas.height);
        // draw grid (like contribution style squares)
        ctx.strokeStyle = '#1a2a3a';
        ctx.lineWidth = 0.5;
        for (let i = 0; i <= canvas.width / 20; i++) {
            ctx.beginPath();
            ctx.moveTo(i * 20, 0);
            ctx.lineTo(i * 20, canvas.height);
            ctx.stroke();
            ctx.moveTo(0, i * 20);
            ctx.lineTo(canvas.width, i * 20);
            ctx.stroke();
        }
        // draw food as "git commit" green block with spark
        ctx.shadowBlur = 6;
        ctx.shadowColor = '#2dd4bf';
        ctx.fillStyle = '#39ff14';
        ctx.fillRect(food.x, food.y, 10, 10);
        ctx.fillStyle = '#b0ff90';
        ctx.fillRect(food.x+2, food.y+2, 6, 6);
        ctx.shadowBlur = 0;
        // draw snake as "contribution streak"
        for (let i = 0; i < snake.length; i++) {
            const seg = snake[i];
            const intensity = 0.5 + (i / snake.length) * 0.5;
            ctx.fillStyle = `rgba(34, 211, 238, ${intensity})`;
            ctx.fillRect(seg.x, seg.y, 10, 10);
            ctx.strokeStyle = '#0ff';
            ctx.strokeRect(seg.x, seg.y, 10, 10);
        }
        // head special
        const head = snake[0];
        ctx.fillStyle = '#f0f';
        ctx.fillRect(head.x, head.y, 10, 10);
        ctx.fillStyle = 'white';
        ctx.fillRect(head.x+3, head.y+3, 4, 4);
        // draw commit message style
        ctx.font = "bold 13px 'JetBrains Mono'";
        ctx.fillStyle = "#adf0ff";
        ctx.fillText(`🍎 commits: ${score}`, 20, 40);
        ctx.font = "10px monospace";
        ctx.fillStyle = "#aaa";
        ctx.fillText("← Snake eats commits → grow contributions", canvas.width-180, 30);
    }

    function moveSnake() {
        direction = nextDirection;
        let newHead = {...snake[0]};
        switch(direction) {
            case 'RIGHT': newHead.x += 10; break;
            case 'LEFT': newHead.x -= 10; break;
            case 'UP': newHead.y -= 10; break;
            case 'DOWN': newHead.y += 10; break;
        }
        // check collision with walls
        if (newHead.x < 0 || newHead.y < 0 || newHead.x >= canvas.width || newHead.y >= canvas.height) {
            gameOver();
            return false;
        }
        // check collision with self
        for (let seg of snake) {
            if (seg.x === newHead.x && seg.y === newHead.y) {
                gameOver();
                return false;
            }
        }
        snake.unshift(newHead);
        // food check
        if (newHead.x === food.x && newHead.y === food.y) {
            score++;
            updateScoreUI();
            food = randomFood();
        } else {
            snake.pop();
        }
        return true;
    }

    function gameOver() {
        if (gameLoop) clearInterval(gameLoop);
        gameRunning = false;
        ctx.fillStyle = "rgba(0,0,0,0.75)";
        ctx.fillRect(0, 0, canvas.width, canvas.height);
        ctx.font = "bold 28px 'Inter'";
        ctx.fillStyle = "#ff5e7c";
        ctx.shadowBlur = 0;
        ctx.fillText("💀 GAME OVER 💀", canvas.width/2-130, canvas.height/2);
        ctx.font = "16px monospace";
        ctx.fillStyle = "#0ff";
        ctx.fillText("Click 'Restart Snake' to start new streak", canvas.width/2-160, canvas.height/2+50);
        updateScoreUI();
    }

    function restartGame() {
        if (gameLoop) clearInterval(gameLoop);
        snake = [
            {x: 200, y: 200},
            {x: 190, y: 200},
            {x: 180, y: 200},
            {x: 170, y: 200},
            {x: 160, y: 200}
        ];
        direction = 'RIGHT';
        nextDirection = 'RIGHT';
        score = 0;
        scoreSpan.innerText = '0';
        updateScoreUI();
        food = randomFood();
        gameRunning = true;
        gameLoop = setInterval(() => {
            if (!gameRunning) return;
            const success = moveSnake();
            drawGitTheme();
            if (!success) gameRunning = false;
        }, 110);
    }

    // event listeners
    window.addEventListener('keydown', (e) => {
        if (!gameRunning) return;
        const key = e.key;
        if (key === 'ArrowUp' && direction !== 'DOWN') nextDirection = 'UP';
        else if (key === 'ArrowDown' && direction !== 'UP') nextDirection = 'DOWN';
        else if (key === 'ArrowLeft' && direction !== 'RIGHT') nextDirection = 'LEFT';
        else if (key === 'ArrowRight' && direction !== 'LEFT') nextDirection = 'RIGHT';
        e.preventDefault();
    });
    document.getElementById('restartSnakeBtn').addEventListener('click', () => restartGame());

    // Initialize game
    food = randomFood();
    gameLoop = setInterval(() => {
        if (!gameRunning) return;
        const cont = moveSnake();
        drawGitTheme();
        if (!cont) gameRunning = false;
    }, 110);
    drawGitTheme();

    // Add a cool floating particles effect (optional mouse trail)
    const readmeDiv = document.querySelector('.glass-readme');
    const style = document.createElement('style');
    style.textContent = `
        .badge { background: #2dd4bf30; border-radius: 40px; padding: 4px 12px; font-size: 0.7rem; color: cyan; display: inline-block; margin-top: 8px;}
        .mt-1 { margin-top: 4px; }
        .mt-2 { margin-top: 10px; }
    `;
    document.head.appendChild(style);
</script>
</body>
</html>
