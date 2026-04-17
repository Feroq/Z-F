<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Zeynep 🤍 Feridun</title>
    <style>
        * { margin: 0; padding: 0; box-sizing: border-box; }
        body, html { height: 100%; overflow-x: hidden; background: #000; font-family: 'Segoe UI', Arial, sans-serif; color: white; }

        /* Şifre Giriş Ekranı */
        #passwordScreen {
            position: fixed; top: 0; left: 0; width: 100%; height: 100%;
            background: linear-gradient(rgba(0,0,0,0.85), rgba(139,0,0,0.7));
            display: flex; flex-direction: column; align-items: center; justify-content: center;
            z-index: 100; transition: opacity 1s;
        }
        #passwordScreen h1 {
            font-size: 4.5rem; margin-bottom: 40px; letter-spacing: 4px;
            text-shadow: 0 0 30px #ff3366;
        }
        #passwordInput {
            padding: 18px 30px; font-size: 1.5rem; width: 320px; text-align: center;
            background: rgba(255,255,255,0.1); border: 3px solid #ff4d94; border-radius: 50px;
            color: white; outline: none;
        }
        #submitBtn {
            margin-top: 30px; padding: 15px 60px; font-size: 1.4rem;
            background: #ff3366; border: none; border-radius: 50px; color: white; cursor: pointer;
        }
        #errorMsg { color: #ff9999; margin-top: 20px; font-size: 1.2rem; display: none; }

        /* Ana İçerik */
        #mainContent { display: none; min-height: 100vh; position: relative; }

        /* YouTube Videosu - Üstte */
        .video-container {
            position: relative; width: 100%; max-width: 900px; margin: 40px auto 30px; padding: 0 20px;
            z-index: 5;
        }
        .video-container iframe {
            width: 100%; height: 500px; border-radius: 15px; box-shadow: 0 0 40px rgba(255, 50, 100, 0.6);
        }

        /* Slayt Gösterisi - Alta */
        .slideshow {
            position: relative; width: 100%; height: 80vh; overflow: hidden;
        }
        .slide {
            position: absolute; top: 0; left: 0; width: 100%; height: 100%;
            background-size: cover; background-position: center;
            opacity: 0; transition: opacity 3s ease;
        }
        .slide.active { opacity: 1; }

        .overlay {
            position: absolute; top: 0; left: 0; width: 100%; height: 100%;
            background: linear-gradient(to bottom, rgba(0,0,0,0.4), rgba(139,0,0,0.6));
        }

        .title {
            position: absolute; top: 50%; left: 50%; transform: translate(-50%, -50%);
            text-align: center; z-index: 6; text-shadow: 0 0 25px #ff3366;
        }
        .title h1 {
            font-size: 4rem; margin-bottom: 10px;
        }
        .title p {
            font-size: 1.8rem;
        }

        /* Düşen Kırmızı Güller */
        .roses {
            position: fixed; top: 0; left: 0; width: 100%; height: 100%; pointer-events: none; z-index: 4; overflow: hidden;
        }
        .rose {
            position: absolute; color: #ff3366; font-size: 2.5rem; opacity: 0.9;
            animation: fall linear forwards;
            text-shadow: 0 0 10px #ff0000;
        }

        @keyframes fall {
            0% { transform: translateY(-100px) rotate(0deg); }
            100% { transform: translateY(110vh) rotate(360deg); }
        }

        @media (max-width: 768px) {
            #passwordScreen h1 { font-size: 3rem; }
            .title h1 { font-size: 2.8rem; }
            .video-container iframe { height: 320px; }
        }
    </style>
</head>
<body>

    <!-- Şifre Giriş Ekranı -->
    <div id="passwordScreen">
        <h1>ZEYNEP 🤍 FERIDUN</h1>
        <input type="password" id="passwordInput" placeholder="Şifreyi girin...">
        <button id="submitBtn">Giriş Yap ❤️</button>
        <div id="errorMsg">Yanlış şifre, tekrar dene.</div>
    </div>

    <!-- Ana İçerik -->
    <div id="mainContent">
        <!-- Düşen Kırmızı Güller -->
        <div class="roses" id="roses"></div>

        <!-- YouTube Videosu -->
        <div class="video-container">
            <iframe src="https://www.youtube.com/embed/HQxmGjTV5TI?autoplay=1&loop=1&playlist=HQxmGjTV5TI" 
                    title="Kalbimi Koydum" frameborder="0" 
                    allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
                    allowfullscreen></iframe>
        </div>

        <!-- Slayt Gösterisi + Başlık -->
        <div class="slideshow" id="slideshow">
            <div class="slide active" style="background-image: url('images/1.jpg');"></div>
            <div class="slide" style="background-image: url('images/2.jpg');"></div>
            <div class="slide" style="background-image: url('images/3.jpg');"></div>
            <div class="slide" style="background-image: url('images/4.jpg');"></div>
            <div class="slide" style="background-image: url('images/5.jpg');"></div>
            <div class="slide" style="background-image: url('images/6.jpg');"></div>
            <div class="slide" style="background-image: url('images/1.jpg');"></div>
        </div>
        <div class="overlay"></div>

        <div class="title">
            <h1>ZEYNEP 🤍 FERIDUN</h1>
            <p>Kalbimi Koydum Sana ❤️</p>
        </div>

        <!-- Müzik -->
        <audio id="bgMusic" loop>
            <source src="music.mp3" type="audio/mpeg">
        </audio>
    </div>

    <script>
        const correctPass = "ZeynepFeridun";

        // Şifre Kontrolü
        document.getElementById('submitBtn').addEventListener('click', () => {
            if (document.getElementById('passwordInput').value === correctPass) {
                document.getElementById('passwordScreen').style.opacity = '0';
                setTimeout(() => {
                    document.getElementById('passwordScreen').style.display = 'none';
                    document.getElementById('mainContent').style.display = 'block';
                    document.getElementById('bgMusic').play().catch(() => {});
                }, 800);
            } else {
                const err = document.getElementById('errorMsg');
                err.style.display = 'block';
                setTimeout(() => err.style.display = 'none', 3000);
            }
        });

        // Enter tuşu ile giriş
        document.getElementById('passwordInput').addEventListener('keypress', (e) => {
            if (e.key === 'Enter') document.getElementById('submitBtn').click();
        });

        // Düşen Kırmızı Güller Animasyonu
        function createRose() {
            const rose = document.createElement('div');
            rose.classList.add('rose');
            rose.textContent = '🌹';
            rose.style.left = Math.random() * 100 + 'vw';
            rose.style.fontSize = (Math.random() * 30 + 25) + 'px';
            rose.style.animationDuration = (Math.random() * 8 + 10) + 's';
            rose.style.opacity = Math.random() * 0.7 + 0.6;
            document.getElementById('roses').appendChild(rose);

            setTimeout(() => rose.remove(), 20000);
        }
        setInterval(createRose, 280);

        // Slayt Gösterisi
        const slides = document.querySelectorAll('.slide');
        let currentSlide = 0;
        setInterval(() => {
            slides[currentSlide].classList.remove('active');
            currentSlide = (currentSlide + 1) % slides.length;
            slides[currentSlide].classList.add('active');
        }, 5200);

        // Müzik Ses Seviyesi
        const music = document.getElementById('bgMusic');
        music.volume = 0.68;
    </script>
</body>
</html>
