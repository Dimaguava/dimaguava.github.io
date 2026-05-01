<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ануфриев Дмитрий - Digital Art,композитор,diy,noise,художник Санкт-Петербург,Circuit bend </title>
    
    <style>


    

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

       
/* ГАЛЕРЕЯ (МЕЙСОНРИ ДЛЯ РАЗНОЙ ВЫСОТЫ) */
        .gallery {
            column-count: 2; column-gap: 12px; padding: 5px; max-width: none; margin: 0 auto;
        }
        .art-item {
            display: inline-block; width: 100%; margin-bottom: 5px;
            background-color: rgba(0,0,0,0.5); border: 1px solid rgba(255,255,255,0.2);
            transition: transform 0.3s; cursor: pointer;
        }
        .art-item img, .art-item video { width: 100%; display: block; height: auto; }

        /* ОКНО ПРОСМОТРА */
        #viewer-overlay {
            display: none; position: fixed; top: 0; left: 0; width: 100%; height: 100%;
            background: rgba(0,0,0,0.95); z-index: 1000000; align-items: center; justify-content: center;
        }
        #viewer-content img, #viewer-content video { max-width: 95vw; max-height: 95vh; border: 1px solid white; }


        /* Двигающийся элемент (муха/глюк) */
        .moving-element {
            position: fixed;
            width: 70px;
            height: 70px;
            background: rgba(255, 255, 0, 0.7);
            border-radius: 50%;
            animation: move-around 9s linear infinite;
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

/* Панель управления ползунками */
.controls-panel {
    position: fixed;
    bottom: 20px;
    left: 10px;
    z-index: 10001; /* Поверх всего */
    background: rgba(0, 0, 0, 0.0);
    padding: 3px;
    border: 1px solid #fff;
    font-family: monospace;
    color: white;
    pointer-events: auto;
    width: 130px;
    height: 80px;
}

.control-group { margin-bottom: 10px; }
.control-group label { display: block; font-size: 10px; text-transform: uppercase; margin-bottom: 5px; }

/* Наш круг (обновленный) */
.moving-element, .float-eye {
    /* Используем переменные. Если их нет, возьмутся значения по умолчанию */
    width: var(--circle-size, 80px);
    height: var(--circle-size, 80px);
    animation-duration: var(--circle-speed, 11s) !important;
    
    position: fixed;
    border-radius: 50%;
    background: yellow;
    mix-blend-mode: difference;
    z-index: 10000;
    pointer-events: none;
}

/* БАННЕР */
        #entry-banner {
            position: fixed; top: 0; left: 0; width: 100%; height: 100%;
            background: white; display: flex; justify-content: center; align-items: center; z-index: 9999999;
        }

    </style>
</head>
<body>


<!-- ПЛЕЕР -->
<audio id="bg-music" src="audio1.mp3" loop></audio>



<div id="entry-banner">
    <div style="text-align: center; color: black; display: flex; gap: 20px; font-family: monospace;">
        <div onclick="location.href='nice.html'" style="cursor:pointer;">
             <img src="img_left.jpg" width="200" style="border-radius:10px;"><br>Я ЛЮБЛЮ ПОКОЙ
        </div>
        <div onclick="startSite()" style="cursor:pointer;">
             <img src="img_right.jpg" width="200" style="border-radius:10px;"><br>ШУМ / ВХОД
        </div>
    </div>
</div>

<script>
    function startSite() {
        var audio = document.getElementById('bg-music');
        var banner = document.getElementById('overlay');
        
        // Включаем музыку
        audio.play().catch(function(error) {
            console.log("Ошибка автоплея:", error);
        });
        
        // Убираем баннер
        banner.style.opacity = '0';
        banner.style.pointerEvents = 'none'; // Чтобы нельзя было кликнуть сквозь прозрачный баннер во время анимации
        
        setTimeout(function() {
            banner.remove();
        }, 500);
    }
</script>

<script>
    const overlay = document.getElementById('overlay');
    const startMusicBtn = document.getElementById('start-music');
    const audio = document.getElementById('bg-music');

    startMusicBtn.addEventListener('click', () => {
       

 // 1. Запускаем музыку
        audio.play().catch(e => console.log("Ошибка воспроизведения:", e));
        
        // 2. Делаем баннер прозрачным
        overlay.style.opacity = '0';
        
        // 3. Полностью удаляем баннер через 0.5 сек, чтобы он не мешал кликать по сайту
        setTimeout(() => {
            overlay.remove();
        }, 500);
    });
</script>



<div id="overlay" onclick="closeFull()" style="display: none; position: fixed; top: 0; left: 0; width: 100%; height: 100%; background: rgba(0,0,0,0.9); z-index: 99999; align-items: center; justify-content: center; cursor: zoom-out;">
    <img id="full-img" src="" style="max-width: 90%; max-height: 90vh; border: 1px solid white;">
</div>

<!-- ОКНО ПРОСМОТРА -->
<div id="viewer-overlay" onclick="closeFull()">
    <div id="viewer-content" onclick="event.stopPropagation()"></div>
</div>


    <!-- Двигающийся элемент -->
    <div class="moving-element"></div>

    <header>
        <h1>АНУФРИЕВ ДМИТРИЙ</h1>
        <p>Psychedelic Digital Art, композитор <br> noise, объекты в смешанной технике, Санкт-Петербург</p>
    </header>

<div class="controls-panel">
    <div class="control-group">
        <label>Рзмр Крг</label>
        <input type="range" id="sizeRange" min="20" max="1000" value="80">
    </div>
    <div class="control-group">
        <label>Скрст Крг</label>
        <input type="range" id="speedRange" min="0" max="31" value="9">
    </div>
</div>


    <div class="menu">
        <a href="gallery.html" class="glitch-button">Галерея</a>
        <a href="manifest.html" class="glitch-button">Обо мне</a>
        <a href="contact.html" class="glitch-button">Контакты</a>
    </div>

    <!-- Контейнер для картинок. Скопируйте art-item для добавления новых -->
    <div class="gallery">
        <div class="art-item" style="background-image: url('Screenshot_20260428_021401.jpg');"></div>
        <div class="art-item" style="background-image: url('jPDAfbffEcI.jpg');"></div>
        <div class="art-item" style="background-image: url('IMG_20260428_030610_579.jpg');"></div>

<div class="art-item">
    <video class="art-video" loop muted playsinline onmouseover="this.play()" onmouseout="this.pause()" onclick="this.muted = !this.muted">
        <source src="vacuum.mp4" type="video/mp4">
        Ваш браузер не поддерживает видео.
    </video>

   <h4>вакуумные работы где я смешиваю органику и неорганику останавливая время и разделяю объект из зрителя непроницаемой прозрачной мембраной отвратительной становится интересным а прекрасное теряет свою привлекательность и становится плоским</h4> 
    
    <div style="font-size: 8px; padding: 5px; color: #0f0;">[ CLICK FOR SOUND ]</div>
</div>

        
        <div class="art-item" style="background-image: url('m8SBsQvwA1GV72MMnlgVWp44seLJrT8WaTv9afzo5WxXMD0l7YVujDSqhfVcNCjlj39k82osW109nA-llm2B6MLq.jpg');"></div>

       <h4> сайт пока в разработке Я изучаю вообще как это всё работает по одной добавляю картинке Но конечно непонятно уже что это портфолио или самодостаточный арт-объект в котором я в очередной раз показываю принципы осознанной пассивности/ эстетики капитуляции которая не формирует объект по своему образу и подобию отвечающим поставленным задачам а позволяет ему быть таким какой он есть Напоминаю что я про сайт напоминаю также о принципах изменчивости поэтому вполне возможно послезавтра здесь будет другоослезавти другой дибудет</h4> 

        
<div class="art-item" style="background-image: url('IMG_20260428_030249_945.jpg');"></div>
<div class="art-item tall" style="background-image: url('long.jpg');">6</div>
<div class="art-item" style="background-image: url('snow.jpg');">7</div>
<div class="art-item" style="background-image: url('marine.jpg');">8</div>
    </div>
<div class="art-item tall" style="background-image: url('people.jpg');">8</div>
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
    

function startSite() {
        document.getElementById('entry-banner').style.opacity = '0';
        setTimeout(() => document.getElementById('entry-banner').style.display = 'none', 500);
        document.getElementById('bg-music').play();
    }

    function openFull(url, isVideo = false) {
        const overlay = document.getElementById('viewer-overlay');
        const container = document.getElementById('viewer-content');
        container.innerHTML = '';
        
        if (isVideo) {
            const video = document.createElement('video');
            video.src = url; video.controls = true; video.autoplay = true; video.loop = true;
            container.appendChild(video);
        } else {
            const img = document.createElement('img');
            img.src = url;
            container.appendChild(img);
        }
        overlay.style.display = 'flex';
        document.body.classList.add('no-scroll');
    }

    function closeFull() {
        document.getElementById('viewer-overlay').style.display = 'none';
        document.getElementById('viewer-content').innerHTML = '';
        document.body.classList.remove('no-scroll');
    }

    document.addEventListener('click', function(e) {
        const item = e.target.closest('.art-item');
        if (!item) return;

        const video = item.querySelector('video');
        if (video) {
            const src = video.querySelector('source') ? video.querySelector('source').src : video.src;
            openFull(src, true);
        } else {
            const img = item.querySelector('img');
            if (img) openFull(img.src, false);
        }
    });

    const circle = document.querySelector('.moving-element');
    document.getElementById('sizeRange').addEventListener('input', (e) => {
        circle.style.setProperty('--circle-size', e.target.value + 'px');
    });
    document.getElementById('speedRange').addEventListener('input', (e) => {
        circle.style.setProperty('--circle-speed', (32 - e.target.value) + 's');
    });



        // Регулировка размера
        sizeInput.addEventListener('input', (e) => {
            const size = e.target.value + 'px';
            circle.style.setProperty('--circle-size', size);
        });

        // Регулировка скорости
        speedInput.addEventListener('input', (e) => {
            // Инвертируем значение, чтобы чем больше ползунок, тем быстрее (меньше секунд) анимация
            const speed = (31 - e.target.value) + 's';
            circle.style.setProperty('--circle-speed', speed);
        });
    }
</script>

</body>
