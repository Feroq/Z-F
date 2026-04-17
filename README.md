<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Zeynep & Feridun ❤️</title>
    <style>
        * { margin: 0; padding: 0; box-sizing: border-box; }
        body, html { 
            height: 100%; 
            overflow: hidden; 
            background: #000; 
            font-family: 'Segoe UI', Arial, sans-serif; 
            color: white;
        }

        /* Şifre Ekranı */
        #passwordScreen {
            position: fixed;
            top: 0; left: 0;
            width: 100%; height: 100%;
            background: linear-gradient(rgba(0,0,0,0.85), rgba(0,0,0,0.9));
            display: flex;
            align-items: center;
            justify-content: center;
            z-index: 100;
            flex-direction: column;
        }

        #passwordScreen h1 {
            font-size: 2.8rem;
            margin-bottom: 30px;
            text-shadow: 0 0 20px rgba(255, 105, 180, 0.8);
        }

        #passwordInput {
            padding: 15px 25px;
            font-size: 1.3rem;
            border: none;
            border-radius: 50px;
            width: 280px;
            text-align: center;
            background: rgba(255,255,255,0.15);
            color: white;
            outline: none;
        }

        #passwordInput::placeholder {
            color: rgba(255,255,255,0.6);
        }

        #submitBtn {
            margin-top: 20px;
            padding: 12px 40px;
            font-size: 1.2rem;
            background: #ff4d94;
            color: white;
            border: none;
            border-radius: 50px;
            cursor: pointer;
            transition: 0.3s;
        }

        #submitBtn:hover {
            background: #ff3388;
            transform: scale(1.05);
        }

        #errorMsg {
            color: #ff6666;
            margin-top: 15px;
            font-size: 1.1rem;
            display: none;
        }

        /* Slayt Gösterisi (şifre doğru girilince görünür) */
        #mainContent {
            display: none;
        }

        .slideshow {
            position: fixed;
            top: 0; left: 0;
            width: 100%; height: 100%;
            z-index: 1;
        }

        .slide {
            position: absolute;
            top: 0; left: 0;
            width: 100%; height: 100%;
            background-size: cover;
            background-position: center;
            opacity: 0;
            transition: opacity 2.5s ease-in-out;
        }

        .slide.active {
            opacity: 1;
            z-index: 2;
        }

        .overlay {
            position: fixed;
            top: 0; left: 0;
            width: 100%; height: 100%;
            background: linear-gradient(to bottom, rgba(0,0,0,0.2), rgba(0,0,0,0.7));
            z-index: 3;
        }

        .text {
            position: fixed;
            bottom: 22%;
            left: 50%;
            transform: translateX(-50%);
            text-align: center;
            z-index: 4;
            text-shadow: 0 4px 25px rgba(0,0,0,0.95);
        }

        .text h1 {
            font-size: 3.5rem;
            margin-bottom: 12px;
        }

        .text p {
            font-size: 1.75rem;
        }

        .music {
            position: fixed;
            bottom: 30px;
            right: 30px;
            z-index: 5;
        }

        @media (max-width: 768px) {
            #passwordScreen h1 { font-size: 2.3rem; }
            .text h1 { font-size: 2.7rem; }
            .text p { font-size: 1.45rem; }
        }
    </style>
</head>
<body>

    <!-- Şifre Ekranı -->
    <div id="passwordScreen">
        <h1>Zeynep & Feridun</h1>
        <input type="password" id="passwordInput" placeholder="Şifreyi girin...">
        <button id="submitBtn">Giriş Yap ❤️</button>
        <div id="errorMsg">Yanlış şifre! Tekrar deneyin.</div>
    </div>

    <!-- Ana İçerik (Şifre doğruysa gösterilecek) -->
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

        <div class="text">
            <h1>Kalbimi Koydum</h1>
            <p>Sana… ❤️</p>
        </div>

        <div class="music">
            <audio id="bgMusic" loop>
                <source src="music.mp3" type="audio/mpeg">
            </audio>
        </div>
    </div>

    <script>
        const password = "ZeynepFeridun";
        const passwordScreen = document.getElementById('passwordScreen');
        const mainContent = document.getElementById('mainContent');
        const input = document.getElementById('passwordInput');
        const errorMsg = document.getElementById('errorMsg');
        const music = document.getElementById('bgMusic');

        // Şifre kontrolü
        document.getElementById('submitBtn').addEventListener('click', () => {
            if (input.value === password) {
                passwordScreen.style.display = 'none';
                mainContent.style.display = 'block';
                
                // Müzik otomatik çalmaya çalış
                music.volume = 0.72;
                music.play().catch(() => {
                    // Otomatik başlamazsa tıklayınca başlasın
                    document.body.addEventListener('click', () => {
                        if (music.paused) music.play();
                    }, { once: true });
                });
            } else {
                errorMsg.style.display = 'block';
                input.value = '';
                setTimeout(() => { errorMsg.style.display = 'none'; }, 2500);
            }
        });

        // Enter tuşu ile de giriş yapılabilsin
        input.addEventListener('keypress', (e) => {
            if (e.key === 'Enter') {
                document.getElementById('submitBtn').click();
            }
        });

        // Slayt gösterisi
        const slides = document.querySelectorAll('.slide');
        let current = 0;
        const intervalTime = 5200;

        function nextSlide() {
            slides[current].classList.remove('active');
            current = (current + 1) % slides.length;
            slides[current].classList.add('active');
        }

        setInterval(nextSlide, intervalTime);
    </script>
</body>
</html>
