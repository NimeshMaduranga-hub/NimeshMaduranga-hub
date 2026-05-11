<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Nimesh Maduranga | Full Stack Developer</title>
    
    <!-- Google Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;700;800&family=JetBrains+Mono:wght@400;700&display=swap" rel="stylesheet">
    
    <!-- FontAwesome for Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">

    <style>
        /* --- CSS Variables & Reset --- */
        :root {
            --bg-color: #0a0a0c;
            --card-bg: #16161a;
            --text-primary: #fffffe;
            --text-secondary: #94a1b2;
            --accent-primary: #7f5af0; /* Purple */
            --accent-secondary: #2cb67d; /* Green */
            --accent-glow: rgba(127, 90, 240, 0.3);
            --font-main: 'Inter', sans-serif;
            --font-code: 'JetBrains Mono', monospace;
            --transition: all 0.3s ease-in-out;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background-color: var(--bg-color);
            color: var(--text-primary);
            font-family: var(--font-main);
            line-height: 1.6;
            overflow-x: hidden;
        }

        a {
            text-decoration: none;
            color: inherit;
            transition: var(--transition);
        }

        ul {
            list-style: none;
        }

        /* --- Layout Utilities --- */
        .container {
            max-width: 1100px;
            margin: 0 auto;
            padding: 0 20px;
        }

        section {
            padding: 80px 0;
        }

        /* --- Header / Nav --- */
        header {
            position: fixed;
            top: 0;
            width: 100%;
            background: rgba(10, 10, 12, 0.85);
            backdrop-filter: blur(10px);
            z-index: 1000;
            border-bottom: 1px solid rgba(255, 255, 255, 0.05);
        }

        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            height: 70px;
        }

        .logo {
            font-size: 1.5rem;
            font-weight: 800;
            background: linear-gradient(90deg, #fffffe, var(--accent-primary));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            letter-spacing: -0.5px;
        }

        .nav-links {
            display: flex;
            gap: 30px;
        }

        .nav-links a {
            font-size: 0.95rem;
            color: var(--text-secondary);
            font-weight: 500;
        }

        .nav-links a:hover {
            color: var(--accent-primary);
        }

        /* --- Hero Section --- */
        .hero {
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            position: relative;
        }

        /* Ambient Background Glow */
        .hero::before {
            content: '';
            position: absolute;
            width: 300px;
            height: 300px;
            background: var(--accent-primary);
            filter: blur(150px);
            opacity: 0.15;
            border-radius: 50%;
            z-index: -1;
            top: 20%;
            left: 20%;
        }

        .hero::after {
            content: '';
            position: absolute;
            width: 300px;
            height: 300px;
            background: var(--accent-secondary);
            filter: blur(150px);
            opacity: 0.1;
            border-radius: 50%;
            z-index: -1;
            bottom: 20%;
            right: 20%;
        }

        .hero-content h1 {
            font-size: 4rem;
            font-weight: 800;
            margin-bottom: 10px;
            line-height: 1.1;
        }

        .hero-content h1 span {
            color: var(--accent-primary);
        }

        .typewriter {
            font-family: var(--font-code);
            font-size: 1.25rem;
            color: var(--text-secondary);
            min-height: 1.6em;
            margin-bottom: 30px;
        }

        .cursor {
            display: inline-block;
            width: 2px;
            background-color: var(--accent-secondary);
            animation: blink 1s infinite;
        }

        @keyframes blink {
            0%, 100% { opacity: 1; }
            50% { opacity: 0; }
        }

        .hero-btns {
            margin-top: 30px;
            display: flex;
            justify-content: center;
            gap: 20px;
        }

        .btn {
            padding: 12px 28px;
            border-radius: 5px;
            font-weight: 600;
            font-size: 1rem;
            cursor: pointer;
            transition: var(--transition);
        }

        .btn-primary {
            background-color: var(--accent-primary);
            color: #fffffe;
            border: 2px solid var(--accent-primary);
        }

        .btn-primary:hover {
            background-color: transparent;
            box-shadow: 0 0 15px var(--accent-glow);
        }

        .btn-outline {
            background-color: transparent;
            color: var(--text-secondary);
            border: 1px solid var(--text-secondary);
        }

        .btn-outline:hover {
            border-color: var(--text-primary);
            color: var(--text-primary);
        }

        /* --- About & Goals --- */
        .section-title {
            font-size: 2rem;
            margin-bottom: 40px;
            position: relative;
            display: inline-block;
        }

        .section-title::after {
            content: '';
            position: absolute;
            width: 50%;
            height: 4px;
            background: var(--accent-secondary);
            bottom: -10px;
            left: 0;
            border-radius: 2px;
        }

        .about-grid {
            display: grid;
            grid-template-columns: 1.5fr 1fr;
            gap: 40px;
            align-items: start;
        }

        .card {
            background-color: var(--card-bg);
            padding: 30px;
            border-radius: 12px;
            border: 1px solid rgba(255, 255, 255, 0.05);
            transition: var(--transition);
        }

        .card:hover {
            transform: translateY(-5px);
            border-color: var(--accent-primary);
        }

        .about-text p {
            color: var(--text-secondary);
            margin-bottom: 20px;
        }

        .location-badge {
            display: inline-flex;
            align-items: center;
            gap: 8px;
            background: rgba(44, 182, 125, 0.1);
            color: var(--accent-secondary);
            padding: 8px 16px;
            border-radius: 20px;
            font-size: 0.9rem;
            font-weight: 600;
            margin-bottom: 20px;
        }

        .goals-list li {
            margin-bottom: 15px;
            color: var(--text-secondary);
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .goals-list li i {
            color: var(--accent-primary);
        }

        /* --- Tech Stack --- */
        .tech-grid {
            display: flex;
            flex-wrap: wrap;
            gap: 15px;
            justify-content: center;
        }

        .tech-item {
            display: flex;
            align-items: center;
            gap: 10px;
            background: rgba(255, 255, 255, 0.03);
            padding: 12px 20px;
            border-radius: 8px;
            border: 1px solid rgba(255, 255, 255, 0.05);
            font-family: var(--font-code);
            font-size: 0.9rem;
            transition: var(--transition);
        }

        .tech-item:hover {
            background: rgba(255, 255, 255, 0.08);
            transform: scale(1.05);
            border-color: var(--text-secondary);
        }

        /* --- GitHub Stats (Updated) --- */
        .stats-wrapper {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 20px;
        }

        .stats-grid {
            display: grid;
            grid-template-columns: 1fr; /* Stack on mobile */
            gap: 20px;
            width: 100%;
            max-width: 900px;
        }

        .stat-card {
            background: rgba(255,255,255,0.02);
            padding: 15px;
            border-radius: 12px;
            box-shadow: 0 4px 20px rgba(0,0,0,0.2);
            text-align: center;
            width: 100%;
        }

        .stat-card img {
            max-width: 100%;
            border-radius: 8px;
        }

        /* --- Connect --- */
        .connect-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
        }

        .connect-card {
            background: var(--card-bg);
            padding: 30px;
            border-radius: 12px;
            text-align: center;
            border: 1px solid rgba(255, 255, 255, 0.05);
            transition: var(--transition);
            position: relative;
            overflow: hidden;
        }

        .connect-card:hover {
            transform: translateY(-5px);
            border-color: var(--accent-secondary);
        }

        .connect-card i {
            font-size: 2.5rem;
            margin-bottom: 15px;
            color: var(--text-secondary);
            transition: var(--transition);
        }

        .connect-card:hover i {
            color: var(--accent-secondary);
        }

        .connect-card h3 {
            font-size: 1.2rem;
            margin-bottom: 10px;
        }

        .connect-card p {
            font-size: 0.9rem;
            color: var(--text-secondary);
        }

        /* --- Footer --- */
        footer {
            text-align: center;
            padding: 40px 0;
            border-top: 1px solid rgba(255, 255, 255, 0.05);
            margin-top: 50px;
        }

        .fun-fact {
            background: linear-gradient(90deg, var(--accent-primary), var(--accent-secondary));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            font-weight: 700;
            font-size: 1.1rem;
            margin-bottom: 15px;
        }

        .footer-text {
            color: var(--text-secondary);
            font-size: 0.9rem;
        }

        /* --- Responsive --- */
        @media (max-width: 768px) {
            .hero-content h1 {
                font-size: 2.5rem;
            }
            
            .about-grid {
                grid-template-columns: 1fr;
            }

            .nav-links {
                display: none;
            }
            
            nav {
                justify-content: center;
            }
        }

        /* Desktop Layout for Stats (Side by Side) */
        @media (min-width: 769px) {
            .stats-grid {
                grid-template-columns: 1.2fr 0.8fr; /* Main stats bigger, top langs smaller */
            }
        }
    </style>
</head>
<body>

    <!-- Navigation -->
    <header>
        <div class="container">
            <nav>
                <div class="logo">NM.</div>
                <ul class="nav-links">
                    <li><a href="#about">About</a></li>
                    <li><a href="#stack">Tech Stack</a></li>
                    <li><a href="#stats">Stats</a></li>
                    <li><a href="#connect">Connect</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <main>
        <!-- Hero Section -->
        <section class="hero">
            <div class="container hero-content">
                <p style="color: var(--accent-primary); font-family: var(--font-code); margin-bottom: 10px;">Hi, my name is</p>
                <h1>Nimesh Maduranga.</h1>
                <div class="typewriter">
                    I build <span id="typing-text"></span><span class="cursor">&nbsp;</span>
                </div>
                
                <div class="hero-btns">
                    <a href="#connect" class="btn btn-primary">Contact Me</a>
                    <a href="https://nimeshmaduranga-hub.github.io/MyWebsite/" target="_blank" class="btn btn-outline">Portfolio</a>
                </div>
            </div>
        </section>

        <!-- About Section -->
        <section id="about">
            <div class="container">
                <h2 class="section-title">About Me</h2>
                <div class="about-grid">
                    <div class="about-text">
                        <div class="location-badge">
                            <i class="fas fa-map-marker-alt"></i> Sri Lanka 🇱🇰
                        </div>
                        <p>I’m a developer who loves turning ideas into real-world web applications. I enjoy clean UI design, smooth user experiences, and writing scalable backend logic. Always learning, always building.</p>
                        <p>I am currently working as a <strong>Full Stack Developer</strong>, passionate about building modern web apps that solve real problems.</p>
                    </div>
                    
                    <div class="card">
                        <h3 style="margin-bottom: 20px;">🚀 Goals</h3>
                        <ul class="goals-list">
                            <li><i class="fas fa-check-circle"></i> Build scalable SaaS applications</li>
                            <li><i class="fas fa-check-circle"></i> Improve backend architecture skills</li>
                            <li><i class="fas fa-check-circle"></i> Contribute more to open source</li>
                            <li><i class="fas fa-check-circle"></i> Grow as a Full Stack Engineer</li>
                        </ul>
                    </div>
                </div>
            </div>
        </section>

        <!-- Tech Stack -->
        <section id="stack">
            <div class="container">
                <h2 class="section-title">Tech Stack</h2>
                <div class="tech-grid">
                    <!-- Tech Items -->
                    <div class="tech-item"><i class="fab fa-html5" style="color: #e34c26;"></i> HTML5</div>
                    <div class="tech-item"><i class="fab fa-css3-alt" style="color: #264de4;"></i> CSS3</div>
                    <div class="tech-item"><i class="fab fa-js" style="color: #f0db4f;"></i> JavaScript</div>
                    <div class="tech-item"><i class="fab fa-java" style="color: #f89820;"></i> Java</div>
                    <div class="tech-item"><i class="fas fa-database" style="color: #00758f;"></i> MySQL</div>
                    <div class="tech-item"><i class="fab fa-git-alt" style="color: #f05032;"></i> Git</div>
                </div>
            </div>
        </section>

        <!-- GitHub Stats Section (Updated Layout) -->
        <section id="stats">
            <div class="container">
                <h2 class="section-title" style="text-align: center; display: block;">GitHub Stats</h2>
                <div class="stats-wrapper">
                    
                    <!-- Grid for Main Stats & Top Languages -->
                    <div class="stats-grid">
                        <!-- General Stats -->
                        <div class="stat-card">
                            <img src="https://github-readme-stats.vercel.app/api?username=NimeshMaduranga-hub&show_icons=true&theme=highcontrast" alt="GitHub Stats">
                        </div>
                        
                        <!-- Top Languages -->
                        <div class="stat-card">
                            <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=NimeshMaduranga-hub&layout=compact&theme=highcontrast" alt="Top Languages">
                        </div>
                    </div>

                    <!-- Streak Stats (Full Width) -->
                    <div class="stat-card" style="max-width: 900px;">
                        <img src="https://streak-stats.demolab.com/?user=NimeshMaduranga-hub&theme=highcontrast" alt="GitHub Streak">
                    </div>

                </div>
            </div>
        </section>

        <!-- Connect Section -->
        <section id="connect">
            <div class="container">
                <h2 class="section-title">Connect With Me</h2>
                <div class="connect-grid">
                    <!-- Portfolio -->
                    <a href="https://nimeshmaduranga-hub.github.io/MyWebsite/" target="_blank" class="connect-card">
                        <i class="fas fa-globe"></i>
                        <h3>Portfolio</h3>
                        <p>View my website</p>
                    </a>
                    <!-- LinkedIn -->
                    <a href="https://linkedin.com/in/nimesh-maduranga-97130831a" target="_blank" class="connect-card">
                        <i class="fab fa-linkedin"></i>
                        <h3>LinkedIn</h3>
                        <p>Let's connect professionally</p>
                    </a>
                    <!-- Twitter -->
                    <a href="https://twitter.com/NimeshMadu97252" target="_blank" class="connect-card">
                        <i class="fab fa-twitter"></i>
                        <h3>Twitter</h3>
                        <p>Follow my thoughts</p>
                    </a>
                    <!-- YouTube -->
                    <a href="https://youtube.com/channel/Quickcuttube" target="_blank" class="connect-card">
                        <i class="fab fa-youtube"></i>
                        <h3>YouTube</h3>
                        <p>Check out my channel</p>
                    </a>
                </div>
            </div>
        </section>
    </main>

    <!-- Footer -->
    <footer>
        <div class="container">
            <p class="fun-fact">✨ Fun Fact: I love turning coffee ☕ into code 💻</p>
            <p class="footer-text">⭐ Feel free to star my repositories if you like my work!</p>
            <p class="footer-text" style="margin-top: 10px;">&copy; 2023 Nimesh Maduranga. All Rights Reserved.</p>
        </div>
    </footer>

    <!-- Minimal JS for Typing Effect -->
    <script>
        const textElement = document.getElementById('typing-text');
        const phrases = [
            "Full Stack Developer",
            "Frontend Enthusiast",
            "Java | JavaScript Lover",
            "Always Learning New Things"
        ];
        
        let phraseIndex = 0;
        let charIndex = 0;
        let isDeleting = false;
        let typeSpeed = 100;

        function type() {
            const currentPhrase = phrases[phraseIndex];
            
            if (isDeleting) {
                textElement.textContent = currentPhrase.substring(0, charIndex - 1);
                charIndex--;
                typeSpeed = 50; 
            } else {
                textElement.textContent = currentPhrase.substring(0, charIndex + 1);
                charIndex++;
                typeSpeed = 100;
            }

            if (!isDeleting && charIndex === currentPhrase.length) {
                isDeleting = true;
                typeSpeed = 2000; // Pause at end
            } else if (isDeleting && charIndex === 0) {
                isDeleting = false;
                phraseIndex = (phraseIndex + 1) % phrases.length;
                typeSpeed = 500; // Pause before new word
            }

            setTimeout(type, typeSpeed);
        }

        document.addEventListener('DOMContentLoaded', type);
    </script>
</body>
</html>
