<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ануфриев Дмитрий - Digital Art,композитор,diy,noise,художник Санкт-Петербург,Circuit bend </title>
    
    <style>

/* Окно просмотра в стиле Alva Noto */


#overlay {
    display: none;
    position: fixed;
    top: 0; left: 0; width: 100%; height: 100%;
    background: #000;
    z-index: 1000;
    cursor: crosshair;
    align-items: center;
    justify-content: center;
    overflow: hidden;
}

#full-img-container {
    position: relative;
    display: flex;
    align-items: center;
    justify-content: center;
    /* Убираем лишние рамки для чистоты стиля */
}

#full-img {
    max-width: 95vw;
    max-height: 90vh;
    display: block;
    position: relative;
    z-index: 1; /* Картинка на нижнем слое */
}

/* Контейнер для бегущих строк ПОВЕРХ картинки */
.text-overlay-layer {
    position: absolute;
    top: 0; left: 0; width: 100%; height: 100%;
    z-index: 10; /* Текст на переднем плане */
    pointer-events: none; /* Чтобы клик проходил сквозь текст на оверлей для закрытия */
    display: flex;
    flex-direction: column;
    justify-content: space-around;
}

.data-stream {
    font-family: 'Courier New', monospace;
    font-size: 14px;
    color: rgba(255, 255, 255, 0.8);
    text-shadow: 0 0 5px rgba(0,0,0,1); /* Чтобы текст читался на светлых фото */
    white-space: nowrap;
    animation: textScroll 8s linear infinite;
    opacity: 0.7;
}

/* Сетка (Grid) тоже на переднем плане, но едва заметная */
.overlay-grid {
    position: absolute;
    top: 0; left: 0; width: 100%; height: 100%;
    background-image: 
        linear-gradient(rgba(255,255,255,0.1) 1px, transparent 1px),
        linear-gradient(90deg, rgba(255,255,255,0.1) 1px, transparent 1px);
    background-size: 30px 30px;
    z-index: 5;
    pointer-events: none;
}

@keyframes textScroll {
    0% { transform: translateX(100%); }
    100% { transform: translateX(-100%); }
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
            width: 50px;
            height: 50px;
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
    
<div id="overlay" onclick="closeFull()">
    <div id="full-img-container">
        <!-- Сетка поверх картинки -->
        <div class="overlay-grid"></div>

        <!-- Слой с бегущими строками -->
        <div class="text-overlay-layer">
            <div class="data-stream" style="animation-duration: 6s;">ANUFRIEV_DMITRY_ART_OBJECT_404_NULL_SEQUENCE_010101</div>
            <div class="data-stream" style="animation-duration: 10s; animation-direction: reverse; color: #0f0;">REC_SIGNAL_STABLE_BITRATE_MAX_DATA_STREAM_PROCESSING</div>
            <div class="data-stream" style="animation-duration: 7s;">ERROR_NO_METADATA_FOUND_SYSTEM_REBOOT_REQUIRED</div>
            <div class="data-stream" style="animation-duration: 12s; animation-direction: reverse;">X_COORD_Y_COORD_Z_COORD_VIRTUAL_SPACE_RENDER</div>
            <div class="data-stream" style="animation-duration: 5s; color: #f0f;">00110001 01110010 01111001 00100000 01100001 01110010 01110100</div>
        </div>
        
        <img id="full-img" src="" alt="Art">
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
