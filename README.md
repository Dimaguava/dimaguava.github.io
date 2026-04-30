<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ануфриев Дмитрий - Digital Art, композитор, diy, noise, художник Санкт-Петербург, Circuit bend</title>
    
    <style>
        /* ОСНОВНОЙ СТИЛЬ */
        body, html {
            margin: 0; padding: 0; width: 100%;
            font-family: 'Courier New', Courier, monospace;
            background: linear-gradient(125deg, #ff00ff, #00ffff, #ff0000, #0000ff);
            background-size: 800% 800%;
            animation: gradientBG 10s ease infinite;
            color: white; overflow-x: hidden;
        }

        @keyframes gradientBG {
            0% {background-position: 0% 50%}
            50% {background-position: 100% 50%}
            100% {background-position: 0% 50%}
        }

        /* ИНВЕРСИОННЫЕ ПОЛОСЫ И СЕТКА */
        .alva-grid {
            position: fixed; top: 0; left: 0; width: 100%; height: 100%;
            background-image: linear-gradient(rgba(255,255,255,0.2) 1px, transparent 1px),
                              linear-gradient(90deg, rgba(255,255,255,0.2) 1px, transparent 1px);
            background-size: 50px 50px; mix-blend-mode: difference; z-index: 9998; pointer-events: none;
        }

        .noto-stream {
            position: fixed; left: 0; width: 100%; z-index: 9999;
            pointer-events: none; mix-blend-mode: difference;
        }

        .noto-bar {
            display: inline-block; background: white; color: black;
            font-family: 'Courier New', monospace; font-size: 16px; font-weight: bold;
            padding: 4px 50px; white-space: nowrap; animation: alvaScroll 20s linear infinite;
        }

        @keyframes alvaScroll {
            0% { transform: translateX(100%); }
            100% { transform: translateX(-100%); }
        }

        /* ШАПКА И МЕНЮ */
        header { text-align: center; padding: 50px 20px; }
        h1 { font-size: 4em; text-transform: uppercase; position: relative; display: inline-block; }
        h1::after {
            content: 'АНУФРИЕВ ДМИТРИЙ'; position: absolute; left: 2px; text-shadow: -2px 0 red;
            top: 0; color: white; background: transparent; overflow: hidden;
            clip: rect(0, 900px, 0, 0); animation: glitch-anim 2s infinite linear alternate-reverse;
        }
        @keyframes glitch-anim {
            0% { clip: rect(20px, 9999px, 10px, 0); }
            100% { clip: rect(60px, 9999px, 80px, 0); }
        }

        .menu { display: flex; justify-content: center; gap: 20px; flex-wrap: wrap; margin-bottom: 50px; }
        .glitch-button {
            padding: 15px 30px; background: black; color: #0f0; border: 2px solid #0f0;
            text-transform: uppercase; cursor: pointer; font-weight: bold; text-decoration: none;
        }
        .glitch-button:hover { background: #0f0; color: black; box-shadow: 0 0 20px #0f0; }

        /* ГАЛЕРЕЯ (МЕЙСОНРИ ДЛЯ РАЗНОЙ ВЫСОТЫ) */
        .gallery {
            column-count: 3; column-gap: 15px; padding: 20px; max-width: 1400px; margin: 0 auto;
        }
        .art-item {
            display: inline-block; width: 100%; margin-bottom: 15px;
            background-color: rgba(0,0,0,0.5); border: 1px solid rgba(255,255,255,0.2);
            transition: transform 0.3s; cursor: pointer;
        }
        .art-item img, .art-item video { width: 100%; display: block; height: auto; }

        /* ОКНО ПРОСМОТРА */
        #viewer-overlay {
            display: none; position: fixed; top: 0; left: 0; width: 100%; height: 100%;
            background: rgba(0,0,0,0.95); z-index: 1000000; align-items: center; justify-content: center;
        }
        #viewer-content img, #viewer-content video { max-width: 90vw; max-height: 90vh; border: 1px solid white; }

        /* КРУГ И ПАНЕЛЬ */
        .moving-element {
            position: fixed; width: var(--circle-size, 70px); height: var(--circle-size, 70px);
            background: yellow; border-radius: 50%; mix-blend-mode: difference;
            z-index: 10000; pointer-events: none; animation: move-around var(--circle-speed, 9s) linear infinite;
        }
        @keyframes move-around {
            0% { top: 10%; left: 10%; } 25% { top: 80%; left: 20%; }
            50% { top: 50%; left: 80%; } 75% { top: 20%; left: 60%; }
            100% { top: 10%; left: 10%; }
        }
        .controls-panel {
            position: fixed; bottom: 10px; left: 10px; z-index: 10001;
            background: rgba(0,0,0,0.8); padding: 8px; border: 1px solid white; width: 120px;
        }
        .control-group label { font-size: 8px; display: block; margin-bottom: 2px; }
        .no-scroll { overflow: hidden; }

        /* БАННЕР */
        #entry-banner {
            position: fixed; top: 0; left: 0; width: 100%; height: 100%;
            background: white; display: flex; justify-content: center; align-items: center; z-index: 9999999;
        }
    </style>
</head>
<body>

<audio id="bg-music" src="audio1.mp3" loop></audio>

<!-- БАННЕР ВХОДА -->
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

<div class="noto-stream" style="top: 15vh;"><div class="noto-bar">█║▌│█│║▌║││█║▌ ANUFRIEV_DMITRY_V.2.0.2.4_█║▌│█│║▌║</div></div>
<div class="noto-stream" style="top: 80vh;"><div class="noto-bar" style="animation-direction: reverse;">ERROR_SYSTEM_FAILURE_RECOVERY_SIGNAL_STABLE_░▒▓█</div></div>

<div class="moving-element"></div>

<header>
    <h1>АНУФРИЕВ ДМИТРИЙ</h1>
</header>

<div class="menu">
    <a href="index.html" class="glitch-button">Галерея</a>
    <a href="about.html" class="glitch-button">Манифест</a>
</div>

<!-- ПАНЕЛЬ УПРАВЛЕНИЯ -->
<div class="controls-panel">
    <div class="control-group">
        <label>SIZE</label>
        <input type="range" id="sizeRange" min="20" max="300" value="70">
    </div>
    <div class="control-group">
        <label>SPEED</label>
        <input type="range" id="speedRange" min="1" max="30" value="11">
    </div>
</div>

<!-- ГАЛЕРЕЯ (С ТВОИМИ ССЫЛКАМИ) -->
<div class="gallery">
    
    <!-- Твоя картинка -->
    <div class="art-item">
        <img src="hand.jpg" alt="">
    </div>
    <div class="art-item">
        <img src="long.jpg" alt="">
    </div>


    <!-- Твое Видео (Добавь ссылку вместо vacuum.mp4) -->
    <div class="art-item">
        <video loop muted autoplay playsinline>
            <source src="vacuum.mp4" type="video/mp4">
        </video>
    </div>

    <!-- Добавляй новые art-item сюда -->

</div>

<!-- ОКНО ПРОСМОТРА -->
<div id="viewer-overlay" onclick="closeFull()">
    <div id="viewer-content" onclick="event.stopPropagation()"></div>
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
</script>

</body>
</html>
