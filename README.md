<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Zeynep 🤍 Feridun</title>
    <style>
        * { margin: 0; padding: 0; box-sizing: border-box; }
        body, html { 
            height: 100%; background: #000; font-family: 'Segoe UI', Arial, sans-serif; 
            color: white; overflow-x: hidden;
        }

        /* Şifre Ekranı */
        #passwordScreen {
            position: fixed; top: 0; left: 0; width: 100%; height: 100%;
            background: linear-gradient(rgba(0,0,0,0.92), rgba(139,0,0,0.85));
            display: flex; flex-direction: column; align-items: center; justify-content: center;
            z-index: 100;
        }
        .title {
            text-align: center; margin-bottom: 50px;
        }
        .title .name {
            font-size: 3.6rem; line-height: 1.1; letter-spacing: 3px;
            text-shadow: 0 0 30px #ff3366;
        }
        .title .heart {
            font-size: 4rem; margin: 10px 0; color: #ff3366;
            text-shadow: 0 0 20px #ff0000;
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
        #mainContent { display: none; padding-bottom: 100px; }

        /* Düşen Küçük Kalpler */
        .hearts { 
            position: fixed; top: 0; left: 0; width: 100%; height: 100%; 
            pointer-events: none; z-index: 5; overflow: hidden; 
        }
        .heart {
            position: absolute; color: #ff3366; font-size: 1.8rem;
            animation: fall linear forwards; 
            text-shadow: 0 0 8px #ff0000;
            opacity: 0.9;
        }
        @keyframes fall {
            0% { transform: translateY(-80px) rotate(0deg); }
            100% { transform: translateY(110vh) rotate(25deg); }
        }

        /* YouTube */
        .video-container {
            width: 100%; max-width: 900px; margin: 30px auto; padding: 0 15px;
        }
        .video-container iframe {
            width: 100%; height: 480px; border-radius: 16px; box-shadow: 0 0 40px rgba(255,50,100,0.7);
        }

        /* Giriş Sözü */
        .intro-quote {
            text-align: center; max-width: 800px; margin: 30px auto; padding: 30px 20px;
            font-size: 1.85rem; line-height: 1.5; color: #ffd0d0;
            text-shadow: 0 0 20px #ff3366;
        }

        /* Fotoğraflar */
        .memory {
            width: 100%; max-width: 800px; margin: 40px auto; padding: 0 15px;
        }
        .memory img {
            width: 100%; border-radius: 16px; box-shadow: 0 10px 30px rgba(255,50,100,0.4);
            display: block;
        }
        .memory .quote {
            margin-top: 20px; text-align: center; font-size: 1.55rem; line-height: 1.45;
            padding: 20px; background: rgba(0,0,0,0.5); border-radius: 16px;
            color: #ffe6e6;
        }

        @media (max-width: 768px) {
            .title .name { font-size: 2.8rem; }
            .intro-quote { font-size: 1.5rem; }
            .memory .quote { font-size: 1.35rem; }
            .video-container iframe { height: 320px; }
        }
    </style>
</head>
<body>

    <!-- Şifre Ekranı -->
    <div id="passwordScreen">
        <div class="title">
            <div class="name">ZEYNEP</div>
            <div class="heart">🤍</div>
            <div class="name">FERIDUN</div>
        </div>
        <input type="password" id="passwordInput" placeholder="Şifreyi girin...">
        <button id="submitBtn">Giriş Yap ❤️</button>
        <div id="errorMsg">Yanlış şifre, tekrar dene.</div>
    </div>

    <!-- Ana İçerik -->
    <div id="mainContent">
        <div class="hearts" id="hearts"></div>

        <div class="video-container">
            <iframe src="https://www.youtube.com/embed/HQxmGjTV5TI?autoplay=1&loop=1&playlist=HQxmGjTV5TI" 
                    frameborder="0" allowfullscreen></iframe>
        </div>

        <div class="intro-quote">
            Sen geldin diye hayatım yeniden başladı.<br>
            Kalbimi çıkardım, yerine seninkini koydum.<br>
            Sen benim en güzel mucizemsin ❤️
        </div>

        <!-- Fotoğraflar -->
        <div class="memory">
            <img src="IMG-20260215-WA0026.jpg" alt="">
            <div class="quote">Seninle her bakışım, kalbimin en güzel şiirini yazıyor.</div>
        </div>

        <div class="memory">
            <img src="1000107558.jpg" alt="">   <!-- Yeni eklediğin siyah-beyaz fotoğraf -->
            <div class="quote">Gözlerinle kalbime dokunduğun her an, dünyam daha güzel oluyor.<br>Seni sevmek en masum mutluluğum.</div>
        </div>

        <div class="memory">
            <img src="IMG-20260325-WA0012.jpg" alt="">
            <div class="quote">Yüzüne baktığımda zaman duruyor.<br>Sen benim en derin sessizliğim ve en güzel fırtınamsın.</div>
        </div>

        <div class="memory">
            <img src="IMG-20260325-WA0021.jpg" alt="">
            <div class="quote">Gözlerin benim için en güzel yıldızlar.<br>Seninle her an kendimi daha çok buluyorum.</div>
        </div>

        <div class="memory">
            <img src="IMG-20260402-WA0001.jpg" alt="">
            <div class="quote">Senin yanında olmak dünyanın en güvenli yeri.<br>Kalbim sadece seninle atıyor.</div>
        </div>

        <div class="memory">
            <img src="IMG-20260407-WA0000.jpg" alt="">
            <div class="quote">Seni sevmek, her gün yeni bir bahar açmak gibi.<br>Kalbimi sana adadım.</div>
        </div>

        <div class="memory">
            <img src="IMG-20260411-WA0001.jpg" alt="">
            <div class="quote">Sonsuza kadar seninle...<br>Sen benim her şeyimsin.<br>Zeynep 🤍 Feridun</div>
        </div>

        <audio id="bgMusic" loop autoplay>
            <source src="music.mp3" type="audio/mpeg">
        </audio>
    </div>

    <script>
        document.getElementById('submitBtn').addEventListener('click', () => {
            if (document.getElementById('passwordInput').value === "ZeynepFeridun") {
                document.getElementById('passwordScreen').style.display = 'none';
                document.getElementById('mainContent').style.display = 'block';

                const music = document.getElementById('bgMusic');
                music.volume = 0.68;
                music.play().catch(() => {});
            } else {
                document.getElementById('errorMsg').style.display = 'block';
                setTimeout(() => document.getElementById('errorMsg').style.display = 'none', 3000);
            }
        });

        document.getElementById('passwordInput').addEventListener('keypress', (e) => {
            if (e.key === 'Enter') document.getElementById('submitBtn').click();
        });

        // Düşen küçük kalpler
        function createHeart() {
            const heart = document.createElement('div');
            heart.className = 'heart';
            heart.textContent = '❤️';
            heart.style.left = Math.random() * 100 + 'vw';
            heart.style.fontSize = (Math.random() * 18 + 14) + 'px';
            heart.style.animationDuration = (Math.random() * 12 + 14) + 's';
            heart.style.opacity = Math.random() * 0.6 + 0.7;
            document.getElementById('hearts').appendChild(heart);
            setTimeout(() => heart.remove(), 28000);
        }
        setInterval(createHeart, 280);
    </script>
</body>
</html>
