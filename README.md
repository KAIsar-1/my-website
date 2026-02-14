<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Love is...</title>
<style>
    html, body {
        margin: 0;
        padding: 0;
        height: 100%;
        overflow: hidden;
        font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        background: #000;
    }

    #myVideo {
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        object-fit: cover;
        z-index: -2;
        display: none; /* Скрыто пока не кликнут */
    }

    .dark-layer {
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        background: rgba(0,0,0,0.4);
        z-index: -1;
        display: none;
    }

    .overlay {
        position: fixed;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        text-align: center;
        color: #fff;
    }

    .overlay img {
        max-width: 90%;
        max-height: 60%;
        border-radius: 20px;
        box-shadow: 0 0 30px rgba(0,0,0,0.7);
        opacity: 0;
        transform: translateY(20px);
        animation: fadeInUp 2s forwards;
        animation-delay: 0.5s;
    }

    .overlay h1 {
        font-family: 'Comic Sans MS', cursive, sans-serif;
        font-size: 3em;
        margin: 20px 0 10px;
        opacity: 0;
        transform: translateY(-20px);
        animation: fadeInText 2s forwards;
        animation-delay: 2s;
        color: #ffc0cb;
    }

    .overlay p {
        font-size: 1.8em;
        opacity: 0;
        transform: translateY(20px);
        animation: fadeInText 2s forwards;
        animation-delay: 2.5s;
        color: #ffe4e1;
    }

    @keyframes fadeInUp {
        from { opacity: 0; transform: translateY(20px); }
        to { opacity: 1; transform: translateY(0); }
    }

    @keyframes fadeInText {
        from { opacity: 0; transform: translateY(20px); }
        to { opacity: 1; transform: translateY(0); }
    }

    /* Курсор-указание на клик */
    .click-to-start {
        position: fixed;
        top: 0; left: 0;
        width: 100%; height: 100%;
        background: #000;
        display: flex;
        justify-content: center;
        align-items: center;
        color: #fff;
        font-size: 2em;
        cursor: pointer;
        z-index: 10;
    }
</style>
</head>
<body>

<!-- Видео -->
<video id="myVideo" muted loop playsinline>
    <source src="your-video.mp4" type="video/mp4">
    Ваш браузер не поддерживает видео.
</video>
<div class="dark-layer"></div>

<!-- Фото + текст -->
<div class="overlay">
    <h1>Love is...</h1>
    <img src="your-photo.jpg" alt="Моё фото">
    <p>выбрать быть вместе</p>
</div>

<!-- Экран "Нажмите, чтобы начать" -->
<div class="click-to-start" id="startScreen">Нажмите, чтобы начать</div>

<script>
    const startScreen = document.getElementById('startScreen');
    const video = document.getElementById('myVideo');
    const darkLayer = document.querySelector('.dark-layer');

    startScreen.addEventListener('click', () => {
        video.style.display = 'block';
        darkLayer.style.display = 'block';
        video.play(); // старт видео
        startScreen.style.display = 'none'; // убираем надпись
    });
</script>

</body>
</html>
