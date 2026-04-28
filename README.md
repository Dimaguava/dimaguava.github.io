<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ануфриев Дмитрий - Digital Art,композитор,diy,noise,художник Санкт-Петербург,Circuit bend </title>
    
    <style>

/* Убираем тряску страницы */
html, body {
    overflow-x: hidden;
    margin: 0;
    padding: 0;
}

/* Общий стиль для всех полос */
.noto-stream {
    position: fixed;
    left: 0;
    width: 100%;
    z-index: 9999;
    pointer-events: none; /* Сквозь них можно кликать */
    mix-blend-mode: difference; /* ИНВЕРСИЯ */
}

.noto-bar {
    display: inline-block;
    background: white; /* Белая плашка для инверсии */
    color: black;      /* Черный текст */
    font-family: 'Courier New', monospace;
    font-size: 16px;
    font-weight: bold;
    padding: 4px 50px;
    white-space: nowrap;
    animation: alvaScroll 20s linear infinite;
}

/* Сетка Alva Noto на весь экран */
.alva-grid {
    position: fixed;
    top: 0; left: 0; width: 100%; height: 100%;
    background-image: 
        linear-gradient(rgba(255,255,255,0.2) 1px, transparent 1px),
        linear-gradient(90deg, rgba(255,255,255,0.2) 1px, transparent 1px);
    background-size: 50px 50px;
    mix-blend-mode: difference;
    z-index: 9998;
    pointer-events: none;
}

@keyframes alvaScroll {
    0% { transform: translateX(100%); }
    100% { transform: translateX(-100%); }
}

/* Текстовые ASCII вставки (неподвижные по углам) */
.ascii-corner {
    position: fixed;
    font-family: monospace;
    font-size: 10px;
    color: white;
    mix-blend-mode: difference;
    z-index: 10000;
    line-height: 1;
}



        /* Основные стили и психоделический градиент */
        body, html {
            margin: 0;
            padding: 0;
            width: 100%;
            font-family: 'Courier New', Courier, monospace;
            background: linear-gradient(125deg, #ff00ff, #00ffff, #ff0000, #0000ff);
            background-size: 800% 800%;
            animation: gradientBG 10s ease infinite;
            color: white;
            overflow-x: hidden;
        }

        @keyframes gradientBG {
            0% {background-position: 0% 50%}
            50% {background-position: 100% 50%}
            100% {background-position: 0% 50%}
        }

        /* Заголовок с глитч-эффектом */
        header {
            text-align: center;
            padding: 50px 20px;
            position: relative;
        }

        h1 {
            font-size: 4em;
            text-transform: uppercase;
            position: relative;
            display: inline-block;
        }

        h1::after {
            content: 'АНУФРИЕВ ДМИТРИЙ';
            position: absolute;
            left: 2px;
            text-shadow: -2px 0 red;
            top: 0;
            color: white;
            background: transparent;
            overflow: hidden;
            clip: rect(0, 900px, 0, 0);
            animation: glitch-anim 2s infinite linear alternate-reverse;
        }

        @keyframes glitch-anim {
            0% { clip: rect(20px, 9999px, 10px, 0); }
            100% { clip: rect(60px, 9999px, 80px, 0); }
        }

        /* Глючные кнопки */
        .menu {
            display: flex;
            justify-content: center;
            gap: 20px;
            flex-wrap: wrap;
            margin-bottom: 50px;
        }

        .glitch-button {
            padding: 15px 30px;
            background: black;
            color: #0f0;
            border: 2px solid #0f0;
            text-transform: uppercase;
            cursor: pointer;
            position: relative;
            font-weight: bold;
            transition: all 0.2s;
            text-decoration: none;
        }

        .glitch-button:hover {
            background: #0f0;
            color: black;
            box-shadow: 0 0 20px #0f0;
        }

        .glitch-button:hover::before {
            content: 'ERROR';
            position: absolute;
            top: 0; left: 0; width: 100%; height: 100%;
            background: red; color: white;
            display: flex; align-items: center; justify-content: center;
        }

        /* Галерея картинок */
        .gallery {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 15px;
            padding: 20px;
        }

        .art-item {
            height: 250px;
            background-color: rgba(0,0,0,0.5);
            border: 1px solid rgba(255,255,255,0.2);
            position: relative;
            overflow: hidden;
            transition: transform 0.3s;
            /* Сюда вставлять картинки: background-image: url('https://raw.githubusercontent.com/Dimaguava/dimaguava.github.io/refs/heads/main/Screenshot_20260428_021401.jpg'); */
            background-size: cover;
            background-position: center;
        }

        .art-item:hover {
            transform: scale(1.05) rotate(1deg);
            border-color: #ff00ff;
            box-shadow: 0 0 15px #ff00ff;
        }

        /* Двигающийся элемент (муха/глюк) */
        .moving-element {
            position: fixed;
            width: 70px;
            height: 70px;
            background: rgba(255, 255, 0, 0.7);
            border-radius: 50%;
            animation: move-around 14s linear infinite;
            pointer-events: none;
            mix-blend-mode: difference;
            z-index: 100;
        }

        @keyframes move-around {
            0% { top: 10%; left: 10%; }
            25% { top: 80%; left: 20%; }
            50% { top: 50%; left: 80%; }
            75% { top: 20%; left: 60%; }
            100% { top: 10%; left: 10%; }
        }

    </style>
</head>
<body>

<div id="overlay" onclick="closeFull()" style="display: none; position: fixed; top: 0; left: 0; width: 100%; height: 100%; background: rgba(0,0,0,0.9); z-index: 99999; align-items: center; justify-content: center; cursor: zoom-out;">
    <img id="full-img" src="" style="max-width: 90%; max-height: 90vh; border: 1px solid white;">
</div>


    <!-- Двигающийся элемент -->
    <div class="moving-element"></div>

    <header>
        <h1>АНУФРИЕВ ДМИТРИЙ</h1>
        <p>Psychedelic Digital Art, композитор <br> noise, объекты в смешанной технике, Санкт-Петербург</p>
    </header>

    <div class="menu">
        <a href="#" class="glitch-button">Галерея</a>
        <a href="manifest.html" class="glitch-button">Обо мне</a>
        <a href="#" class="glitch-button">Контакты</a>
    </div>

    <!-- Контейнер для картинок. Скопируйте art-item для добавления новых -->
    <div class="gallery">
        <div class="art-item" style="background-image: url('Screenshot_20260428_021401.jpg');"></div>
        <div class="art-item" style="background-image: url('jPDAfbffEcI.jpg');"></div>
        <div class="art-item" style="background-image: url('IMG_20260428_030610_579.jpg');"></div>
        <div class="art-item" style="background-image: url('m8SBsQvwA1GV72MMnlgVWp44seLJrT8WaTv9afzo5WxXMD0l7YVujDSqhfVcNCjlj39k82osW109nA-llm2B6MLq.jpg');"></div>
        <div class="art-item" style="background-image: url('IMG_20260428_030249_945.jpg');"></div>
        <div class="art-item" style="background-color: #666;">6</div>
        <div class="art-item" style="background-color: #777;">7</div>
        <div class="art-item" style="background-color: #888;">8</div>
    </div>

<!-- Сетка -->
<div class="alva-grid"></div>

<!-- ASCII элементы по углам -->
<div class="ascii-corner" style="top:10px; left:10px;">
    █║▌│█│║▌║││█║▌<br>ANUFRIEV_DMITRY<br>V.2.0.2.6
</div>
<div class="ascii-corner" style="bottom:10px; right:10px; text-align: right;">
    [SYSTEM_STABLE]<br>___/‾‾\___<br>ALVA_NOTO_MODE
</div>

<!-- Бегущие инвертирующие полосы -->
<!-- Полоса 1 -->
<div class="noto-stream" style="top: 15vh;">
    <div class="noto-bar">
        ░▒▓█ ERROR_0101010101010101_SYSTEM_FAILURE_RECOVERY_SIGNAL_STABLE_░▒▓█
    </div>
</div>

<!-- Полоса 2 -->
<div class="noto-stream" style="top: 45vh;">
    <div class="noto-bar" style="animation-direction: reverse; animation-duration: 30s; height: 30px; font-size: 24px;">
        ██████████████  DATA_STREAM_ANUFRIEV_██████████████
    </div>
</div>

<!-- Полоса 3 -->
<div class="noto-stream" style="top: 80vh;">
    <div class="noto-bar" style="animation-duration: 15s;">
        [ +++ ]  SIGNAL_LOST  [ +++ ]  ALVA_NOTO_STYLIZATION  [ +++ ]  ASCII_CODE_PROCESSED
    </div>
</div>



<script>
    function openFull(element) {
        // Достаем URL картинки из стиля background-image
        const bg = element.style.backgroundImage;
        const url = bg.replace(/url\(['"]?(.*?)['"]?\)/i, '$1');
        
        document.getElementById('full-img').src = url;
        document.getElementById('overlay').style.display = 'flex';
    }

    function closeFull() {
        document.getElementById('overlay').style.display = 'none';
    }

    // Автоматически добавляем клик на все карточки арт-объектов
    document.querySelectorAll('.art-item').forEach(item => {
        item.setAttribute('onclick', 'openFull(this)');
    });
</script>


</body>
</html>
