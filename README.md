<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ануфриев Дмитрий - Digital Art,композитор,diy,noise,художник Санкт-Петербург,Circuit bend </title>
    
    <style>

/* 1. ГЛОБАЛЬНЫЕ СЛОИ (СЕТКА И ТЕКСТ) */
.global-overlay {
    position: absolute;
    top: 0; left: 0;
    width: 100%; height: 100%;
    pointer-events: none; /* Чтобы кнопки под ними работали */
    z-index: 999;
}

.global-grid {
    background-image: 
        linear-gradient(rgba(255,255,255,0.1) 1px, transparent 1px),
        linear-gradient(90deg, rgba(255,255,255,0.1) 1px, transparent 1px);
    background-size: 40px 40px;
    mix-blend-mode: difference;
}

.global-text-streams {
    display: flex;
    flex-direction: column;
    justify-content: space-around; /* Равномерно по высоте */
    padding: 2vh 0;
}

.data-stream-wrapper { width: 100%; overflow: visible; }

.data-stream {
    font-family: 'Courier New', monospace;
    font-size: clamp(14px, 2vw, 20px);
    font-weight: bold;
    white-space: nowrap;
    background: white; /* Белая плашка */
    color: black;      /* Черный текст */
    display: inline-block;
    padding: 5px 30px;
    mix-blend-mode: difference; /* ЭФФЕКТ ИНВЕРСИИ */
    animation: textScroll 12s linear infinite;
}

@keyframes textScroll {
    13% { transform: translateX(100%); }
    100% { transform: translateX(-100%); }
}

/* 2. ОКНО ПРОСМОТРА КАРТИНКИ */
#overlay {
    display: none;
    position: fixed;
    top: 0; left: 0;
    width: 100%; height: 100%;
    background: rgba(0,0,0,0.9);
    z-index: 2000; /* Выше всего */
    cursor: zoom-out;
    align-items: center;
    justify-content: center;
}

#full-img {
    max-width: 90%;
    max-height: 90vh;
    border: 1px solid #555;
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
            animation: move-around 10s linear infinite;
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

    <!-- Двигающийся элемент -->
    <div class="moving-element"></div>

    <header>
        <h1>АНУФРИЕВ ДМИТРИЙ</h1>
        <p>Psychedelic Digital Art, композитор <br> noise, объекты в смешанной технике, Санкт-Петербург</p>
    </header>

    <div class="menu">
        <a href="#" class="glitch-button">Галерея</a>
        <a href="#" class="glitch-button">Обо мне</a>
        <a href="#" class="glitch-button">Контакты</a>
    </div>

    <!-- Контейнер для картинок. Скопируйте art-item для добавления новых -->
    <div class="gallery">
        <div class="art-item" style="background-image: url('Screenshot_20260428_021401.jpg');"></div>
        <div class="art-item" style="background-image: url('IMG_20260428_030610_579.jpg');"></div>
        <div class="art-item" style="background-image: url('IMG_20260428_030458_887.jpg');"></div>
        <div class="art-item" style="background-color: #444;">ыыыы </div>
        <div class="art-item" style="background-color: #555;">5</div>
        <div class="art-item" style="background-color: #666;">6</div>
        <div class="art-item" style="background-color: #777;">7</div>
        <div class="art-item" style="background-color: #888;">8</div>
    </div>

<!-- Глобальные элементы на весь сайт -->
<div class="global-overlay global-grid"></div>
<div class="global-overlay global-text-streams">
    <div class="data-stream-wrapper"><div class="data-stream">ANUFRIEV_DMITRY_ART_SEQUENCE_0101010101</div></div>
    <div class="data-stream-wrapper"><div class="data-stream" style="animation-direction: reverse; animation-duration: 25s;">SYSTEM_ERROR_DATA_STREAM_ALVA_NOTO_RECOVERY</div></div>
    <div class="data-stream-wrapper"><div class="data-stream" style="animation-duration: 12s;">PROCESS_RENDER_404_NULL_POINTER_STABLE</div></div>
</div>

<!-- Окно для картинок (чистое, так как сетка уже есть везде) -->
<div id="overlay" onclick="closeFull()">
    <img id="full-img" src="" alt="">
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
