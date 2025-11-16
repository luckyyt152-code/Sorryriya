<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>I'm Sorry, My Love</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Georgia', serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            overflow-x: hidden;
        }

        /* Floating hearts animation */
        .heart {
            position: fixed;
            color: rgba(255, 255, 255, 0.3);
            font-size: 20px;
            animation: float 10s infinite;
            z-index: 1;
        }

        @keyframes float {
            0% {
                transform: translateY(100vh) rotate(0deg);
                opacity: 0;
            }
            10% {
                opacity: 1;
            }
            90% {
                opacity: 1;
            }
            100% {
                transform: translateY(-100vh) rotate(360deg);
                opacity: 0;
            }
        }

        /* Main container */
        .container {
            position: relative;
            z-index: 2;
            max-width: 800px;
            margin: 0 auto;
            padding: 40px 20px;
        }

        /* Hero section */
        .hero {
            text-align: center;
            color: white;
            margin-bottom: 60px;
            animation: fadeIn 1s ease-in;
        }

        @keyframes fadeIn {
            from {
                opacity: 0;
                transform: translateY(-20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .hero h1 {
            font-size: 3em;
            margin-bottom: 20px;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
        }

        .hero .subtitle {
            font-size: 1.5em;
            opacity: 0.9;
        }

        /* Letter section */
        .letter {
            background: white;
            border-radius: 20px;
            padding: 40px;
            margin: 40px 0;
            box-shadow: 0 20px 60px rgba(0,0,0,0.3);
            animation: slideUp 1s ease-out 0.5s both;
        }

        @keyframes slideUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .letter h2 {
            color: #764ba2;
            margin-bottom: 20px;
            font-size: 2em;
        }

        .letter p {
            color: #555;
            line-height: 1.8;
            font-size: 1.1em;
            margin-bottom: 15px;
        }

        /* Promises section */
        .promises {
            background: rgba(255, 255, 255, 0.95);
            border-radius: 20px;
            padding: 40px;
            margin: 40px 0;
            animation: slideUp 1s ease-out 1s both;
        }

        .promises h3 {
            color: #667eea;
            text-align: center;
            margin-bottom: 30px;
            font-size: 2em;
        }

        .promise-item {
            background: linear-gradient(135deg, #f093fb 0%, #f5576c 100%);
            color: white;
            padding: 20px;
            margin: 15px 0;
            border-radius: 15px;
            transform: translateX(-100%);
            animation: slideIn 0.8s ease-out forwards;
            box-shadow: 0 5px 15px rgba(0,0,0,0.2);
        }

        .promise-item:nth-child(2) { animation-delay: 1.3s; }
        .promise-item:nth-child(3) { animation-delay: 1.6s; }
        .promise-item:nth-child(4) { animation-delay: 1.9s; }
        .promise-item:nth-child(5) { animation-delay: 2.2s; }

        @keyframes slideIn {
            to {
                transform: translateX(0);
            }
        }

        /* Reasons section */
        .reasons {
            text-align: center;
            margin: 60px 0;
            animation: fadeIn 1s ease-out 2.5s both;
        }

        .reasons h3 {
            color: white;
            font-size: 2.5em;
            margin-bottom: 30px;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
        }

        .reason-cards {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            margin-top: 30px;
        }

        .reason-card {
            background: rgba(255, 255, 255, 0.9);
            padding: 25px;
            border-radius: 15px;
            transform: scale(0);
            animation: popIn 0.6s ease-out forwards;
            cursor: pointer;
            transition: transform 0.3s ease;
        }

        .reason-card:hover {
            transform: scale(1.05);
        }

        .reason-card:nth-child(1) { animation-delay: 3s; }
        .reason-card:nth-child(2) { animation-delay: 3.2s; }
        .reason-card:nth-child(3) { animation-delay: 3.4s; }
        .reason-card:nth-child(4) { animation-delay: 3.6s; }
        .reason-card:nth-child(5) { animation-delay: 3.8s; }
        .reason-card:nth-child(6) { animation-delay: 4s; }

        @keyframes popIn {
            to {
                transform: scale(1);
            }
        }

        .reason-card .icon {
            font-size: 2em;
            margin-bottom: 10px;
        }

        .reason-card p {
            color: #555;
            font-size: 1.1em;
        }

        /* Interactive button */
        .forgive-section {
            text-align: center;
            margin: 80px 0;
            animation: fadeIn 1s ease-out 4.5s both;
        }

        .forgive-btn {
            background: linear-gradient(135deg, #f093fb 0%, #f5576c 100%);
            color: white;
            border: none;
            padding: 20px 40px;
            font-size: 1.3em;
            border-radius: 50px;
            cursor: pointer;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            box-shadow: 0 10px 30px rgba(0,0,0,0.3);
        }

        .forgive-btn:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 40px rgba(0,0,0,0.4);
        }

        .forgive-btn:active {
            transform: translateY(-2px);
        }

        /* Hidden message */
        .hidden-message {
            display: none;
            text-align: center;
            margin: 40px 0;
            animation: fadeIn 1s ease;
        }

        .hidden-message.show {
            display: block;
        }

        .hidden-message h2 {
            color: white;
            font-size: 3em;
            margin-bottom: 20px;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
        }

        .big-heart {
            font-size: 5em;
            color: #ff6b6b;
            animation: pulse 1s infinite;
        }

        @keyframes pulse {
            0% {
                transform: scale(1);
            }
            50% {
                transform: scale(1.1);
            }
            100% {
                transform: scale(1);
            }
        }

        /* Footer */
        .footer {
            text-align: center;
            color: white;
            padding: 40px 0;
            font-size: 1.2em;
        }

        /* Responsive */
        @media (max-width: 600px) {
            .hero h1 {
                font-size: 2em;
            }
            
            .hero .subtitle {
                font-size: 1.2em;
            }
            
            .letter, .promises {
                padding: 25px;
            }
        }
    </style>
</head>
<body>
    <!-- Floating hearts background -->
    <div id="hearts-container"></div>

    <div class="container">
        <!-- Hero Section -->
        <div class="hero">
            <h1>I'm Sorry, My Love ❤️</h1>
            <p class="subtitle">This is for you, the most amazing person in my life</p>
        </div>

        <!-- Letter Section -->
        <div class="letter">
            <h2>My Dearest Riya,</h2>
            <p>
                I know I've made a mistake, and I can't stop thinking about how much I've hurt you. 
                You mean everything to me, and seeing you upset breaks my heart into a million pieces.
            </p>
            <p>
                I was wrong, and I take full responsibility for my actions. There's no excuse for what I did, 
                and I understand if you need time to forgive me. But please know that I'm truly, deeply sorry.
            </p>
            <p>
                You deserve so much better, and I promise to be the person you deserve. Your happiness 
                means the world to me, and I'll do whatever it takes to make things right.
            </p>
            <p>
                I love you more than words can express, and I'm committed to earning back your trust.
            </p>
            <p style="text-align: right; font-style: italic; margin-top: 30px;">
                Forever yours,<br>
                Nishidh
            </p>
        </div>

        <!-- Promises Section -->
        <div class="promises">
            <h3>My Promises to You 🤝</h3>
            <div class="promise-item">
                💕 I promise to listen to you more carefully and understand your feelings
            </div>
            <div class="promise-item">
                🌟 I promise to be more thoughtful and considerate in my actions
            </div>
            <div class="promise-item">
                🎁 I promise to make you feel special every single day
            </div>
            <div class="promise-item">
                💪 I promise to work on myself and become a better partner for you
            </div>
        </div>

        <!-- Reasons I Love You -->
        <div class="reasons">
            <h3>Reasons Why You're Amazing</h3>
            <div class="reason-cards">
                <div class="reason-card">
                    <div class="icon">😊</div>
                    <p>Your beautiful smile that lights up my world</p>
                </div>
                <div class="reason-card">
                    <div class="icon">💖</div>
                    <p>Your kind heart that makes everyone feel loved</p>
                </div>
                <div class="reason-card">
                    <div class="icon">🌺</div>
                    <p>Your grace and elegance in everything you do</p>
                </div>
                <div class="reason-card">
                    <div class="icon">✨</div>
                    <p>The way you make ordinary moments magical</p>
                </div>
                <div class="reason-card">
                    <div class="icon">🤗</div>
                    <p>Your warm hugs that make everything better</p>
                </div>
                <div class="reason-card">
                    <div class="icon">🎵</div>
                    <p>Your laugh that's my favorite sound</p>
                </div>
            </div>
        </div>

        <!-- Interactive Forgiveness Button -->
        <div class="forgive-section">
            <button class="forgive-btn" onclick="showLove()">
                Click Here to See How Much You Mean to Me 💕
            </button>
        </div>

        <!-- Hidden Message -->
        <div class="hidden-message" id="hiddenMessage">
            <div class="big-heart">❤️</div>
            <h2>Thank You for Being in My Life!</h2>
            <p style="color: white; font-size: 1.3em;">
                I promise to cherish every moment with you<br>
                and never take your love for granted again.
            </p>
        </div>

        <!-- Footer -->
        <div class="footer">
            <p>Made with all my love, just for you ❤️</p>
            <p style="margin-top: 10px; opacity: 0.8;">I'm truly sorry and I love you endlessly</p>
        </div>
    </div>

    <script>
        // Generate floating hearts
        function createHeart() {
            const heart = document.createElement('div');
            heart.className = 'heart';
            heart.innerHTML = '❤️';
            heart.style.left = Math.random() * 100 + 'vw';
            heart.style.animationDuration = Math.random() * 3 + 7 + 's';
            heart.style.fontSize = Math.random() * 20 + 15 + 'px';
            document.getElementById('hearts-container').appendChild(heart);

            setTimeout(() => {
                heart.remove();
            }, 10000);
        }

        // Create hearts periodically
        setInterval(createHeart, 1000);

        // Show hidden message
        function showLove() {
            document.getElementById('hiddenMessage').classList.add('show');
            
            // Scroll to the hidden message
            document.getElementById('hiddenMessage').scrollIntoView({ 
                behavior: 'smooth', 
                block: 'center' 
            });

            // Create explosion of hearts
            for(let i = 0; i < 20; i++) {
                setTimeout(createHeart, i * 100);
            }
        }

        // Add click sound effect (optional)
        document.querySelectorAll('.reason-card').forEach(card => {
            card.addEventListener('click', function() {
                this.style.animation = 'none';
                setTimeout(() => {
                    this.style.animation = 'popIn 0.6s ease-out forwards';
                }, 10);
            });
        });

        // Personalization tip alert
        window.addEventListener('load', function() {
            setTimeout(() => {
                console.log("💡 Tip: Don't forget to personalize this with specific details about your relationship!");
            }, 3000);
        });
    </script>
</body>
</html>
