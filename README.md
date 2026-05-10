<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ануфриев Дмитрий - Digital Art, композитор, diy, noise, художник Санкт-Петербург, Circuit bend</title>
    
    <style>

.music-player {
    position: fixed;
    top: 10px; left: 50%;
    transform: translateX(-50%);
    z-index: 100003;
    font-family: monospace;
    font-size: 14px;
    color: #ffffff;     
    font-weight: 1000 !important;
    cursor: pointer;
    mix-blend-mode: difference;
    pointer-events: auto;
}
.music-player span {
    background: rgba(0, 0, 0, 0.4);
    padding: 3px 8px;
    border: 2px solid rgba(255, 255, 255, 0.3);
    margin: 0 3px;
         color: #ffffff !important;
    font-weight: 1000 !important;
    font-size: 12px !important;
}
.music-player span:hover { color: #0f0; border-color: #0f0; }

    
/* ОБЩИЙ СТИЛЬ ДЛЯ ВСЕХ ПОЛОС */
.noto-stream {
    position: fixed;
    left: 0;
    width: 100%;
    z-index: 9999;
    pointer-events: none;
    mix-blend-mode: difference;
}

.noto-bar {
    display: inline-block;
    background: white;
    color: black;
    font-family: 'Courier New', monospace;
    font-size: 16px;
    font-weight: bold;
    padding: 4px 50px;
    white-space: nowrap;
    animation: alvaScroll 20s linear infinite;
}

/* СЕТКА ALVA NOTO */
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

.ascii-corner {
    position: fixed;
    font-family: monospace;
    font-size: 11px;
    color: white;
    mix-blend-mode: difference;
    z-index: 10000;
    line-height: 2;
}

body, html {
    margin: 0; padding: 0; width: 100%;
    font-family: 'Courier New', Courier, monospace;
    background: linear-gradient(125deg, #f4d03f, #cd6155, blue, #0000ff);
    background-size: 200% 200%;
    animation: gradientBG 15s ease infinite;
    color: white; overflow-x: hidden;
}

@keyframes gradientBG {
    0% {background-position: 0% 50%}
    50% {background-position: 100% 50%}
    100% {background-position: 0% 50%}
}

header { text-align: center; padding: 50px 20px; position: relative; }
h1 { font-size: 4em; text-transform: uppercase; position: relative; display: inline-block; }
h1::after {
    content: 'Ануфриев Всегда '; position: absolute; left: 2px; text-shadow: -2px 0 red;
    top: 0; color: white; background: transparent; overflow: hidden;
    clip: rect(0, 900px, 0, 0); animation: glitch-anim 2s infinite linear alternate-reverse;
}

@keyframes glitch-anim {
    0% { clip: rect(20px, 9999px, 10px, 0); }
    100% { clip: rect(60px, 9999px, 80px, 0); }
}


.menu {
    position: absolute;
    top: 15px;       /* Отступ сверху */
    right: 15px;     /* Отступ справа */
    display: flex;
    flex-direction: column; /* Выстраиваем в столбик */
    gap: 5px;        /* Расстояние между кнопками */
    z-index: 10002;  /* Выше полосок и круга, чтобы всегда можно было нажать */
    align-items: flex-end; /* Выравнивание по правому краю */
}

.glitch-button {
    padding: 6px 12px;           
    background: rgba(0, 0, 0, 0); 
    color: #0f0;                 
    border: 1px solid rgba(0, 255, 0, 0.5); 
    text-transform: uppercase;
    cursor: pointer;
    font-weight: bold;
    font-size: 9px;              
    letter-spacing: 1px;         
    text-decoration: none;
    transition: all 0.3s ease;   
    white-space: nowrap;
    backdrop-filter: blur(3px);  
} 

.glitch-button:hover {
    background: rgba(0, 255, 0, 0.8); 
    color: black;
    box-shadow: 0 0 15px rgba(0, 255, 0, 0.5);
}


/* ГАЛЕРЕЯ ДВЕ КОЛОНКИ */
.gallery {
    column-count: 2; column-gap: 10px; padding: 8px; max-width: none; margin: 0 auto;
}

.art-item {
    display: inline-block; width: 100%; margin-bottom: 10px;
    background-color: rgba(0,0,0,0.5); border: 1px solid rgba(255,255,255,0.2);
    transition: transform 0.3s; cursor: pointer;
}
.art-item img, .art-item video { width: 100%; display: block; height: auto; }

/* Стиль для полноэкранной одиночной картинки */
.art-item-full {
    width: 100%;
    margin-bottom: 12px; /* Такой же отступ, как у маленьких карточек */
    background-color: rgba(0,0,0,0.5);
    border: 1px solid rgba(255,255,255,0.2);
    cursor: pointer;
    overflow: hidden;
    box-sizing: border-box;
}

.art-item-full img {
    width: 100%;
    height: auto;
    display: block;
    transition: transform 0.3s;
}

.art-item-full:hover img {
    transform: scale(1.01); /* Легкий зум при наведении */
}


/* ОКНО ПРОСМОТРА (OVERLAY) */
#viewer-overlay {
    display: none; position: fixed; top: 0; left: 0; width: 100%; height: 100%;
    background: rgba(0,0,0,0.95); z-index: 1000000; align-items: center; justify-content: center;
}
#viewer-content { max-width: 95vw; max-height: 95vh; }
#viewer-content img, #viewer-content video { max-width: 95vw; max-height: 95vh; border: 0px solid white; }

#viewer-content img { pointer-events: none; }

.moving-element {
    position: fixed; border-radius: 50%; background: yellow; mix-blend-mode: difference;
    z-index: 10000; pointer-events: none;
    width: var(--circle-size, 70px); height: var(--circle-size, 70px);
    animation: move-around var(--circle-speed, 11s) linear infinite;
}
@keyframes move-around {
    0% { top: 10%; left: 10%; } 25% { top: 80%; left: 20%; }
    50% { top: 50%; left: 80%; } 75% { top: 20%; left: 60%; }
    100% { top: 10%; left: 10%; }
}

.controls-panel {
    position: fixed; bottom: 10px; left: 10px; z-index: 10001;
    background: rgba(0, 0, 0, 0); padding: 8px; border: 0px solid #fff;
    width: 130px; color: white; font-family: monospace;
}
.control-group label { display: block; font-size: 10px; margin-bottom: 5px; }

#entry-banner {
    position: fixed; top: 0; left: 0; width: 100%; height: 100%;
    background: white; display: flex; justify-content: center; align-items: center; 
    z-index: 9999999; transition: opacity 0.5s ease;
}
.no-scroll { overflow: hidden; }






.white-steppe {
    position: relative;
    margin-top: -300px; /* Наплыв на галерею */
    background: linear-gradient(to bottom, transparent, #ffffff 40%); /* Быстрый уход в белый */
    min-height: 200vh;
}

.layering-text {
    position: sticky;
    top: 0;
    height: 130vh;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    pointer-events: none;
}

.layering-text h1 {
    position: absolute;
    font-size: 10vw;
    color: #fff;
    /* Разница (difference) заставит текст быть черным на белом и белым на цветном */
    mix-blend-mode: difference; 
    margin: 0;
    line-height: 0.8;
    text-transform: uppercase;
}


/* Этот блок сработает только на экранах меньше 768 пикселей (смартфоны) */
@media (max-width: 768px) {
    #guestbook {
        margin-top: -350px !important; /* Принудительно затягиваем форму вверх */
        position: relative;
        z-index: 10005; /* Поднимаем её выше залипающего текста */
        background: rgba(255, 255, 255, 0.9); /* Добавляем легкую белую подложку, чтобы сквозь форму не просвечивали другие элементы */
        padding: 15px;
    }
    
    .white-steppe {
        min-height: 180vh; /* Слегка уменьшаем высоту степи для мобильных, чтобы не было гигантских пустых экранов */
    }
}


    </style>

    
</head>
<body>

<div class="music-player">
    <span id="audio-control" onclick="toggleMusic()">[ || ]</span>
    <span id="next-track" onclick="nextTrack()">[ >> ]</span>
</div>


<!-- Добавь onended="nextTrack()" внутрь тега: -->
<audio id="bg-music" data-current="1" onended="nextTrack()"></audio>



<div id="entry-banner"> этот сайт представляет собой самодостаточный арт-объект Нажмите на правую картинку чтобы получить полный экспириенс в верхней части сайта находятся кнопки управления звуком в Нижней - кругом <br>
    <div style="text-align: center; color: black; display: flex; gap: 20px; font-family: monospace;">

    
        <div onclick="location.href='nice.html'" style="cursor:pointer;">
             <img src="img_left.jpg" width="200" style="border-radius:10px;"><br>Я ЛЮБЛЮ ПОКОЙ
        </div>
        <div onclick="startSite()" style="cursor:pointer;">
             <img src="img_right.jpg" width="200" style="border-radius:10px;"><br>ШУМ / ВХОД
        </div>
    </div>
</div>

<div class="alva-grid"></div>

<div class="ascii-corner" style="top:10px; left:10px;">
    █║▌│█│║▌║││█║▌<br>ANUFRIEV_DMITRY<br>V.2.0.2.6
</div>
<div class="ascii-corner" style="bottom:10px; right:10px; text-align: right;">
    [SYSTEM_STABLE]<br>___/‾‾\___<br>ALVA_NOTO_MODE
</div>

<div class="noto-stream" style="top: 15vh;"><div class="noto-bar">░▒▓█ ERROR_01010101_SYSTEM_FAILURE_RECOVERY_░▒▓█</div></div>
<div class="noto-stream" style="top: 45vh;"><div class="noto-bar" style="animation-direction: reverse;">██████████ DATA_STREAM_ANUFRIEV_██████████</div></div>
<div class="noto-stream" style="top: 80vh;"><div class="noto-bar" style="animation-duration: 15s;">[ +++ ] ЭЛЕКТРОХОЛМ [ +++ ] ALVA_NOTO_MODE  [ +++ ] ELECTROXOLM</div></div>

<div class="moving-element"></div>

<header><h1>АНУФРИЕВ ДМИТРИЙ</h1> <br>композитор и художник из санкт-петербурга, работающий в смешанной технике. инсталляции, звуковые diy-объекты, работы в вакуумных пакетах, circuit bend, 2d и 3d сканирование</header>

<div class="menu">
    <a href="gallery.html" class="glitch-button">Галерея</a>
    <a href="manifest.html" class="glitch-button">Обо мне</a>
    <a href="contact.html" class="glitch-button">Контакты</a>
</div>



<div class="controls-panel">
    <div class="control-group">
        <label>size</label>
        <input type="range" id="sizeRange" min="20" max="900" value="200">
    </div>
    <div class="control-group">
        <label>speed</label>
        <input type="range" id="speedRange" min="0" max="33" value="1">
    </div>
</div>


<!-- Одиночное изображение во всю ширину -->
<div style="padding: 10px;">
    <div class="art-item" style="margin-bottom: 6px;">
        <img src="Screenshot_20260428_021401.jpg" alt="">
    </div>
</div>


<div class="gallery">
    <!-- КАРТИНКИ ТЕПЕРЬ ВСТАВЛЯЮТСЯ ТАК (ЧЕРЕЗ ТЕГ IMG), ЧТОБЫ КОЛОНКИ РАБОТАЛИ -->
    <div class="art-item"><img src="hand.jpg" alt=""></div>
    <div class="art-item"><img src="jPDAfbffEcI.jpg" alt=""></div>
    <div class="art-item"><img src="IMG_20260428_030610_579.jpg" alt=""></div>
    <div class="art-item">
        <video loop muted autoplay playsinline><source data-src="vacuum.mp4" type="video/mp4"></video>
    </div>
    <div class="art-item"><img data-src="long.jpg" alt=""></div>
<div class="art-item">
        <video loop muted autoplay playsinline><source data-src="2_5453932549736797835.mp4" type="video/mp4"></video>
    </div>

<div class="art-item">
        <video loop muted autoplay playsinline><source data-src="VID_20260502_072620_076.mp4" type="video/mp4"></video>
    </div>
<div class="art-item"><img src="marine.jpg" alt=""></div>
    <div class="art-item"><img src="IMG_20260428_030249_945.jpg" alt=""></div>
    <div class="art-item">
        <video loop muted autoplay playsinline><source data-src="VID_20260502_072915_864.mp4" type="video/mp4"></video>
    </div>

<div class="art-item"><img src="m8SBsQvwA1GV72MMnlgVWp44seLJrT8WaTv9afzo5WxXMD0l7YVujDSqhfVcNCjlj39k82osW109nA-llm2B6MLq.jpg" alt=""></div>
    <div class="art-item"><img src="vaka.jpg" alt=""></div>
    
[ Здесь будет наш с вами проект если вы напишите мне, а пока здесь просто буквы ] 

  <div class="art-item">
        <video loop muted autoplay playsinline><source data-src="VID_20260502_072919_416.mp4" type="video/mp4"></video>
    </div>
<div class="art-item">
        <video loop muted autoplay playsinline><source data-src="VID_20260502_082928_229.mp4" type="video/mp4"></video>
    </div>
</div>
галерея заканчивается здесь ..здесь .дальше начинается пустое пространство, как будто степь, бесконечное поле, усыпанное снегом.. Я бы хотел чтобы <h1>текст</h1> наслаивался и переходил в <h1>белое</h1>, я бы хотел чтобы каждый текст наслаивался и переходил в белое. так наслаивается <h1>человек</h1>.



<div class="white-steppe">
    <div class="layering-text">
        <!-- Тексты с разным смещением, чтобы они наслаивались друг на друга -->
        <h1 style="transform: translate(-5%, -40%);">человек</h1>
        <h1 style="transform: translate(40%, 15%); opacity: 0.7; font-size: 20vw;">наслаивается</h1>
        <h1 style="transform: translate(-2%, 20%); font-size: 70vw;">БЕЛОЕ</h1>
        <h1 style="transform: translate(15%, -5%); opacity: 0.4; font-size: 20vw;">человек</h1>
        <h1 style="transform: translate(-10%, 40%); filter: blur(5px);">СТЕПЬ</h1>
        <h1 style="transform: translate(0, 0); font-size: 90vw; opacity: 0.2;">ЧЕЛОВЕК</h1>
        <h1 style="transform: translate(-30%, 40%); font-size: 70vw;">Снег</h1>
    </div>


<div id="guestbook" style="padding: 20px; color: black; font-family: monospace; position: relative; z-index: 20003; font-size: 22px; background: transparent;">
    <h2 style="font-size: 11px; color: black; text-transform: uppercase; border-bottom: 1px solid black; display: inline-block;">ОСТАВИТЬ СЛЕД [GUESTBOOK]</h2>
    
    <!-- Форма -->
    <div style="margin: 20px 0 30px 0; display: flex; gap: 10px; flex-wrap: wrap;">
        <input type="text" id="guestName" placeholder="ИМЯ/Контакт" 
               style="background: transparent; color: black; border: 1px solid black; padding: 8px; font-family: monospace; font-size: 12px; font-weight: normal; outline: none;">
    

<!-- (Тег textarea для многострочного текста): -->
<textarea id="guestMsg" placeholder="Текст/ASCII рисунок" rows="6" style="background: transparent; color: black; border: 1px solid black; padding: 8px; font-family: 'Courier New', monospace; font-size: 13px; width: 60%; outline: none; resize: vertical; display: block; margin-top: 10px;"></textarea>

        
        <button onclick="sendSignal()" class="glitch-button" 
                style="background: transparent; color: black; border: 1px solid black; cursor: pointer; padding: 8px 15px; font-size: 10px;">ОТПРАВИТЬ</button>
    </div>

    <!-- Сюда будет подгружаться текст -->
    <div id="messages-container" style="border-top: 1px solid black; padding-top: 15px; color: black; font-size: 14px; line-height: 1.2; white-space: pre-wrap; font-family: 'Courier New', monospace;">
        ЗАГРУЗКА СООБЩЕНИЙ...
    </div>
</div>


</div>

<div id="viewer-overlay" onclick="closeFull()">
    <div id="viewer-content" ></div>
</div>


<script>


  const SCRIPT_URL = 'https://script.google.com/macros/s/AKfycbzcjJn7VluyxowHJF-3KFlUwyn68WhAnuLk23_sIRWpNefGX8XWwQuxCO-F15DnhsQ9/exec'; // Твоя ссылка из Google Apps Script

// Функция отправки
function sendSignal() {
    const name = document.getElementById('guestName').value;
    const message = document.getElementById('guestMsg').value;
    
    fetch(SCRIPT_URL, {
        method: 'POST',
        body: JSON.stringify({ name, message })
    }).then(() => location.reload()); // Перезагрузка, чтобы увидеть текст
}

// Функция загрузки сообщений при входе
function loadMessages() {
    fetch(SCRIPT_URL)
        .then(res => res.json())
        .then(data => {
            const container = document.getElementById('messages-container');
            // Переворачиваем массив, чтобы новые сообщения были сверху
            container.innerHTML = data.reverse().map(row => `<div style="margin-bottom: 20px; border-bottom: 1px dashed #ccc; padding-bottom: 15px; font-family: 'Courier New', monospace; font-size: 10px; white-space: pre-wrap; line-height: 1.1; letter-spacing: -0.5px;"><span style="font-weight: normal; display: block; margin-bottom: 8px; color: black;">[${row[1] || 'АНОНИМ'}]</span>${row[2]}</div>`).join('');
        });
}


// Функция, которая находит пустые картинки/видео и наполняет их контентом
function loadGalleryElements() {
    // Загружаем картинки
    document.querySelectorAll('.art-item img[data-src]').forEach(img => {
        img.src = img.getAttribute('data-src');
        img.removeAttribute('data-src'); // Очищаем маркер
    });

    // Загружаем видео
    document.querySelectorAll('.art-item video source[data-src]').forEach(source => {
        const video = source.closest('video');
        source.src = source.getAttribute('data-src');
        source.removeAttribute('data-src');
        video.load(); // Принудительно перезапускаем плеер для старта видео
    });
}


    
// ГЛАВНЫЙ ДИСПЕТЧЕР ОЧЕРЕДНОСТИ
// НАВЕДЕНИЕ ПОРЯДКА В ОЧЕРЕДНОСТИ
document.addEventListener('DOMContentLoaded', () => {
    
    // ЭТАП 1: Загружаем ТОЛЬКО сообщения из Google Таблицы
    fetch(SCRIPT_URL)
        .then(res => res.json())
        .then(data => {
            const container = document.getElementById('messages-container');
            container.innerHTML = data.reverse().map(row => `<div style="margin-bottom: 20px; border-bottom: 1px dashed #ccc; padding-bottom: 15px; font-family: 'Courier New', monospace; white-space: pre-wrap; line-height: 1.1; letter-spacing: -0.5px;"><span style="font-weight: normal; display: block; margin-bottom: 8px; color: black;">[${row[1] || 'АНОНИМ'}]</span>${row[2]}</div>`).join('');
            
            // ЭТАП 2: Даем зеленый свет тяжелой галерее
            // Музыку отсюда полностью убрали, теперь она не конфликтует с баннером!
            setTimeout(loadGalleryElements, 100);
        })
        .catch(err => {
            console.error("Критический сбой очереди:", err);
            loadGalleryElements(); // В случае сбоя бэкенда всё равно включаем галерею
        });
});

  


    
    
    function startSite() {
        // Убираем баннер
        const banner = document.getElementById('entry-banner');
        banner.style.opacity = '0';
        setTimeout(() => banner.style.display = 'none', 500);

        const audio = document.getElementById('bg-music');
        
        // Рандом от 1 до 7
        const randomTrack = Math.floor(Math.random() * 7) + 1;
        
        // Установка трека
        audio.src = 'audio' + randomTrack + '.mp3';
        audio.setAttribute('data-current', randomTrack);
        
        // Принудительная загрузка и старт
        audio.load();
        audio.play().catch(e => console.log("Audio play blocked"));
    }

    function toggleMusic() {
        const audio = document.getElementById('bg-music');
        const btn = document.getElementById('audio-control');
        if (audio.paused) {
            audio.play();
            btn.innerHTML = '[ || ]';
        } else {
            audio.pause();
            btn.innerHTML = '[ ▶ ]';
        }
    }

    function nextTrack() {
        const audio = document.getElementById('bg-music');
        let current = parseInt(audio.getAttribute('data-current')) || 1;
        
        // Листаем вперед
        let next = (current >= 7) ? 1 : current + 1;
        
        audio.src = 'audio' + next + '.mp3';
        audio.setAttribute('data-current', next);
        
        audio.load();
        audio.play();
        
        const btn = document.getElementById('audio-control');
        if (btn) btn.innerHTML = '[ || ]';
    }

    


// Функция открытия
function openFull(url, isVideo = false) {
    const overlay = document.getElementById('viewer-overlay');
    const container = document.getElementById('viewer-content');
    const bgMusic = document.getElementById('bg-music'); // Находим фоновую музыку
    
    container.innerHTML = '';
    
    if (isVideo) {
        // Если открывается видео, СТАВИМ НА ПАУЗУ фоновую музыку
        if (bgMusic) bgMusic.pause();
        
        const video = document.createElement('video');
        video.src = url; 
        video.controls = true; 
        video.autoplay = true; 
        video.loop = true;
        container.appendChild(video);
    } else {
        const img = document.createElement('img');
        img.src = url;
        container.appendChild(img);
    }
    
    overlay.style.display = 'flex';
    document.body.classList.add('no-scroll');
}

// Функция закрытия

function closeFull() {
    const overlay = document.getElementById('viewer-overlay');
    const container = document.getElementById('viewer-content');
    const bgMusic = document.getElementById('bg-music'); // Находим фоновую музыку
    
    // ПРОВЕРЯЕМ: если внутри оверлея сейчас играет видео
    const currentVideo = container.querySelector('video');
    
    overlay.style.display = 'none';
    container.innerHTML = ''; // Удаляем контент (видео перестает звучать)
    document.body.classList.remove('no-scroll');
    
    // Если мы закрыли именно видео, ВОЗОБНОВЛЯЕМ фоновую музыку
    if (currentVideo && bgMusic) {
        bgMusic.play().catch(e => console.log("Музыка не смогла включиться автоматически"));
    }
}

    
    document.addEventListener('click', (e) => {
        const item = e.target.closest('.art-item');
        if (!item) return;
        const video = item.querySelector('video');
        if (video) openFull(video.querySelector('source').src, true);
        else { const img = item.querySelector('img'); if (img) openFull(img.src, false); }
    });


const audio = document.getElementById('bg-music');

// Функция Пауза / Плей
function toggleMusic() {
    const btn = document.getElementById('audio-control');
    if (audio.paused) {
        audio.play();
        btn.innerHTML = '[ || ]';
    } else {
        audio.pause();
        btn.innerHTML = '[ ▶ ]';
    }
}


function nextTrack() {
    const audio = document.getElementById('bg-music');
    let current = parseInt(audio.getAttribute('data-current'));
    
    // Листаем вперед: если был 7-й, включаем 1-й
    let next = (current >= 7) ? 1 : current + 1;
    
    audio.src = 'audio' + next + '.mp3';
    audio.setAttribute('data-current', next);
    
    audio.play();
    
    audio.src = 'audio' + next + '.mp3';
    audio.setAttribute('data-current', next);
    
    audio.play();
    document.getElementById('audio-control').innerHTML = '[ || ]';
}


    
    const circle = document.querySelector('.moving-element');
    document.getElementById('sizeRange').addEventListener('input', (e) => {
        circle.style.setProperty('--circle-size', e.target.value + 'px');
    });
    document.getElementById('speedRange').addEventListener('input', (e) => {
        circle.style.setProperty('--circle-speed', (32 - e.target.value) + 's');
    });
</script>

</body>
</html>
