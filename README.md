<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Zeynep & Feridun ❤️</title>
    <style>
        * { margin: 0; padding: 0; box-sizing: border-box; }
        body, html { 
            height: 100%; overflow: hidden; background: #000; 
            font-family: 'Segoe UI', Arial, sans-serif; 
            color: white;
        }

        /* Şifre Ekranı */
        #passwordScreen {
            position: fixed; top: 0; left: 0; width: 100%; height: 100%;
            background: linear-gradient(rgba(0,0,0,0.9), rgba(0,0,0,0.95));
            display: flex; flex-direction: column; align-items: center; justify-content: center;
            z-index: 100;
        }
        #passwordScreen h1 { font-size: 3rem; margin-bottom: 40px; }
        #passwordInput {
            padding: 18px 30px; font-size: 1.4rem; width: 300px; text-align: center;
            background: rgba(255,255,255,0.1); border: 2px solid #ff4d94; border-radius: 50px;
            color: white; outline: none;
        }
        #submitBtn {
            margin-top: 25px; padding: 14px 50px; font-size: 1.3rem;
            background: #ff4d94; border: none; border-radius: 50px; color: white; cursor: pointer;
        }
        #errorMsg { color: #ff6666; margin-top: 20px; display: none; }

        /* Ana İçerik */
        #mainContent { display: none; height: 100%; position: relative; }

        .slideshow {
            position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: 1;
        }
        .slide {
            position: absolute; top: 0; left: 0; width: 100%; height: 100%;
            background-size: cover; background-position: center;
            opacity: 0; transition: opacity 3s ease-in-out;
        }
        .slide.active { opacity: 1; z-index: 2; }

        .overlay {
            position: absolute; top: 0; left: 0; width: 100%; height: 100%;
            background: linear-gradient(to bottom, rgba(0,0,0,0.3), rgba(0,0,0,0.75));
            z-index: 3;
        }

        .content {
            position: absolute; top: 50%; left: 50%; transform: translate(-50%, -50%);
            text-align: center; z-index: 5;
        }
        .content h1 {
            font-size: 4.2rem; margin-bottom: 10px; 
            text-shadow: 0 0 30px rgba(255, 105, 180, 0.9);
        }
        .content p {
            font-size: 1.8rem; font-weight: 300;
            text-shadow: 0 0 20px rgba(0,0,0,0.8);
        }

        .hearts {
            position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: 4;
            pointer-events: none; overflow: hidden;
        }

        .music {
            position: fixed; bottom: 30px; right: 30px; z-index: 10;
        }

        @media (max-width: 768px) {
            .content h1 { font-size: 3rem; }
            .content p { font-size: 1.5rem; }
        }
    </style>
</head>
<body>

    <!-- Şifre Ekranı -->
    <div id="passwordScreen">
        <h1>Zeynep & Feridun ❤️</h1>
        <input type="password" id="passwordInput" placeholder="Şifreyi gir...">
        <button id="submitBtn">Giriş Yap</button>
        <div id="errorMsg">Yanlış şifre! Tekrar dene.</div>
    </div>

    <!-- Ana Slayt Gösterisi -->
    <div id="mainContent">
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

        <div class="content">
            <h1>Zeynep & Feridun</h1>
            <p>Kalbimi Koydum Sana ❤️</p>
        </div>

        <!-- Kalp Animasyonu -->
        <div class="hearts" id="hearts"></div>

        <div class="music">
            <audio id="bgMusic" loop>
                <source src="music.mp3" type="audio/mpeg">
            </audio>
        </div>
    </div>

    <script>
        const correctPassword = "ZeynepFeridun";
        
        // Şifre Kontrolü
        document.getElementById('submitBtn').addEventListener('click', () => {
            const input = document.getElementById('passwordInput').value;
            if (input === correctPassword) {
                document.getElementById('passwordScreen').style.display = 'none';
                document.getElementById('mainContent').style.display = 'block';
                document.getElementById('bgMusic').play();
            } else {
                const error = document.getElementById('errorMsg');
                error.style.display = 'block';
                setTimeout(() => error.style.display = 'none', 3000);
            }
        });

        // Slayt Gösterisi
        const slides = document.querySelectorAll('.slide');
        let current = 0;
        setInterval(() => {
            slides[current].classList.remove('active');
            current = (current + 1) % slides.length;
            slides[current].classList.add('active');
        }, 5200);

        // Kalp Animasyonu (MehmetVeGulsum tarzı)
        function createHeart() {
            const heart = document.createElement('div');
            heart.textContent = '❤️';
            heart.style.position = 'absolute';
            heart.style.left = Math.random() * 100 + 'vw';
            heart.style.fontSize = Math.random() * 25 + 20 + 'px';
            heart.style.opacity = Math.random() * 0.7 + 0.4;
            heart.style.animation = `float ${Math.random() * 8 + 10}s linear forwards`;
            document.getElementById('hearts').appendChild(heart);

            setTimeout(() => heart.remove(), 18000);
        }

        setInterval(createHeart, 400);

        // Kalp animasyon CSS
        const style = document.createElement('style');
        style.innerHTML = `
            @keyframes float {
                0% { transform: translateY(100vh) rotate(0deg); opacity: 0.9; }
                100% { transform: translateY(-100vh) rotate(25deg); opacity: 0; }
            }
        `;
        document.head.appendChild(style);

        // Müzik
        const music = document.getElementById('bgMusic');
        music.volume = 0.7;
    </script>
</body>
</html>
