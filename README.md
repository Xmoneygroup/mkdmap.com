<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>XKAPO | Authority</title>
    <style>
        /* RESET TOTAL */
        * { margin: 0; padding: 0; box-sizing: border-box; }
        body, html { 
            width: 100%; height: 100%; 
            background-color: #000; 
            color: #fff; 
            font-family: Arial, sans-serif; 
            overflow: hidden; 
        }

        /* 1. INTRO LOGO (2 SEKONDA) */
        #intro-splash {
            position: fixed; top: 0; left: 0; width: 100%; height: 100%;
            background-color: #000;
            display: flex; justify-content: center; align-items: center;
            z-index: 10000;
        }

        .logo-anim {
            max-width: 80%; height: auto;
            opacity: 0;
            animation: logoFlash 2s forwards;
        }

        @keyframes logoFlash {
            0% { opacity: 0; transform: scale(0.98); }
            50% { opacity: 1; transform: scale(1); }
            100% { opacity: 0; transform: scale(1.02); }
        }

        /* NAVIGATION STYLE MANSORY */
        nav {
            position: fixed; top: 0; width: 100%; padding: 30px 60px;
            display: flex; justify-content: space-between; align-items: center;
            z-index: 2000;
            background: linear-gradient(to bottom, rgba(0,0,0,0.7), transparent);
            text-transform: uppercase; font-size: 12px; letter-spacing: 3px;
        }
        .nav-logo { font-size: 24px; letter-spacing: 10px; font-weight: bold; }
        .contact-btn { 
            border: 1px solid #fff; padding: 10px 25px; 
            text-decoration: none; color: #fff; transition: 0.3s; 
        }
        .contact-btn:hover { background: #fff; color: #000; }

        /* HOME PAGE & SLIDER */
        #home-content { opacity: 0; width: 100%; height: 100vh; position: relative; }
        .slider-container { width: 100%; height: 100%; position: relative; }
        
        .slide {
            position: absolute; width: 100%; height: 100%;
            background-size: cover; 
            background-position: center;
            display: none; /* E bëjmë display none që të mos përzihen */
        }
        .slide.active { display: block; } /* Vetëm fotoja aktive shfaqet direkt */

        /* OVERLAY PËR PAMJE PREMIUM */
        .overlay { 
            position: absolute; top: 0; left: 0; width: 100%; height: 100%;
            background: rgba(0,0,0,0.2); z-index: 5; pointer-events: none; 
        }
    </style>
</head>
<body>

    <div id="intro-splash">
        <img src="9BA7D80D-DB0A-4D39-9C65-6FD915BCF247.jpg" alt="XKAPO" class="logo-anim">
    </div>

    <div id="home-content">
        <nav>
            <div style="visibility: hidden;">MODELS</div> <div class="nav-logo">XKAPO</div>
            <a href="tel:+389070878227" class="contact-btn">CONTACT US</a>
        </nav>

        <div class="slider-container">
            <div class="overlay"></div>
            
            <div class="slide active" style="background-image: url('IMG_1022.jpg');"></div>
            <div class="slide" style="background-image: url('IMG_1024.jpg');"></div>
            <div class="slide" style="background-image: url('IMG_1025.jpg');"></div>
            <div class="slide" style="background-image: url('IMG_1026.jpg');"></div>
            <div class="slide" style="background-image: url('IMG_1027.jpg');"></div>
        </div>
    </div>

    <script>
        // TRANZICIONI NGA LOGO TE HOME
        window.addEventListener('load', () => {
            setTimeout(() => {
                document.getElementById('intro-splash').style.display = 'none';
                document.getElementById('home-content').style.opacity = '1';
                startInstantSlider();
            }, 2000); // 2 sekonda logoja
        });

        // SLIDERI DIREKT PA "FADE" (3.5 SEKONDA)
        function startInstantSlider() {
            const slides = document.querySelectorAll('.slide');
            let current = 0;

            setInterval(() => {
                slides[current].classList.remove('active'); // Zhduket direkt
                current = (current + 1) % slides.length;
                slides[current].classList.add('active'); // Shfaqet direkt tjetra
            }, 3500); // 3.5 sekonda qëndrimi
        }
    </script>
</body>
</html>
