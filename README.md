<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Grumio - $TENETTE</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Arial', sans-serif;
            background: #000;
            color: #fff;
            overflow-x: hidden;
        }

        /* Rainbow text effect */
        .rainbow-text {
            background: linear-gradient(45deg, #ff0000, #ff8000, #ffff00, #00ff00, #00ffff, #0000ff, #8000ff, #ff00ff);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-size: 400% 400%;
            animation: rainbow 3s ease infinite;
        }

        @keyframes rainbow {
            0% { background-position: 0% 50% }
            50% { background-position: 100% 50% }
            100% { background-position: 0% 50% }
        }

        /* Glow text effect */
        .glow-text {
            text-shadow: 0 0 10px #ff0000, 0 0 20px #ff0000, 0 0 30px #ff0000;
        }

        /* Header styles */
        header {
            position: fixed;
            top: 0;
            width: 100%;
            background: rgba(0, 0, 0, 0.9);
            backdrop-filter: blur(10px);
            z-index: 1000;
            padding: 15px 0;
            border-bottom: 2px solid #ff0000;
        }

        .nav-container {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 0 20px;
        }

        .logo {
            font-size: 2rem;
            font-weight: bold;
            color: #ff0000;
        }

        .nav-menu {
            display: flex;
            gap: 30px;
        }

        .nav-menu a {
            color: #fff;
            text-decoration: none;
            font-weight: bold;
            transition: color 0.3s;
        }

        .nav-menu a:hover {
            color: #ff0000;
        }

        .buy-button {
            background: linear-gradient(45deg, #8B0000, #B22222);
            color: white;
            border: none;
            padding: 12px 25px;
            border-radius: 25px;
            font-weight: bold;
            cursor: pointer;
            text-decoration: none;
            transition: transform 0.3s;
            font-size: 1.1rem;
        }

        .buy-button:hover {
            transform: scale(1.05);
            background: linear-gradient(45deg, #B22222, #FF0000);
        }

        /* Hero section */
        .hero {
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            padding: 100px 20px 50px;
            background: linear-gradient(135deg, #0a0a0a 0%, #2e1a1a 50%, #3e1616 100%);
        }

        .hero h1 {
            font-size: 4rem;
            margin-bottom: 20px;
            text-transform: uppercase;
        }

        .hero-image {
            max-width: 300px;
            margin: 30px 0;
            border-radius: 20px;
            border: 3px solid #ff0000;
            box-shadow: 0 0 30px #ff0000;
        }

        /* Sections */
        section {
            padding: 80px 20px;
            max-width: 1200px;
            margin: 0 auto;
        }

        .section-title {
            font-size: 3rem;
            text-align: center;
            margin-bottom: 30px;
            text-transform: uppercase;
        }

        .section-subtitle {
            font-size: 2rem;
            text-align: center;
            margin-bottom: 40px;
        }

        /* About section */
        .about-content {
            text-align: center;
            font-size: 1.2rem;
            line-height: 1.6;
            max-width: 800px;
            margin: 0 auto;
        }

        /* Infinite scroller */
        .infinite-scroller {
            margin: 50px 0;
            overflow: hidden;
            position: relative;
        }

        .scroller-track {
            display: flex;
            animation: scroll 40s linear infinite;
        }

        .scroller-track:hover {
            animation-play-state: paused;
        }

        .scroller-item {
            flex: 0 0 auto;
            width: 200px;
            height: 200px;
            margin: 0 10px;
            border-radius: 15px;
            overflow: hidden;
            border: 2px solid #ff0000;
            background: #333; /* Placeholder background */
            display: flex;
            align-items: center;
            justify-content: center;
            color: #fff;
            font-weight: bold;
        }

        @keyframes scroll {
            0% { transform: translateX(0); }
            100% { transform: translateX(-50%); }
        }

        /* Features grid */
        .features {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            margin-top: 50px;
        }

        .feature-card {
            background: rgba(255, 255, 255, 0.1);
            padding: 30px;
            border-radius: 15px;
            text-align: center;
            border: 1px solid #ff0000;
            transition: transform 0.3s;
        }

        .feature-card:hover {
            transform: translateY(-10px);
        }

        .feature-title {
            font-size: 1.5rem;
            margin-bottom: 15px;
            color: #ff0000;
        }

        /* Meme gallery */
        .meme-gallery {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            margin-top: 50px;
        }

        .meme-item {
            border-radius: 15px;
            overflow: hidden;
            border: 2px solid #ff0000;
            transition: transform 0.3s;
            background: #333; /* Placeholder background */
            height: 250px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: #fff;
            font-weight: bold;
        }

        .meme-item:hover {
            transform: scale(1.05);
        }

        /* Buy section */
        .buy-section {
            text-align: center;
            background: linear-gradient(135deg, #2e1a1a 0%, #3e1616 100%);
            border-radius: 20px;
            padding: 60px 40px;
            margin-top: 50px;
            border: 2px solid #ff0000;
        }

        /* Footer */
        footer {
            background: #0a0a0a;
            padding: 40px 20px;
            text-align: center;
            border-top: 2px solid #ff0000;
        }

        .footer-content {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            gap: 20px;
        }

        /* Responsive */
        @media (max-width: 768px) {
            .nav-container {
                flex-direction: column;
                gap: 15px;
            }

            .nav-menu {
                gap: 15px;
            }

            .hero h1 {
                font-size: 2.5rem;
            }

            .section-title {
                font-size: 2rem;
            }

            .section-subtitle {
                font-size: 1.5rem;
            }

            .footer-content {
                flex-direction: column;
            }
        }

        /* Battle cry */
        .battle-cry {
            font-size: 3rem;
            color: #ff0000;
            text-align: center;
            margin: 30px 0;
            animation: pulse 2s infinite;
            text-transform: uppercase;
        }

        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.1); }
            100% { transform: scale(1); }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <div class="nav-container">
            <div class="logo rainbow-text">GRUMIO</div>
            <nav class="nav-menu">
                <a href="#about">ABOUT</a>
                <a href="#features">FEATURES</a>
                <a href="#buy">BUY</a>
                <a href="#memes">MEMES</a>
            </nav>
            <a href="https://pump.fun/" class="buy-button">BUY $TENETTE</a>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero">
        <h1 class="rainbow-text">GRUMIO</h1>
        <div class="battle-cry">INCREDIBILIS!</div>
        <div class="hero-image">
            <!-- Placeholder for Grumio image -->
            <div style="color: white; font-size: 1.2rem;">GRUMIO IMAGE</div>
        </div>
    </section>

    <!-- About Section -->
    <section id="about">
        <h2 class="section-title rainbow-text">About</h2>
        <h3 class="section-subtitle glow-text">$TENETTE</h3>
        <div class="about-content">
            <p>INCREDIBILIS! The legendary knight of pure, unadulterated chaos has arrived on Solana.</p>
            <br>
            <p>$TENETTE is the embodiment of the "RAH!" energy in your portfolio. No strategy, no utility, 
            only pure, incredibilis strength. Contract renounced. No taxes. Just vibes and shoulder bashes.</p>
            <br>
            <p>When weak hands paper-hand their bags, true warriors scream "INCREDIBILIS!" and hold through the chaos.</p>
        </div>

        <!-- Infinite Scroller -->
        <div class="infinite-scroller">
            <div class="scroller-track">
                <div class="scroller-item">GRUMIO MEME 1</div>
                <div class="scroller-item">GRUMIO MEME 2</div>
                <div class="scroller-item">GRUMIO MEME 3</div>
                <div class="scroller-item">GRUMIO MEME 4</div>
                <div class="scroller-item">GRUMIO MEME 5</div>
                <div class="scroller-item">GRUMIO MEME 6</div>
            </div>
        </div>
    </section>

    <!-- Features Section -->
    <section id="features">
        <h2 class="section-title rainbow-text">Warrior Features</h2>
        <div class="features">
            <div class="feature-card">
                <h3 class="feature-title">0% TAX</h3>
                <p>No taxes, no surrender. Pure battle energy only.</p>
            </div>
            <div class="feature-card">
                <h3 class="feature-title">CONTRACT RENOUNCED</h3>
                <p>Fully decentralized. No retreat, no surrender.</p>
            </div>
            <div class="feature-card">
                <h3 class="feature-title">BATTLE TESTED</h3>
                <p>By warriors, for warriors. INCREDIBILIS!</p>
            </div>
        </div>
    </section>

    <!-- Buy Section -->
    <section id="buy">
        <div class="buy-section">
            <h2 class="section-title rainbow-text">Join The Battle!</h2>
            <h3 class="section-subtitle glow-text">BUY $TENETTE</h3>
            <div class="about-content">
                <p>Ready to scream INCREDIBILIS? Buy $TENETTE on Pump.fun and join the legendary warriors.</p>
                <br>
                <p>Connect your wallet, swap SOL for $TENETTE, and prepare for battle!</p>
                <br>
                <a href="https://pump.fun/" class="buy-button" style="font-size: 1.3rem; padding: 15px 30px;">BUY $TENETTE NOW</a>
            </div>
        </div>
    </section>

    <!-- Memes Section -->
    <section id="memes">
        <h2 class="section-title rainbow-text">Warrior Memes</h2>
        <div class="meme-gallery">
            <div class="meme-item">MEME 1</div>
            <div class="meme-item">MEME 2</div>
            <div class="meme-item">MEME 3</div>
            <div class="meme-item">MEME 4</div>
            <div class="meme-item">MEME 5</div>
            <div class="meme-item">MEME 6</div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="footer-content">
            <div class="logo rainbow-text">GRUMIO</div>
            <div class="battle-cry" style="font-size: 1.5rem;">INCREDIBILIS!</div>
        </div>
    </footer>

    <script>
        // Smooth scrolling for navigation links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                }
            });
        });

        // Header background on scroll
        window.addEventListener('scroll', function() {
            const header = document.querySelector('header');
            if (window.scrollY > 100) {
                header.style.background = 'rgba(0, 0, 0, 0.95)';
            } else {
                header.style.background = 'rgba(0, 0, 0, 0.9)';
            }
        });

        // Add floating animation to hero image
        const heroImage = document.querySelector('.hero-image');
        if (heroImage) {
            setInterval(() => {
                heroImage.style.transform = `translateY(${Math.sin(Date.now() / 1000) * 10}px)`;
            }, 50);
        }

        // Battle cry animation
        const battleCry = document.querySelector('.battle-cry');
        if (battleCry) {
            setInterval(() => {
                battleCry.style.textShadow = `0 0 20px rgba(255, 0, 0, ${0.5 + Math.random() * 0.5})`;
            }, 500);
        }
    </script>
</body>
</html>
