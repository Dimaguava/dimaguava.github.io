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
    font-size: 11px;
    color: #ffffff;     
    font-weight: 900 !important;
    cursor: pointer;
    mix-blend-mode: difference;
    pointer-events: auto;
}
.music-player span {
    background: rgba(0, 0, 0, 0.4);
    padding: 3px 8px;
    border: 1px solid rgba(255, 255, 255, 0.3);
    margin: 0 2px;
         color: #ffffff !important;
    font-weight: 900 !important;
    font-size: 8px !important;
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
    backdrop-filter: blur(2px);  
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
#viewer-content img, #viewer-content video { max-width: 95vw; max-height: 95vh; border: 1px solid white; }

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
    position: fixed; bottom: 20px; left: 10px; z-index: 10001;
    background: rgba(0, 0, 0, 0); padding: 8px; border: 1px solid #fff;
    width: 130px; color: white; font-family: monospace;
}
.control-group label { display: block; font-size: 10px; margin-bottom: 5px; }

#entry-banner {
    position: fixed; top: 0; left: 0; width: 100%; height: 100%;
    background: white; display: flex; justify-content: center; align-items: center; 
    z-index: 9999999; transition: opacity 0.5s ease;
}
.no-scroll { overflow: hidden; }
    </style>
</head>
<body>

<div class="music-player">
    <span id="audio-control" onclick="toggleMusic()">[ || ]</span>
    <span id="next-track" onclick="nextTrack()">[ >> ]</span>
</div>


<audio id="bg-music" src="audio1.mp3" loop data-current="1"></audio>



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

<header><h1>АНУФРИЕВ ДМИТРИЙ</h1></header>

<div class="menu">
    <a href="gallery.html" class="glitch-button">Галерея</a>
    <a href="manifest.html" class="glitch-button">Обо мне</a>
    <a href="contact.html" class="glitch-button">Контакты</a>
</div>

<div class="controls-panel">
    <div class="control-group">
        <label>Рзмр крг</label>
        <input type="range" id="sizeRange" min="20" max="900" value="200">
    </div>
    <div class="control-group">
        <label>Скрст крг</label>
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
        <video loop muted autoplay playsinline><source src="vacuum.mp4" type="video/mp4"></video>
    </div>
    <div class="art-item"><img src="long.jpg" alt=""></div>
<div class="art-item">
        <video loop muted autoplay playsinline><source src="2_5453932549736797835.mp4" type="video/mp4"></video>
    </div>

<div class="art-item">
        <video loop muted autoplay playsinline><source src="VID_20260502_072620_076.mp4" type="video/mp4"></video>
    </div>
<div class="art-item"><img src="marine.jpg" alt=""></div>
    <div class="art-item"><img src="IMG_20260428_030249_945.jpg" alt=""></div>
    <div class="art-item">
        <video loop muted autoplay playsinline><source src="VID_20260502_072915_864.mp4" type="video/mp4"></video>
    </div>

<div class="art-item"><img src="m8SBsQvwA1GV72MMnlgVWp44seLJrT8WaTv9afzo5WxXMD0l7YVujDSqhfVcNCjlj39k82osW109nA-llm2B6MLq.jpg" alt=""></div>
    <div class="art-item"><img src="vaka.jpg" alt=""></div>
    
а что если добавить текст в таблицу только на самом деле это все уже было 

  <div class="art-item">
        <video loop muted autoplay playsinline><source src="VID_20260502_072919_416.mp4" type="video/mp4"></video>
    </div>
<div class="art-item">
        <video loop muted autoplay playsinline><source src="VID_20260502_082928_229.mp4" type="video/mp4"></video>
    </div>
</div>
галерея заканчивается здесь ..здесь .дальше начинается пустое пространство, как будто степь, бесконечное поле, усыпанное снегом.. Я бы хотел чтобы <h1>текст</h1> наслаивался и переходил в <h1>белое</h1>, я бы хотел чтобы каждый текст наслаивался и переходил в белое. так наслаивается <h1>человек</h1>.






<div id="viewer-overlay" onclick="closeFull()">
    <div id="viewer-content" onclick="event.stopPropagation()"></div>
</div>


<script>
    function startSite() {
        document.getElementById('entry-banner').style.opacity = '0';
        setTimeout(() => document.getElementById('entry-banner').style.display = 'none', 500);
        document.getElementById('bg-music').play().catch(() => {});
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

// Функция переключения на следующий трек
function nextTrack() {
    let current = parseInt(audio.getAttribute('data-current'));
    
    // Если текущий трек 7, то сбрасываем на 1. Иначе просто прибавляем 1.
    let next = (current >= 7) ? 1 : current + 1;
    
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
