<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>GigaChad - $CHAD</title>
    <style>
        /* Reset and base styles */
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
            text-shadow: 0 0 10px #00ffff, 0 0 20px #00ffff, 0 0 30px #00ffff;
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
            border-bottom: 2px solid #00ffff;
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
            color: #00ffff;
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
            color: #00ffff;
        }

        .buy-button {
            background: linear-gradient(45deg, #ff0000, #ff8000);
            color: white;
            border: none;
            padding: 10px 20px;
            border-radius: 25px;
            font-weight: bold;
            cursor: pointer;
            text-decoration: none;
            transition: transform 0.3s;
        }

        .buy-button:hover {
            transform: scale(1.05);
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
            background: linear-gradient(135deg, #0a0a0a 0%, #1a1a2e 50%, #16213e 100%);
        }

        .hero h1 {
            font-size: 4rem;
            margin-bottom: 20px;
        }

        .hero-image {
            max-width: 300px;
            margin: 30px 0;
            border-radius: 20px;
            border: 3px solid #00ffff;
            box-shadow: 0 0 30px #00ffff;
        }

        .hero-links {
            display: flex;
            gap: 30px;
            margin-top: 20px;
            flex-wrap: wrap;
            justify-content: center;
        }

        .hero-links a {
            color: #00ffff;
            text-decoration: none;
            font-weight: bold;
            border: 1px solid #00ffff;
            padding: 10px 20px;
            border-radius: 25px;
            transition: all 0.3s;
        }

        .hero-links a:hover {
            background: #00ffff;
            color: #000;
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
            border: 2px solid #00ffff;
        }

        .scroller-item img {
            width: 100%;
            height: 100%;
            object-fit: cover;
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
            border: 1px solid #00ffff;
            transition: transform 0.3s;
        }

        .feature-card:hover {
            transform: translateY(-10px);
        }

        .feature-title {
            font-size: 1.5rem;
            margin-bottom: 15px;
            color: #00ffff;
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
            border: 2px solid #00ffff;
            transition: transform 0.3s;
        }

        .meme-item:hover {
            transform: scale(1.05);
        }

        .meme-item img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        /* Social section */
        .social-section {
            text-align: center;
            background: linear-gradient(135deg, #1a1a2e 0%, #16213e 100%);
            border-radius: 20px;
            padding: 60px 40px;
            margin-top: 50px;
        }

        /* Footer */
        footer {
            background: #0a0a0a;
            padding: 40px 20px;
            text-align: center;
            border-top: 2px solid #00ffff;
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

        /* Noise overlay */
        .noise-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" width="200" height="200" opacity="0.1"><filter id="a"><feTurbulence type="fractalNoise" baseFrequency="0.9" numOctaves="4" stitchTiles="stitch"/></filter><rect width="100%" height="100%" filter="url(%23a)"/></svg>');
            pointer-events: none;
            z-index: 9999;
            mix-blend-mode: overlay;
            opacity: 0.3;
        }
    </style>
</head>
<body>
    <div class="noise-overlay"></div>

    <!-- Header -->
    <header>
        <div class="nav-container">
            <div class="logo rainbow-text">GigaChad</div>
            <nav class="nav-menu">
                <a href="#about">ABOUT</a>
                <a href="#features">FEATURES</a>
                <a href="#buy">BUY</a>
                <a href="#memes">MEMES</a>
                <a href="#social">SOCIAL</a>
            </nav>
            <a href="#" class="buy-button">BUY $CHAD</a>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero">
        <h1 class="rainbow-text">GIGACHAD</h1>
        <img src="https://i.imgur.com/7QXZP4p.png" alt="GigaChad" class="hero-image">
        <div class="hero-links">
            <a href="#">DEXSCREENER</a>
            <a href="#">TWITTER</a>
            <a href="#">TELEGRAM</a>
            <a href="#">SOLSCAN</a>
        </div>
    </section>

    <!-- About Section -->
    <section id="about">
        <h2 class="section-title rainbow-text">About</h2>
        <h3 class="section-subtitle glow-text">$CHAD</h3>
        <div class="about-content">
            <p>GigaChad is not just a meme - it's a lifestyle. The ultimate symbol of peak performance, 
            unwavering confidence, and absolute dominance in the crypto space.</p>
            <br>
            <p>$CHAD represents the alpha mentality that separates winners from losers. While weak hands 
            paper-hand their bags, true Chads diamond-hand their way to financial freedom.</p>
            <br>
            <p>Zero tax, max gains. Contract renounced. No weak energy allowed.</p>
        </div>

        <!-- Infinite Scroller -->
        <div class="infinite-scroller">
            <div class="scroller-track">
                <div class="scroller-item">
                    <img src="https://i.imgur.com/7QXZP4p.png" alt="Chad 1">
                </div>
                <div class="scroller-item">
                    <img src="https://i.imgur.com/kEa2B3q.png" alt="Chad 2">
                </div>
                <div class="scroller-item">
                    <img src="https://i.imgur.com/mN8p7F2.png" alt="Chad 3">
                </div>
                <div class="scroller-item">
                    <img src="https://i.imgur.com/9rV8cL7.png" alt="Chad 4">
                </div>
                <div class="scroller-item">
                    <img src="https://i.imgur.com/7QXZP4p.png" alt="Chad 5">
                </div>
                <div class="scroller-item">
                    <img src="https://i.imgur.com/kEa2B3q.png" alt="Chad 6">
                </div>
            </div>
        </div>
    </section>

    <!-- Features Section -->
    <section id="features">
        <h2 class="section-title rainbow-text">Alpha Features</h2>
        <div class="features">
            <div class="feature-card">
                <h3 class="feature-title">0% TAX</h3>
                <p>No taxes, no bullsh*t. Pure alpha energy only.</p>
            </div>
            <div class="feature-card">
                <h3 class="feature-title">CONTRACT RENOUNCED</h3>
                <p>Fully decentralized. No rug pulls, Chad's honor.</p>
            </div>
            <div class="feature-card">
                <h3 class="feature-title">COMMUNITY OWNED</h3>
                <p>By the Chads, for the Chads. Always.</p>
            </div>
        </div>
    </section>

    <!-- Buy Section -->
    <section id="buy">
        <h2 class="section-title rainbow-text">Buy Sum</h2>
        <h3 class="section-subtitle glow-text">$CHAD</h3>
        <div class="about-content">
            <p>Join the alpha movement. Buy $CHAD on Pump.fun or any Solana DEX.</p>
            <br>
            <p>Connect your wallet, swap SOL for $CHAD, and start your journey to becoming a crypto Chad.</p>
            <br>
            <div style="display: flex; gap: 20px; justify-content: center; flex-wrap: wrap; margin-top: 30px;">
                <a href="#" class="buy-button">BUY $CHAD</a>
                <a href="#" class="buy-button">VIEW CHART</a>
            </div>
        </div>
    </section>

    <!-- Memes Section -->
    <section id="memes">
        <h2 class="section-title rainbow-text">Chad Memes</h2>
        <div class="meme-gallery">
            <div class="meme-item">
                <img src="https://i.imgur.com/7QXZP4p.png" alt="Meme 1">
            </div>
            <div class="meme-item">
                <img src="https://i.imgur.com/kEa2B3q.png" alt="Meme 2">
            </div>
            <div class="meme-item">
                <img src="https://i.imgur.com/mN8p7F2.png" alt="Meme 3">
            </div>
            <div class="meme-item">
                <img src="https://i.imgur.com/9rV8cL7.png" alt="Meme 4">
            </div>
            <div class="meme-item">
                <img src="https://i.imgur.com/7QXZP4p.png" alt="Meme 5">
            </div>
            <div class="meme-item">
                <img src="https://i.imgur.com/kEa2B3q.png" alt="Meme 6">
            </div>
        </div>
    </section>

    <!-- Social Section -->
    <section id="social">
        <div class="social-section">
            <h2 class="section-title rainbow-text">Join The</h2>
            <h3 class="section-subtitle glow-text">CHAD ARMY</h3>
            <div class="about-content">
                <p>Follow us on social media, share memes, and help build the strongest community in crypto.</p>
                <br>
                <p>Weakness is not an option. Only diamond hands allowed.</p>
                <br>
                <a href="#" class="buy-button">FOLLOW ON TWITTER</a>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="footer-content">
            <div class="logo rainbow-text">GIGACHAD</div>
            <div>CONTACT@GIGACHAD.COM</div>
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
    </script>
</body>
</html>
