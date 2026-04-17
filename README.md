<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Zeynep🤍Feridun</title>
    <style>
        * { margin: 0; padding: 0; box-sizing: border-box; }
        body, html { height: 100%; overflow-x: hidden; background: #000; font-family: 'Segoe UI', Arial, sans-serif; color: white; }

        /* Şifre Giriş Ekranı */
        #passwordScreen {
            position: fixed; top: 0; left: 0; width: 100%; height: 100%;
            background: linear-gradient(rgba(0,0,0,0.9), rgba(139,0,0,0.8));
            display: flex; flex-direction: column; align-items: center; justify-content: center;
            z-index: 100; transition: opacity 1s;
        }
        #passwordScreen h1 {
            font-size: 4.2rem; margin-bottom: 30px; letter-spacing: 5px;
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

        /* YouTube Videosu */
        .video-container {
            position: relative; width: 100%; max-width: 900px; margin: 30px auto; padding: 0 20px; z-index: 6;
        }
        .video-container iframe {
            width: 100%; height: 480px; border-radius: 16px; box-shadow: 0 0 40px rgba(255, 50, 100, 0.7);
        }

        /* Slayt Gösterisi */
        .slideshow {
            position: relative; width: 100%; height: 85vh; overflow: hidden;
        }
        .slide {
            position: absolute; top: 0; left: 0; width: 100%; height: 100%;
            background-size: cover; background-position: center;
            opacity: 0; transition: opacity 3s ease;
        }
        .slide.active { opacity: 1; }

        .overlay {
            position: absolute; top: 0; left: 0; width: 100%; height: 100%;
            background: linear-gradient(to bottom, rgba(0,0,0,0.35), rgba(139,0,0,0.75));
            z-index: 4;
        }

        .quote {
            position: absolute; bottom: 15%; left: 50%; transform: translateX(-50%);
            text-align: center; z-index: 7; max-width: 90%; padding: 15px 25px;
            background: rgba(0,0,0,0.4); border-radius: 20px;
            font-size: 1.65rem; line-height: 1.4; text-shadow: 0 0 15px #ff3366;
        }

        /* Düşen Kırmızı Güller */
        .roses { position: fixed; top: 0; left: 0; width: 100%; height: 100%; pointer-events: none; z-index: 5; overflow: hidden; }

        .rose {
            position: absolute; color: #ff3366; font-size: 2.8rem; opacity: 0.85;
            animation: fall linear forwards; text-shadow: 0 0 12px #ff0000;
        }

        @keyframes fall {
            0% { transform: translateY(-120px) rotate(0deg); }
            100% { transform: translateY(110vh) rotate(420deg); }
        }

        @media (max-width: 768px) {
            #passwordScreen h1 { font-size: 3rem; }
            .quote { font-size: 1.35rem; }
            .video-container iframe { height: 320px; }
        }
    </style>
</head>
<body>

    <!-- Şifre Giriş Ekranı -->
    <div id="passwordScreen">
        <h1>ZEYNEP🤍FERIDUN</h1>
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

        <!-- Slayt Gösterisi + Fotoğraflara Özel Sözler -->
        <div class="slideshow" id="slideshow">
            <!-- 1. Aynada bej takım (zarif ve güçlü) -->
            <div class="slide active" style="background-image: url('images/1.jpg');"></div>
            <div class="quote">Seninle her bakışım, kalbimin en güzel şiirini yazıyor.<br>❤️</div>

            <!-- 2. Kırmızı elbise doğada (masum ve huzurlu) -->
            <div class="slide" style="background-image: url('images/2.jpg');"></div>
            <div class="quote">Gözlerinle doğan her sabah, hayatıma yeniden anlam katıyor.<br>Seni sevmek en büyük huzurum.</div>

            <!-- 3. Yatakta yakın yüz (samimi ve derin) -->
            <div class="slide" style="background-image: url('images/3.jpg');"></div>
            <div class="quote">Yüzüne baktığımda zaman duruyor.<br>Sen benim en derin sessizliğim ve en güzel fırtınamsın.</div>

            <!-- 4. Siyah başörtülü makyajlı portre (güçlü ve büyüleyici) -->
            <div class="slide" style="background-image: url('images/4.jpg');"></div>
            <div class="quote">Gözlerin benim için en güzel yıldızlar.<br>Seninle her an, kendimi daha çok buluyorum.</div>

            <!-- 5. Gri yelekli ayna selfie (modern ve kendine güvenen) -->
            <div class="slide" style="background-image: url('images/5.jpg');"></div>
            <div class="quote">Senin yanında olmak, dünyanın en güvenli yeri.<br>Kalbim seninle atıyor, ruhum seninle yaşıyor.</div>

            <!-- 6. Kırmızı gül buketi (mutluluk ve aşk dolu) -->
            <div class="slide" style="background-image: url('images/6.jpg');"></div>
            <div class="quote">Seni sevmek, her gün yeni bir bahar açmak gibi.<br>Kalbimi çıkardım, yerine seninkini koydum ❤️</div>

            <!-- 7. Tekrar 1. fotoğraf (kapanış) -->
            <div class="slide" style="background-image: url('images/1.jpg');"></div>
            <div class="quote">Sonsuza kadar seninle... Sen benim her şeyimsin.<br>Zeynep 🤍 Feridun</div>
        </div>
        <div class="overlay"></div>

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

        document.getElementById('passwordInput').addEventListener('keypress', (e) => {
            if (e.key === 'Enter') document.getElementById('submitBtn').click();
        });

        // Düşen Kırmızı Güller
        function createRose() {
            const rose = document.createElement('div');
            rose.classList.add('rose');
            rose.textContent = '🌹';
            rose.style.left = Math.random() * 100 + 'vw';
            rose.style.fontSize = (Math.random() * 35 + 25) + 'px';
            rose.style.animationDuration = (Math.random() * 9 + 11) + 's';
            document.getElementById('roses').appendChild(rose);
            setTimeout(() => rose.remove(), 22000);
        }
        setInterval(createRose, 250);

        // Slayt Gösterisi (her slayt 5.5 saniye)
        const slides = document.querySelectorAll('.slide');
        let current = 0;
        setInterval(() => {
            slides[current].classList.remove('active');
            current = (current + 1) % slides.length;
            slides[current].classList.add('active');
        }, 5500);

        const music = document.getElementById('bgMusic');
        music.volume = 0.7;
    </script>
</body>
</html>
